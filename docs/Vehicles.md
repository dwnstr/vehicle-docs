# Vehicles.meta
## Overview

Hello world!

## Extras

Most of the content here was originally provided by [a63nt-5m1th](https://forums.gta5-mods.com/user/a63nt-5m1th) at the link below!

> Source: [\[ Tutorial \] How to make specific vehicle EXTRAS appear on a vehicle EVERY spawn. | GTA5-Mods.com Forums](https://forums.gta5-mods.com/topic/19786/tutorial-how-to-make-specific-vehicle-extras-appear-on-a-vehicle-every-spawn)

### Flags

``FLAG_EXTRAS_REQUIRE`` 

Always spawns with EXACTLY 1 RANDOM extra.

``FLAG_EXTRAS_ALL`` 

Always spawns with ALL extras

``FLAG_EXTRAS_RARE`` 

Spawns with only one random extra but ONLY ~15% of the time. (85% of the time, no extras will spawn)

### Forcing Specific Extras

Below is how you can force specific extras to be enabled when the vehicle spawns. This specific method does NOT prevent other extras from also spawning.

1. Change ```<extraIncludes />``` to ```<extraIncludes>```
2. Change ```<requiredExtras />``` to ```<requiredExtras> <requiredExras />```
3. Fill the ``requiredExtras`` tag with the extras you want to force separated by spaces.

Example
```xml
<requiredExtras>EXTRA_4 EXTRA_5</requiredExtras>
```
In this example, the vehicle will now always spawn with                                                                                                                                                           Extra 4 and Extra 5. Again, it could also spawn with other extras depending on the rest of the setup, but now it will always spawn with 4 and 5.

Both tags must be changed correctly, or the vehicle will revert to the default behavior of spawning with random extras.

#### HOW THESE EDITS WORK IN COMBINATION WITH FLAGS

These two settings above work in combination with any flags set in the ```<flags>``` line.

For example if I was to add ``FLAG_EXTRAS_REQUIRE`` to the ```<flags>``` line also, then **EXTRA_4**, **EXTRA_11** & one random EXTRA would be enabled.

In this scenario it is also possible for the ``FLAG_EXTRAS_REQUIRE`` random extra to also be either ``EXTRA_4`` or ``EXTRA_11`` (rather than a different random extra) resulting in only ``EXTRA_4`` & ``EXTRA_11`` appearing some of the time.

``FLAG_EXTRAS_ALL`` will overwrite this effects and will still force all extras to spawn.

For ``FLAG_EXTRAS_RARE`` see below.

### STOPPING SPECIFIC EXTRAS FROM SPAWNING

Short answer: There's no way to 100% prevent certain extras from spawning.

The closest possible solution is using ```<extraIncludes>``` and ```<requiredExtras>``` in combination with ``FLAG_EXTRAS_RARE``. With this setup, you will get only ``EXTRA_4`` and ``EXTRA_11``, but 10-15% of the time there will be a random extra in addition.

**Extra:** I'm not sure how much use this will be or whether it even applies to any cars other than the [Dodge Dart](https://www.gta5-mods.com/vehicles/68-dodge-dart-hemi-add-on-livery-animated-hq) I was testing but I'll mention it anyway.

I was able to enter '**FLAG\_EXTRAS\_RARE**' & '**FLAG\_EXTRAS\_SCRIPT**' in the '**<flags>**' line in combination with the two edits & was able to have EXTRA\_4 & EXTRA\_11 spawn all of the time but restict the random (~10%>15% of the time) EXTRA to only be able to select EXTRA\_1, EXTRA\_2 or EXTRA\_3 (no other higher numbered random EXTRAS appeared in ~350 or so spawns). It may be pure luck GTA unicorns but it worked out rather well so try it out if you think that it might suit your need
