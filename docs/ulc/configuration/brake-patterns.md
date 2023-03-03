# Brake Extras

Brake extras allow you to enable extras while the vehicle is braking. There is a speed threshold variable that will make the effect only activate at higher speeds if you prefer.3

**How to Create Brake Patterns**

The primary use for this feature is adding functional brake lights as extras.

Create a stage as normal, and assign it in the config! Generally the usage for brake patterns is to create a faster pattern while braking to grab more attention.

An alternative use is to add a faster or brighter pattern that will show only while the vehicle brakes at high speeds. To do this create a new stage as normal, and change `speedThreshold` to a higher value.

{% hint style="info" %}
Brake extras are not state aware.
{% endhint %}

**Brake Pattern Vehicle Config**

```lua
brakeConfig = {
    -- whether to use the brake effects
    useBrakes = true,
    
    -- below this speed the effect is disabled
    -- at 3 or below, realistic brakes are enabled (extra will stay on when stopped)
    speedThreshold = 3,

    -- extras to enable while braking
    brakeExtras = {12}
},
```
