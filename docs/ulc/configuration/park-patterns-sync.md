# Park Patterns/Sync

Park patterns allow you to automatically enable or disable extras based on the speed of the vehicle.

Park pattern will enable 2 seconds after vehicle is parked.

The feature is intended for use with park patterns, that is, enabling a park pattern stage extra when the vehicle comes to a full stop. However, you can specify the speed threshold to enable the extras when the vehicle is going below a certain speed if you want to.

**How to Create a Park Pattern**

To create a functional park pattern, create a stage extra that has a much slower pattern than your main lighting. If needed, be sure to create divider meshes to hide the underneath pattern.

Then configure your vehicle to enable that extra. You can also choose to disable another extra when parked. These extras will switch between each other based on whether the vehicle is parked or driving automatically.

**Park Config**

{% code overflow="wrap" %}
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
{% endcode %}

**Vehicle Park Config**

```lua
parkConfig = {
    -- whether to use park pattern or not
    -- accepts: boolean
    usePark = true

    -- whether to use park pattern syncing or not
    -- accepts: boolean
    useSync = true

    -- vehicles that this vehicle with sync with
    -- you do not need to include the vehicle itself
    -- if your config is for more than one vehicle include all of them here
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
