# Brake Patterns

Brake patterns allow you to enable extras while the vehicle is braking. There is a speed threshold variable that will prevent the effect from activating at low speeds if you desire.

**How to Create Brake Patterns**

Create a stage as normal, and assign it in the config! Generally the usage for brake patterns is to create a faster pattern while braking to grab more attention.

An alternative use for this feature is to add brake light emissives. The recommended way to do that would be to bind the emissives to the actual brake lights, but this could be a workaround.

**Brake Pattern Config**

{% code overflow="wrap" %}
```lua
BrakeSettings = {
    -- brake patterns will not activate below this speed
    -- if it's already active while you brake from 50 - 30 it will stay active until you release brakes
    speedThreshold = 30
},
```
{% endcode %}

**Brake Pattern Vehicle Config**

```lua
brakeConfig = {
    -- whether to use the brake effects
    useBrakes = true,

    -- extras to enable while braking
    brakeExtras = {12}
},
```
