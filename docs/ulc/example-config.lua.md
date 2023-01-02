# Example config.lua

{% code title="config.lua" overflow="wrap" lineNumbers="true" %}
```lua
-- Ultimate Lighting Controller by Dawnstar FiveM
-- Written by Dawnstar
-- For support: https://discord.gg/dwnstr-fivem

Config = {
    muteBeepForLights = true,
    useKPH = false,
    healthThreshold = 990,

    -- Park Pattern Settings;
    ParkSettings = {
        speedThreshold = 1,
        checkDoors = true,
        delay = 0.5,
        syncDistance = 32,
        syncCooldown = 10,
    },

    -- Steady Burn Config;
    SteadyBurnSettings = {
        nightStartHour = 18,
        nightEndHour = 6,
        delay = 10,
    },

    -- Brake Extras/Patterns Config;
    BrakeSettings = {
        speedThreshold = 30
    },

    -- the resource names of vehicle resources that include a ulc.lua config file
    ExternalVehResources = {
        -- ex. "my-police-vehicle",
    },

    Vehicles = {
        {name = 'example', -- Vehicle Spawn Name
        
            -- Steady Burn/Alaways On Settings
            steadyBurnConfig = {
                forceOn = false,
                useTime = true,
                sbExtras = {1}
            },
            -- Park Pattern Settings
            parkConfig = {
                usePark = true,
                useSync = true,
                syncWith = {'example', 'sp18chrg'},
                pExtras = {10, 11},
                dExtras = {}
            },
            -- Extras on Airhorn (E key)
            hornConfig = {
                useHorn = true,
                hornExtras = {12}
            },
            -- Brake Lights/Patterns Settings;
            brakeConfig = {
                useBrakes = false,
                brakeExtras = {12}
            },
            -- Stage Control Button Mappings
            buttons = {
                {label = 'STAGE 2', key = 5, extra = 8},
                {label = 'TA', key = 6, extra = 9},
                {label = 'AUX1', key = 7, extra = 10},
                {label = 'AUX 2',key = 8,extra = 11},
                {label = 'SCENE',key = 9,extra = 12},
            }
        },
        {name = 'example2', -- Vehicle Spawn Name
        
            -- Steady Burn/Alaways On Settings
            steadyBurnConfig = {
                forceOn = true,
                useTime = false,
                sbExtras = {2}
            },
            -- Park Pattern Settings
            parkConfig = {
                usePark = false,
                useSync = true,
                syncWith = {'example', 'sp18chrg'},
                pExtras = {10, 11},
                dExtras = {}
            },
            -- Extras on Airhorn (E key)
            hornConfig = {
                useHorn = true,
                hornExtras = {10}
            },
            -- Brake Lights/Patterns Settings;
            brakeConfig = {
                useBrakes = true,
                brakeExtras = {6}
            },
            -- Stage Control Button Mappings
            buttons = {
                {label = 'TA R', key = 5, extra = 2},
                {label = 'TA L', key = 6, extra= 3
                {label = 'TKD', key = 1, extra = 1},
            }
        },
    }
}
```
{% endcode %}
