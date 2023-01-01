---
description: An overview of ULC features and configuration values
---

# Configuration

ULC was designed to be as user-friendly as possible.&#x20;

Configuration is simple and extremely customizable.\
\
Vehicle developers can easily share vehicle configurations with users, and users can easily implement included configs in their server.

## Global Settings

The first section of the `config.lua` file contains a series of global settings. These settings determine the behavior of some features.&#x20;

Most settings can be left at their default value. If you are using Luxart Vehicle Controls or a similar resource that plays a tone when lights are turned on, you should set `muteBeepForLights` to `true.`

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

-- the resource names of vehicle resources that include a ulc.lua config file
ExternalVehResources = {
    -- ex. "my-police-vehicle",
},

-- table of vehicle configurations
Vehicles = {
}
```
{% endcode %}

## Vehicle Configuration

The second part of `config.lua` is a table of vehicle configurations.

By default, no vehicles are affected by ULC. In order for a vehicle to be affected by ULC there must be a configuration for it.



## Adding Vehicle Configurations to a Server

There are 2 methods for configuring a vehicle for use with ULC.

{% tabs %}
{% tab title="Importing ulc.lua" %}
{% hint style="success" %}
Preferred Method\
\
Load a `ulc.lua` config file directly from vehicle resource by adding the resource name to the `ExternalVehResources` table
{% endhint %}

This method makes ULC extremely user-friendly. This allows for plug-and-play ULC functionality with vehicles you download that are ULC ready.



Example:&#x20;

```lua
ExternalVehResources = {
  "my-vehicle-resource",
},
```



Of course, in order for this to work there has to be a ulc.lua file in the resource.&#x20;

In the case a vehicle did not have a `ulc.lua` config, you can opt to create one instead of using the other method. Follow instructions for vehicle developers for more info.
{% endtab %}

{% tab title="Manual Configs" %}
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
},
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

