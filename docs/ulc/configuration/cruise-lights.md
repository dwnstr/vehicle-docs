# Cruise Lights

The cruise lights feature allows you to specify extras that will be enabled by the time of day, or always if you choose.

**How to Create Cruise Lights**

Cruise lights don't have to be sirens. They can just be plain emissive meshes that aren't scaled down.

Simply create an extra that is just cruise light emissives. Make sure the emissives are dimmed down!

If you want environment lighting, or you want the steady burns to only show when the emergency lights are activated, then you should make these a siren.

## **Cruise Light Config Example**

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

## Vehicle Cruise Light Config Example

```lua
steadyBurnConfig = {
        -- whether to force cruise lights 24/7 (overrides useTime)
        forceOn = false,
        
        -- whether to use cruise lights at night
        useTime = true,
        
        -- whether to disable cruise lights when main lights activate
        disableWithLights = false,
        
        -- extras that will be activated
        sbExtras = {1, 2}
},
```
