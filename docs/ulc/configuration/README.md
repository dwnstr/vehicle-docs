---
description: An overview of ULC features and configuration values
---

# Configuration

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

{% code title="config.lua" overflow="wrap" %}
```lua
-- whether to mute the tone that plays when lights are turned on, use if you have another resources that already plays a tone.
muteBeepForLights = true,
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

BrakeSettings = {
    -- brake effect will only be applied if vehicle was traveling above this speed
    speedThreshold = 30
},
...
```
{% endcode %}

## 2. Configure your first vehicle

By default, no vehicles are affected by ULC. In order for a vehicle to be affected by ULC there must be a configuration for it.

Let's start by setting up your first vehicle.

There are two methods for configuring a vehicle. Using an external `ulc.lua` file in the vehicle resource or adding the vehicle to the `config.lua` manually. \
\
We will use the first method as it is much cleaner and easier.\
\
If your vehicle already has a `ulc.lua` file, skip to step 7!

{% tabs %}
{% tab title="Importing ulc.lua" %}
{% hint style="success" %}
#### Preferred Method

This method loads a ulc.lua file directly from a vehicle resource. It results in a much cleaner config.lua file and makes it more user friendly to configure vehicles.



Additionally, this method means that vehicle developers can include a ulc.lua file along with their resource, so it can be ULC ready out-of-the-box!



Follow the steps below to configure a vehicle using a ulc.lua file.
{% endhint %}



{% hint style="warning" %}
In version 1.0.0 (old) the`ulc.lua`file MUST be in the`data`folder of your vehicle resource. Update to correct this.
{% endhint %}



1. Create a new file in your vehicle resource and name it `ulc.lua`
2. Open your new file and paste the below content.



```lua
return {name = "",
  steadyBurnConfig = {
      forceOn = false,
      useTime = false,
      sbExtras = {}
  },
  parkConfig = {
      usePark = false,
      useSync = false,
      syncWith = {""},
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
  -- example button
  -- {label = 'STAGE 2', key = 5, extra = 8},
  buttons = {
  }
}
```



3\. Add the [model name](#user-content-fn-1)[^1] of your vehicle at the top at `name = ""`&#x20;

ex. `name = "pd4"`\


### 4. Configure Vehicle Settings

Review the [steady burn](cruise-lights.md), [park](park-patterns.md), [horn](horn-extras.md), and [brake](brake-patterns.md) settings to match your vehicle.&#x20;

ex. If your vehicle has steady burns as extra 1 it should look like this:

```lua
steadyBurnConfig = {
    forceOn = false,
    useTime = true,
    sbExtras = {1}
},
```

I left `forceOn = false` since I want the steady burns to be on at night only. You can view full details about each config value in the pages for each section.



### 5. Configure your buttons!&#x20;

For details on stage control buttons you can view the [Stage Controls page.](stage-controls.md) Here's an example of how it could look.

```lua
buttons = {
    {label = 'STAGE 2', key = 1, extra = 8},
    {label = 'TA', key = 2, extra = 9},
    {label = 'TKD', key = 3, extra = 10},
}
```

This example vehicle has extra 8 as it's stage 2 pattern, extra 9 as it's traffic advisor, and extra 10 as takedown lights.\
I assigned these extras to keys 1, 2 and 3 on the numpad.



_Now that your ulc.lua file is complete, we will link your vehicle to ULC so that the config can be loaded!_

__

### 6. Open your ULC `config.lua` file



### 7. Find the `ExternalVehResources` table



### 8. Add the resource name of the vehicle you just configured!

This is how it should look:

```lua
ExternalVehResources = {
    "pd4",
},
```



9\. Restart ULC, and you should see that your config has loaded in the server console!\


<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Manual Addittions to config.lua" %}
{% hint style="info" %}
Worse Method

Manually create a vehicle configuration object and add it to the `Vehicles` table in `config.lua`
{% endhint %}

This method is messier, but is totally acceptable if the vehicle you are setting up did not come with a `ulc.lua` file.
{% endtab %}
{% endtabs %}

## Configuring Vehicles for ULC

Vehicle developers who are creating vehicles compatible with ULC can provide a local configuration file within their vehicle resources for use by users.

By providing a configuration file your vehicle will be pre-configured for all users who use it. Users will be able to simply plug-and-play your vehicle with ULC functionality.

Create a file named `ulc.lua` in your vehicle resource and paste the template below.&#x20;

{% hint style="warning" %}
Be sure to include the `return` tag!
{% endhint %}

```lua
return {name = "",
  steadyBurnConfig = {
      forceOn = false,
      useTime = false,
      sbExtras = {}
  },
  parkConfig = {
      usePark = false,
      useSync = false,
      syncWith = {""},
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
  -- example button
  -- {label = 'STAGE 2', key = 5, extra = 8},
  buttons = {
  }
}
```

The user now just has to add the resource name of the vehicle to their `Config.ExternalVehResources` table.

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

{% content-ref url="horn-extras.md" %}
[horn-extras.md](horn-extras.md)
{% endcontent-ref %}



[^1]: Model name is not the same as resource name! The model name is the name of the .ytf files.
