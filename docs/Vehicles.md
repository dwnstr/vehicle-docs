# vehicles.meta

The vehicles.meta defines the main features / functions of the vehicle. This includes:

* [Vehicles.meta](Vehicles.md#vehiclesmeta)
  * [Overview](Vehicles.md#overview)
  * [Vehicle naming](Vehicles.md#vehicle-naming)
  * [Animations](Vehicles.md#animations)
  * [Vehicle Audio](Vehicles.md#vehicle-audio)
  * [VFX Info](Vehicles.md#vfx-info)
  * [Wheel Scale](Vehicles.md#wheel-scale)
  * [LOD Distances](Vehicles.md#lod-distances)
  * [Swankness](Vehicles.md#swankness)
  * [Extras](Vehicles.md#extras)
    * [Flags](Vehicles.md#flags)
    * [Forcing Extras](Vehicles.md#forcing-extras)
    * [Preventing Specific Extras from Spawning](Vehicles.md#preventing-specific-extras-from-spawning)
  * [Type](Vehicles.md#type)
  * [Plate Type](Vehicles.md#plate-type)
  * [Vehicle class](Vehicles.md#vehicle-class)
  * [Trailers](Vehicles.md#trailers)
  * [TXD Relationships](Vehicles.md#txd-relationships)

This is just to name a few of the important parts. A lot of the values / options will never be used.

## Vehicle naming

The first few lines within the vehicles.meta defines the vehicle.

```xml
<modelName>tow_truck</modelName>
<txdName>tow_truck</txdName>
<handlingId>tow_truck</handlingId>
<gameName>tow_truck</gameName>
<vehicleMakeName>20FORD</vehicleMakeName>
```

The **modelName** defines the .yft name within the stream folder. The **txdName** is the name of the texture dictionary that the vehicle uses. The **handlingID** links directly to the handling.meta name. The **gamename** doesn't have a lot of use (that we know of) so is best to set it to the same as the modelname. The **vehicleMakeName** is what company made the vehicle. E.G:

| Label    | Displayed string |
| -------- | ---------------- |
| ALBANY   | Albany           |
| ANNIS    | Annis            |
| BENEFAC  | Benefactor       |
| BF       | BF               |
| BOLLOKAN | Bollokan         |
| BRAVADO  | Bravado          |
| BRUTE    | Brute            |
| BUCKING  | Bukingham        |
| CANIS    | Canis            |
| CHARIOT  | Chariot          |
| CHEVAL   | Cheval           |
| COIL     | Coil             |
| DECLASSE | Declasse         |
| DEWBAUCH | Dewbauchee       |
| DINKA    | Dinka            |
| DUNDREAR | Dundreary        |
| EMPEROR  | Emperor          |
| ENUS     | Enus             |
| FATHOM   | Fathom           |
| GALLIVAN | Gallivanter      |
| GROTTI   | Grotti           |
| HIJAK    | Hijak            |
| HVY      | HVY              |
| IMPONTE  | Imponte          |
| INVERTO  | Invetero         |
| JACKSHP  | Jacksheepe       |
| JOBUILT  | Jobuilt          |
| KARIN    | Karin            |
| KRAKEN   | Kraken           |
| LAMPADA  | Lampadati        |
| LCC      | LCC              |
| MAIBATSU | Maibatsu         |
| MAMMOTH  | Mammoth          |
| MAXWELL  | Maxwell          |
| MTL      | MTL              |
| NAGASAKI | Nagasaki         |
| OBEY     | Obey             |
| OCELOT   | Ocelot           |
| OVERFLOD | Overflod         |
| PEGASSI  | Pegassi          |
| PFISTER  | Pfister          |
| PRINCIPL | Principe         |
| PROGEN   | Progen           |
| RUNE     | Rune             |
| SCHYSTER | Schyster         |
| SHITZU   | Shitzu           |
| SPEEDOPH | Speedophile      |
| STANLEY  | Stanley          |
| TRUFFADE | Truffade         |
| UBERMACH | Ubermacht        |
| VAPID    | Vapid            |
| VULCAR   | Vulcar           |
| VYSSER   | Vysser           |
| WEENY    | Weeny            |
| WESTERN  | Western          |
| WILLARD  | Willard          |
| ZIRCONIU | Zirconium        |

These are all the base game manufacturer that are used. With Rockstars new policy / TOS on RP servers it may be a good idea to stick with these when making vehicles.

## Animations

The animations are created in zmodeler 3 but are defined within the vehicles.meta. The following code will allow you hold **H** when inside the vehicle in game to play the animation.

```xml
<animConvRoofDictName>AnimationDictName</animConvRoofDictName>
<animConvRoofName>AnimationName</animConvRoofName>
```

The **animConvRoofDictName** is set to what the .ycd file is called once it has been exported from zmodeler and put into the vehicles stream folder. The **animConvRoofName** is the name of the animation within the .ycd file. Get this from the animation window within zmodeler.

Usually, these two are the same name.

## Vehicle Audio

The vehicle audio is used to define what audio is used for the vehicle.

```xml
<audioNameHash>fbi2</audioNameHash>
```

The value inside the tags can be changed almost any vehicle in the game. [Here is a list of different sounds and desciptions to use.](https://forums.gta5-mods.com/topic/14011/reference-vehicle-sound-guide)

## VFX Info

The VFX info mainly defines the type of effects used on the vehicle.

```xml
<vfxInfoName>VFXVEHICLEINFO_CAR_GENERIC</vfxInfoName>
```

This is will have the standard vehicle smoke but **VFXVEHICLEINFO\_TRUCK\_RIG** will set the vehicle to have a diesel exhaust smoke effect.

## Wheel Scale

The wheel scale defines how much of the rubber tyre is actually removed when the trye is bursted. This value is normally set to **0.292300** but the exact value of the wheel can be found in zmod by scaling down the wheel col.

```xml
<wheelScale value="0.292300" />
<wheelScaleRear value="0.292300" />
```

## LOD Distances

The LOD Distances defines how far away from the vehicle you have to be for the different levels of details are rendered. Its best to leave these as standard but good to know what they do.

```xml
<lodDistances content="float_array">
  35.000000
  45.000000
  150.000000
  250.000000
  500.000000
  500.000000
</lodDistances>
```

## Swankness

This isn't important to the vehicle but it defines whether the AI will take notice in your car. For example, if you are in a high end expensive car with the swankness level being 5 they will be more likely to stop and take a picture of your vehicle.

```xml
<swankness>SWANKNESS_1</swankness>
```

## Extras

Most of the content here was originally provided by [a63nt-5m1th](https://forums.gta5-mods.com/user/a63nt-5m1th) at the link below!

> Source: [\[ Tutorial \] How to make specific vehicle EXTRAS appear on a vehicle EVERY spawn. | GTA5-Mods.com Forums](https://forums.gta5-mods.com/topic/19786/tutorial-how-to-make-specific-vehicle-extras-appear-on-a-vehicle-every-spawn)

### Flags

`FLAG_EXTRAS_REQUIRE`

Always spawns with EXACTLY 1 RANDOM extra.

`FLAG_EXTRAS_ALL`

Always spawns with ALL extras

`FLAG_EXTRAS_RARE`

Spawns with only one random extra but ONLY \~15% of the time. (85% of the time, no extras will spawn)

### Forcing Extras

Below is how you can force specific extras to be enabled when the vehicle spawns. This specific method does NOT prevent other extras from also spawning.

1. Change `<extraIncludes />` to `<extraIncludes>`
2. Change `<requiredExtras />` to `<requiredExtras> <requiredExras />`
3. Fill the `requiredExtras` tag with the extras you want to force separated by spaces.

Example

```xml
<requiredExtras>EXTRA_4 EXTRA_5</requiredExtras>
```

In this example, the vehicle will now always spawn with Extra 4 and Extra 5. Again, it could also spawn with other extras depending on the rest of the setup, but now it will always spawn with 4 and 5.

Both tags must be changed correctly, or the vehicle will revert to the default behavior of spawning with random extras.

These two settings above work in combination with any flags set in the `<flags>` line.

For example if I was to add `FLAG_EXTRAS_REQUIRE` to the `<flags>` line also, then **EXTRA\_4**, **EXTRA\_11** & one random EXTRA would be enabled.

In this scenario it is also possible for the `FLAG_EXTRAS_REQUIRE` random extra to also be either `EXTRA_4` or `EXTRA_11` (rather than a different random extra) resulting in only `EXTRA_4` & `EXTRA_11` appearing some of the time.

`FLAG_EXTRAS_ALL` will overwrite this effects and will still force all extras to spawn.

For `FLAG_EXTRAS_RARE` see below.

### Preventing Specific Extras from Spawning

Short answer: There's no way to 100% prevent certain extras from spawning.

The closest possible solution is using `<extraIncludes>` and `<requiredExtras>` in combination with `FLAG_EXTRAS_RARE`. With this setup, you will get only `EXTRA_4` and `EXTRA_11`, but 10-15% of the time there will be a random extra in addition.

**Extra:** I'm not sure how much use this will be or whether it even applies to any cars other than the [Dodge Dart](https://www.gta5-mods.com/vehicles/68-dodge-dart-hemi-add-on-livery-animated-hq) I was testing but I'll mention it anyway.

I was able to enter '**FLAG\_EXTRAS\_RARE**' & '**FLAG\_EXTRAS\_SCRIPT**' in the '' line in combination with the two edits & was able to have EXTRA\_4 & EXTRA\_11 spawn all of the time but restict the random (\~10%>15% of the time) EXTRA to only be able to select EXTRA\_1, EXTRA\_2 or EXTRA\_3 (no other higher numbered random EXTRAS appeared in \~350 or so spawns). It may be pure luck GTA unicorns but it worked out rather well so try it out if you think that it might suit your need

## Type

The type flag defines what type of vehicle it is. This works in conjunction with the [txdRelationships](Vehicles.md#txd-relationships). You can set the following values within the type flag:

| Enum | Name                                  | Description                                                                                                                     |
| ---- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| -1   | VEHICLE\_TYPE\_NONE                   | Default/Invalid type.                                                                                                           |
| 0    | VEHICLE\_TYPE\_CAR                    | Cars. Used for all non-special land vehicles.                                                                                   |
| 1    | VEHICLE\_TYPE\_PLANE                  | Planes.                                                                                                                         |
| 2    | VEHICLE\_TYPE\_TRAILER                | Trailers. Allows vehicle to be towed by semi trucks.                                                                            |
| 3    | VEHICLE\_TYPE\_QUADBIKE               | Quadbikes. Essentially a bike with support for more than two wheels.                                                            |
| 4    | VEHICLE\_TYPE\_DRAFT                  | Horse carriages. Unused.                                                                                                        |
| 5    | VEHICLE\_TYPE\_SUBMARINECAR           | Submarine cars. Uses convertible roof functions to convert into submarine mode & back. Added in b467 (Xbox360/PS3 Update 1.11). |
| 6    | VEHICLE\_TYPE\_AMPHIBIOUS\_AUTOMOBILE | Amphibious automobiles. Essentially the Car vehicle type, but with the ability to traverse water as well. Added in b944.        |
| 7    | VEHICLE\_TYPE\_AMPHIBIOUS\_QUADBIKE   | Amphibious quadbikes. Similar to the above - a quadbike that can drive on water in addition to land. Added in b944.             |
| 8    | VEHICLE\_TYPE\_HELI                   | Helicopters.                                                                                                                    |
| 9    | VEHICLE\_TYPE\_BLIMP                  | Blimps. Essentially a helicopter that can propel forwards.                                                                      |
| 10   | VEHICLE\_TYPE\_AUTOGYRO               | Autogyro. Appears to be glitchy. Unused.                                                                                        |
| 11   | VEHICLE\_TYPE\_BIKE                   | Motorcycles.                                                                                                                    |
| 12   | VEHICLE\_TYPE\_BICYCLE                | Bicycles. Similar to motorcycles but with a different control set and ability to bunny hop/lean.                                |
| 13   | VEHICLE\_TYPE\_BOAT                   | Boats. A lot of vehicle features such as doors and weapons are disabled.                                                        |
| 14   | VEHICLE\_TYPE\_TRAIN                  | Trains. Hardcoded to prevent the player from pathfinding to enter the vehicle.                                                  |
| 15   | VEHICLE\_TYPE\_SUBMARINE              | Submarines. Allows controls for sumberging/surfacing.                                                                           |

## Plate Type

The plate type defines what type of plate the vehicle will have. E.G:

| Enum | Name                          | Description                                  |
| ---- | ----------------------------- | -------------------------------------------- |
| 0    | VPT\_FRONT\_AND\_BACK\_PLATES | Faces the back of the vehicle.               |
| 1    | VPT\_FRONT\_PLATES            | Faces the front of the vehicle.              |
| 2    | VPT\_BACK\_PLATES             | Faces the back of the vehicle.               |
| 3    | VPT\_NONE                     | Disables the category in Los Santos Customs. |

## Vehicle class

| Enum | Name                | Description                                                                                     |
| ---- | ------------------- | ----------------------------------------------------------------------------------------------- |
| 0    | VC\_COMPACT         | Compacts. Default class when the class is invalid or undefined.                                 |
| 1    | VC\_SEDAN           | Sedans.                                                                                         |
| 2    | VC\_SUV             | SUVs.                                                                                           |
| 3    | VC\_COUPE           | Coupes.                                                                                         |
| 4    | VC\_MUSCLE Muscle   | Hardcoded(since b1604) to enable the handbrake wheelie Advanced Flag on vehicles in this class. |
| 5    | VC\_SPORT\_CLASSIC  | Sports Classics.                                                                                |
| 6    | VC\_SPORT           | Sports.                                                                                         |
| 7    | VC\_SUPER           | Super.                                                                                          |
| 8    | VC\_MOTORCYCLE      | Motorcycles.                                                                                    |
| 9    | VC\_OFF\_ROAD       | Off-Road.                                                                                       |
| 10   | VC\_INDUSTRIAL      | Industrial.                                                                                     |
| 11   | VC\_UTILITY Utility | Also includes trailers.                                                                         |
| 12   | VC\_VAN             | Vans.                                                                                           |
| 13   | VC\_CYCLE           | Cycles.                                                                                         |
| 14   | VC\_BOAT            | Boats.                                                                                          |
| 15   | VC\_HELICOPTER      | Helicopters.                                                                                    |
| 16   | VC\_PLANE           | Planes.                                                                                         |
| 17   | VC\_SERVICE         | Service.                                                                                        |
| 18   | VC\_EMERGENCY       | Emergency.                                                                                      |
| 19   | VC\_MILITARY        | Military.                                                                                       |
| 20   | VC\_COMMERCIAL      | Commercial.                                                                                     |
| 21   | VC\_RAIL            | Trains.                                                                                         |
| 22   | VC\_OPEN\_WHEEL     | Open Wheel. Added in b1868.                                                                     |

## Trailers

The trailers flag defines what trailers can be attached to the vehicle. To ensure they fully work, you will need to either have an attach\_male or attach\_female bone in your vehicle.

```xml
<trailers>
  <Item>trailer_small</Item>
</trailers>
```

## TXD Relationships

This is used for linking a different .ytd to this vehicle to share textures. This is mainly used for dials.

```xml
 <txdRelationships>
   <Item>
     <parent>vehicles_feroci_interior</parent>
     <child>tow_truck</child>
   </Item>
 </txdRelationships>
```

The **parent** is the seperate .ytd that you are trying to import. The **child** is the .ytd that will have the other textures imported into and used within your vehicle.
