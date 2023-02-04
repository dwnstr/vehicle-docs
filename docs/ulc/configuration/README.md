---
description: An overview of ULC features and configuration values
---

# Configuration

{% embed url="https://youtu.be/FIF3qqRY0Ts" %}
ode
{% endembed %}

\
ULC was designed to be as user-friendly as possible.&#x20;

Configuration is simple and extremely customizable.\
\
Vehicle developers can easily share vehicle configurations with users, and users can easily implement included configs in their server.

## 1. Review Global Settings

The top section of the `config.lua` file contains a series of global settings. These settings determine the behavior of some features.&#x20;

_**Most settings can be left at their default value.**_&#x20;

{% hint style="info" %}
If you are using Luxart Vehicle Controls or a similar resource that plays a tone when lights are turned on, you should set `muteBeepForLights` to `true.`
{% endhint %}

<pre class="language-lua" data-title="config.lua" data-overflow="wrap"><code class="lang-lua">-- whether to mute the tone that plays when lights are turned on, use if you have another resources that already plays a tone.
muteBeepForLights = true,
-- global toggle for UI (affects all clients)
hideHud = false,
-- whether to use KPH instead of MPH
useKPH = false,
-- health threshold for effect (probably don't touch this)
healthThreshold = 990,

ParkSettings = {
    -- Vehicle will be considered "parked" below this speed
    speedThreshold = 1,
    -- whether to disable the effect when a door is open (highly recommended)
    checkDoors = true,
    -- delay between checks, should not be lower than 0.5
    delay = 0.5,
    -- distance to sync park pattern (32 is roughly the Yellow Jack parking lot)
    syncDistance = 32,
    -- cooldown between sync attempts
    syncCooldown = 10,
},
    
SteadyBurnSettings = {
    nightStartHour = 18,
    -- should always be a lower number than start hour
    nightEndHour = 6,
    -- delay between checks, this can be very long, it will only make it more realistic
    delay = 10,
},
<strong>...
</strong></code></pre>

## 2. Configure your first vehicle

By default, no vehicles are affected by ULC. In order for a vehicle to be affected by ULC there must be a configuration for it.

Let's start by setting up your first vehicle.

There are two methods for configuring a vehicle. Using an external `ulc.lua` file in the vehicle resource or adding the vehicle to the `config.lua` manually. \
\
We will use the first method as it is much cleaner and easier.

{% hint style="info" %}
If your vehicle already has a `ulc.lua` file, [skip to step 6!](https://docs.dwnstr.com/ulc/configuration#6.-open-your-ulc-config.lua-file)
{% endhint %}

{% tabs %}
{% tab title="Creating a ulc.lua file" %}
{% hint style="success" %}
#### Preferred Method

This method loads a ulc.lua file directly from a vehicle resource. It results in a much cleaner config.lua file and makes it more user friendly to configure vehicles.



Additionally, this method means that vehicle developers can include a ulc.lua file along with their resource, so it can be ULC ready out-of-the-box!



Follow the steps below to configure a vehicle using a ulc.lua file.
{% endhint %}

###

Let's get started!



### 1. Create a new file in your vehicle resource and name it `ulc.lua`

###

### 2. Open your new file and paste the below content.



<pre class="language-lua"><code class="lang-lua"><strong>return { names = {"yourvehiclename"},
</strong>    steadyBurnConfig = {
        forceOn = false,
        useTime = false,
        disableWithLights = false,
        sbExtras = {}
    },
    parkConfig = {
        usePark = false,
        useSync = false,
        syncWith = { "" },
        pExtras = {},
        dExtras = {}
    },
    hornConfig = {
        useHorn = false,
        hornExtras = {}
    },
    brakeConfig = {
        useBrakes = false,
        brakeExtras = {}
    },
    reverseConfig = {
        useReverse = false,
        speedThreshold = 3,
        reverseExtras = {}
    },

    --[[ example button
        {label = 'STAGE 2', key = 5, extra = 8, linkedExtras = {}, offExtras = {1, 2}},
    ]]

    buttons = { --paste your buttons below


    }
}
</code></pre>



### 3. Define the [model name](#user-content-fn-1)[^1]&#x20;

Add the name of your vehicle model at `name = ""`&#x20;

ex. `name = "pd4"`\


### 4. Configure Vehicle Settings

Review the [steady burn](cruise-lights.md), [park](park-patterns.md), [horn](horn-extras.md), and [brake](brake-patterns.md) settings to match your vehicle.&#x20;

ex. If your vehicle has steady burns as extra 1 it could look like this:

```lua
steadyBurnConfig = {
    forceOn = false,
    useTime = true,
    disableWithLights = false,
    sbExtras = {1}
},
```

I left `forceOn = false` since I want the steady burns to be on at night only. You can view full details about each config value in the pages for each section.



### 5. Configure your buttons!&#x20;

For details on stage control buttons you can view the [Stage Controls page.](stage-controls.md) Here's an example of how it could look.

```lua
buttons = {
    {label = 'STAGE 2', key = 1, extra = 8, linkedExtras = {10, 11}, offExtras = {9}},
    {label = 'TA', key = 2, extra = 9, linkedExtras = {}, offExtras = {}},
    {label = 'AUX1', key = 3, extra = 10, linkedExtras = {}, offExtras = {}},
    {label = 'TKD', key = 5, extra = 12, linkedExtras = {}, offExtras = {8}},
}
```

This example vehicle has extra 8 as it's stage 2 pattern, extra 9 as it's traffic advisor, and extra 10 as take-down lights. I assigned these extras to keys 1, 2 and 3 on the numpad.



_Now that your ulc.lua file is complete, we will link your vehicle to ULC so that the config can be loaded!_

__

### 6. Open your ULC `config.lua` file



### 7. Find the `ExternalVehResources` table



### 8. Import the Config!

Add the resource name of the vehice you configured.

This is how it should look:

```lua
ExternalVehResources = {
    "pd4",
},
```

{% hint style="warning" %}
Remember, this is not the model name/spawn name. The resource name is the name of the folder.
{% endhint %}



### 9. That's it!

Restart ULC, and you should see that your config has loaded in the server console!\


<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### 10. Repeat for your other vehicles!
{% endtab %}

{% tab title="Manual Adittions to config.lua" %}
{% hint style="info" %}
Worse Method

Manually create a vehicle configuration object and add it to the `Vehicles` table in `config.lua`
{% endhint %}

This method is messier, but is totally acceptable if the vehicle you are setting up did not come with a `ulc.lua` file.
{% endtab %}
{% endtabs %}

## Configuring a Vehicle Pack

If multiple vehicles in the same pack can use _**the same ULC configuration settings**_, you can simply include all of the spawn names in the `names` field of a single configuration in the ulc.lua file.

Ex:

```lua
{names = {"sp20", "sp20"},
...
```

If there are vehicles in the pack that don't share _**the same configuration settings**_, you need to add a another configuration to the ulc.lua file.\
\
See [the example](./#multi-config-ulc.lua-example) below.

<details>

<summary>Multi-Config ulc.lua Example</summary>

```lua
return {names = {"sp20", "pd20"},
    steadyBurnConfig = {
        forceOn = false,
        useTime = false,
        disableWithLights = false,
        sbExtras = {}
    },
     parkConfig = {
        usePark = true,
        useSync = true,
        syncWith = {'sp20', 'sp18chrg'},
        pExtras = {10, 11},
        dExtras = {}
    },
    hornConfig = {
        useHorn = true,
        hornExtras = {12}
    },
    brakeConfig = {
        useBrakes = false,
        speedThreshold = 3,
        brakeExtras = {}
    },
  -- example button
  -- {label = 'STAGE 2', key = 5, extra = 8},
    buttons = {
        {label = 'stage 2', key = 5, extra = 8, offExtras = {10, 11}},
        {label = 'TA', key = 6, extra = 9, offExtras = {}},
        {label = 'AUX1', key = 7, extra = 10, offExtras = {}},
        {label = 'AUX 2',key = 8,extra = 11, offExtras = {}},
        {label = 'SCENE',key = 9,extra = 12, offExtras = {}},
    }
},
{names = {'pdram'}, -- Vehicle Spawn Names
        
	steadyBurnConfig = {
		forceOn = false,
		useTime = false,
		sbExtras = {}
	},

	parkConfig = {
		usePark = true,
		useSync = false,
		syncWith = {},
		pExtras = {9},
		dExtras = {}
	},

	hornConfig = {
		useHorn = true,
		hornExtras = {12}
	},

	brakeConfig = {
		useBrakes = false,
		speedThreshold = 3,
		brakeExtras = {}
	},

	buttons = {
		{label = 'AUX', key = 5, extra = 8, offExtras = {}},
		{label = 'TA L', key = 6, extra = 9, offExtras = {}},
		{label = 'TA R', key = 7, extra = 10, offExtras = {}},
		{label = 'TKD', key = 8, extra = 11, offExtras = {}},
	}
}
```



</details>

## Creating Non-ELS Vehicles for ULC

Vehicle developers who are creating vehicles compatible with ULC can provide a local configuration file within their vehicle resources for use by users.

By providing a configuration file your vehicle will be pre-configured for all users who use it. Users will be able to simply plug-and-play your vehicle with ULC functionality.

Follow steps 1 - 5 above to learn how to create a ulc.lua file.

### Extras with Sirens

The concept of nesting Sirens into an Extra is critical to proper usage of ULC. Most of the features of ULC require sirens to be contained within extras.

All you have to do to set this up is parent your Sirens to an Extra once they are compounded. Your extra can have any other parts also attached. I.E you could have a divider to block the emissives behind the emissives you want to show, such as in the case of a traffic advisor.

For detailed info about each feature and their config values see the below pages.

{% content-ref url="stage-controls.md" %}
[stage-controls.md](stage-controls.md)
{% endcontent-ref %}

{% content-ref url="park-patterns.md" %}
[park-patterns.md](park-patterns.md)
{% endcontent-ref %}

{% content-ref url="cruise-lights.md" %}
[cruise-lights.md](cruise-lights.md)
{% endcontent-ref %}

{% content-ref url="brake-patterns.md" %}
[brake-patterns.md](brake-patterns.md)
{% endcontent-ref %}

{% content-ref url="reverse-extras.md" %}
[reverse-extras.md](reverse-extras.md)
{% endcontent-ref %}

{% content-ref url="horn-extras.md" %}
[horn-extras.md](horn-extras.md)
{% endcontent-ref %}



[^1]: Model name is not the same as resource name! The model name is the name of the .ytf files.
