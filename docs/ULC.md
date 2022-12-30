# Ultimate Lighting Controller Documentation

ULS (Ultimate Lighting Controller) is a resource created by Dawnstar that gives you full control of lights on Emergency Vehicles built with Non-ELS.

ULC primarily interacts wit extras on your vehicles, so you will need to place sirens in extras, and plan your vehicle and siren layout accordingly.

*See something wrong? Create an issue!*

# Features
- Stage Controls
- Park Patterns
- Brake Patterns/Extras
- Automated Cruise Lights
- Horn Patterns/Extras
- Fully configurable 

ULC focuses on being as customizable as possible, to fit every possible scenario. You can individually configure every vehicle you choose to use this resource with. 

Each vehicle can use just one feature, or 3, or all of them. It's completely up to you.

<hr>

- [Ultimate Lighting Controller Documentation](#ultimate-lighting-controller-documentation)
- [Features](#features)
- [ULC for Server Owners](#ulc-for-server-owners)
  - [How to Setup ULC in your Server](#how-to-setup-ulc-in-your-server)
    - [Installation](#installation)
    - [Configuration](#configuration)
      - [How to Import an Included Config](#how-to-import-an-included-config)
      - [How to Manually Configure a Vehicle](#how-to-manually-configure-a-vehicle)
- [ULC for Vehicle Developers](#ulc-for-vehicle-developers)
  - [How to Share ULC Configurations with Users](#how-to-share-ulc-configurations-with-users)
  - [How to Create Vehicles for ULC](#how-to-create-vehicles-for-ulc)
    - [Extras with Sirens](#extras-with-sirens)
    - [Stage Controls](#stage-controls)
      - [Example Usage](#example-usage)
      - [How to Create a Stage](#how-to-create-a-stage)
      - [Vehicle Stage Config](#vehicle-stage-config)
    - [Park Patterns/Extras](#park-patternsextras)
      - [How to Create a Park Pattern](#how-to-create-a-park-pattern)
      - [Park Config](#park-config)
      - [Vehicle Park Config](#vehicle-park-config)
    - [Cruise Lights/Steady Burns](#cruise-lightssteady-burns)
      - [How to Create Cruise Lights](#how-to-create-cruise-lights)
      - [Cruise Light Config](#cruise-light-config)
      - [Vehicle Cruise Light Config](#vehicle-cruise-light-config)
    - [Brake Patterns](#brake-patterns)
      - [How to Create Brake Patterns](#how-to-create-brake-patterns)
      - [Brake Pattern Config](#brake-pattern-config)
      - [Brake Pattern Vehicle Config](#brake-pattern-vehicle-config)
    - [Horn Patterns/Extras](#horn-patternsextras)
      - [Vehicle Horn Extras Config](#vehicle-horn-extras-config)

<hr>

# ULC for Server Owners
## How to Setup ULC in your Server
### Installation
1. Extract ``ulc`` from your download.
2. Place ``ulc`` anywhere in your resources folder.
3. Add ``ensure ulc`` to your server.cfg

### Configuration

The only necessary configuration step is to add or configure vehicles. There are two possible methods.
1. Automatically import vehicle configurations from vehicle resources.
2. Manually add vehicle configurations to the ``Config.Vehicles`` table.

#### How to Import an Included Config
Some vehicle resources may come with a ``ulc.lua`` file. 

If this is the case all you have to do to configure the vehicle is add the resource name to the ``Config.ExternalVehResources`` table.

Example:
```lua
ExternalVehResources = {
  "my-vehicle-resource",
},
```

#### How to Manually Configure a Vehicle
If the vehicle did not come with a ``ulc.lua`` file, you will need to manually create a configuration for the vehicle. You can either add this configuration directly to the ``config.lua`` in the ``Config.Vehicles`` table, or you can create a ``ulc.lua`` file in the vehicle resource and follow the same instructions as above.

For details on all configurations, see the config value documentation below.

# ULC for Vehicle Developers
## How to Share ULC Configurations with Users

ULC is able to grab configuration data from other resources.

If you are releasing a vehicle, and would like to provide users with a configuration file so that your vehicle can be pre-configured for ULC users, you can include a ``ulc.lua`` file in the resource.

The ``ulc.lua`` file will be loaded by ULC, and will work as if it was added manually to the ``Config.Vehicles`` table.

Create a file named "ulc.lua with your configuration like so...<br>
*Note the ``return`` before the table.

```lua
return {name = 'sp20',
  steadyBurnConfig = {
      forceOn = false,
      useTime = true,
      sbExtras = {1}
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
      useBrakes = true,
      brakeExtras = {12}
  },
  buttons = {
    {label = 'STAGE 2', key = 5, extra = 8},
    {label = 'SCENE', key = 6, extra = 12},
    {label = 'TA', key = 7, extra = 9},
  }
},
```
The user now just has to add the resource name of the vehicle to their ``Config.ExternalVehResources`` table.

## How to Create Vehicles for ULC

### Extras with Sirens

The concept of nesting Sirens into an Extra is critical to proper usage of ULC. Most of the features of ULC require sirens to be contained within extras.

All you have to do to set this up is parent your Sirens to an Extra once they are compounded. Your extra can have any other parts also attached. I.E you could have a divider to block the emissives behind the emissives you want to show, such as in the case of a traffic advisor.

### Stage Controls

Stage controls allow the driver of the vehicle to dynamically switch between extras at the press of a button using the number pad. This is not a new concept to vehicle developers, but ULC focuses on a great user experience, and flexibility. 

You can individually assign each extra you want to use to any numpad key, and assign a custom label to it.

Only the keys you define will appear on the UI, and the extras are bound to them individually.

#### Example Usage
- Traffic Advisors
- Flood/Scene/Alley Lighting
- Alternative Patterns
- Stage 2 Lighting
- Much more!

Any stages you create can also be used by any other feature of the resource. For example, if you create a stage extra that has an alternate pattern, you can then use that pattern as your brake pattern.

Stages are fully state aware, meaning if your alt pattern was enabled before you started braking, it will remain on after you finish braking. The same logic applies other features, except park patterns. 

#### How to Create a Stage

The hardest part of creating stages is planning out your vehicle. Sirens parented to extras only show when the extra is enabled, so those Sirens are effectively eliminated from your workflow. They can't be re-used anywhere else. 

This can have you pretty short on sirens if you commit too many of them to extras that aren't used often. Siren Tool can help you with planning out your vehicle to be very efficient with sirens.

Other than that, the process is pretty straight forward. 

- Compound sirens as usual
- Parent sirens to your extra

#### Vehicle Stage Config
**Example Button**
```lua
{   -- the name/label that will show on the UI
    label = 'STAGE 2',
    -- which numpad key the stage will use by default
    -- players can remap these keys on their own
    key = 5,
    -- the extra that this key will toggle
    extra = 8 -- num 5
},

```
**Example Configuration**

Each vehicle can have a minimum of 0 buttons, and a maximum of 9.
Any buttons not configured will not show. 

Buttons can not share the same extra.

Keys don't have to be used in order or sequentially. You could use 5, 3, 1, 7, 2 if you wanted.
```lua
 buttons = {
    {label = 'STAGE 2', key = 1, extra = 8},
    {label = 'TA', key = 2, extra = 9},
    {label = 'AUX1', key = 3, extra = 10},
    {label = 'AUX 2', key = 4, extra = 11},
    {label = 'SCENE', key = 5, extra = 12},
}
```

### Park Patterns/Extras

Park patterns allow you to automatically enable or disable extras based on the speed of the vehicle. 

The feature is intended for use with park patterns, that is, enabling a park pattern stage extra when the vehicle comes to a full stop. However, you can specify the speed threshold to enable the extras when the vehicle is going 
below a certain speed if you want to.

#### How to Create a Park Pattern

To create a functional park pattern, create a stage extra that has a much slower pattern than your main lighting. If needed, be sure to create divider meshes to hide the underneath pattern. 

Then configure your vehicle to enable that extra. You can also choose to disable another extra when parked. These extras will switch between each other based on whether the vehicle is parked or driving automatically.

#### Park Config

```lua
ParkSettings = {
    -- extras will toggle below this speed
    speedThreshold = 1,
    -- check if any doors are fully open before executing effect (prevents doors from always snapping shut)
    checkDoors = true,
    -- time between checks in seconds
    -- should not need to be any lower than .5 seconds
    -- higher values may look more realistic
    delay = 0.5,
    -- distance at which to check for other vehicles to sync patterns with
    syncDistance = 32,
    -- seconds before a single client triggers sync again 
    -- I'm not aware of anything specific that this fixes, but it seems like a safe move and shouldn't affect the outcome.
    syncCooldown = 10,
},
```

#### Vehicle Park Config
```lua
parkConfig = {
    -- whether to use park pattern or not
    -- accepts: boolean
    usePark = true

    -- whether to use park pattern syncing or not
    -- accepts: boolean
    useSync = true

    -- vehicles that this vehicle with sync with
    -- accepts: table of vehicle spawn names
    syncWith = {'police', 'police2'}

    -- extras that will be enabled when the vehicle comes to a stop
    -- accepts: table of integers
    pExtras = {1, 3}

    -- extras that will be disabled when the vehicle comes to a stop
    -- accepts: table of integers
    dExtras = {9}
}
```

### Cruise Lights/Steady Burns

The cruise lights feature allows you to specify extras that will be enabled by the time of day, or always if you choose.

#### How to Create Cruise Lights

Cruise lights don't have to be sirens. They can just be plain emissive meshes that aren't scaled down. 

Simply create an extra that is just cruise light emissives. Make sure the emissives are dimmed down!

If you want environment lighting, or you want the steady burns to only show when the emergency lights are activated, then you should make these a siren.

#### Cruise Light Config

```lua
SteadyBurnSettings = {
    -- the game hour when the effect starts (extras are enabled)
    nightStartHour = 18,

    -- the game hour when effect ends (extras are disabled)
    nightEndHour = 6,

    -- specifies time between checks in seconds
    -- should be high (checks also occur when entering vehicle)
    -- should NEVER be lower than 2 seconds (bad things will happen)
    delay = 10,
},
```

#### Vehicle Cruise Light Config 

```lua
steadyBurnConfig = {
    -- whether to force steady burns on this vehicle;
    -- overrides useTime, lights will always be on
    forceOn = false,

    -- whether to enable steady burns at night on this vehicle
    useTime = true,

    -- extras to enable for steady burns
    sbExtras = {1}
},
```

### Brake Patterns

Brake patterns allow you to enable extras while the vehicle is braking. There is a speed threshold variable that will prevent the effect from activating at low speeds if you desire.

#### How to Create Brake Patterns

Create a stage as normal, and assign it in the config! Generally the usage for brake patterns is to create a faster pattern while braking to grab more attention.

An alternative use for this feature is to add brake light emissives. The recommended way to do that would be to bind the emissives to the actual brake lights, but this could be a workaround.

#### Brake Pattern Config

```lua
BrakeSettings = {
    -- brake patterns will not activate below this speed
    -- if it's already active while you brake from 50 - 30 it will stay active until you release brakes
    speedThreshold = 30
},
```

#### Brake Pattern Vehicle Config

```lua
brakeConfig = {
    -- whether to use the brake effects
    useBrakes = true,

    -- extras to enable while braking
    brakeExtras = {12}
},
```

### Horn Patterns/Extras

This feature allows you to bind extras to your airhorn. For example, you could enable a more aggressive/faster pattern , or takedown lights while the horn is in use.

Simply create a stage extra as usual, and assign it in the config.

#### Vehicle Horn Extras Config

```lua
hornConfig = {
    useHorn = true,
    hornExtras = {12}
},
```

