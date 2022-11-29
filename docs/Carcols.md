# Carcols.meta

## Siren Sequencers

### Overview

Siren Sequencers are decimal values that represent 32-bit binary strings. The sequencers are converted to binary and used by emergency vehicles to represent the pattern of their flashing lights.

The patterns are expressed by using each digit of the binary value, one for each of 32 "ticks" (similar to frames) as an on or off value, and using a BPM value to determine the length of each tick.

The sequencer value in Carcols.meta is represented as a decimal value, but a decimal value is unreadable as a pattern to us mere humans, there for we must construct them in binary, and convert them for use.

You can use a converter such as this one to accomplish this.
https://www.rapidtables.com/convert/number/binary-to-decimal.html

### Sequencer Example

Binary Sequence: 10101010101010101010101010101010

Decimal Value from Sequence: 2863311530

### Ways to Create Sequencers
There are 2 common methods of creating sequencers for patterns.
*   Using [Siren Tool](https://dwnstr.com/sirentool)
*   Torture (Straining your eyes in nodepad)

# Siren Deltas

Siren deltas determine the rotation of the emissive mesh, and the environment lighting. 

There are 8 commonly used delta values.

| Direction | Side |  Degrees | Delta |
|---|---|---|---|
|Front | Front | 0 | 0.00000000|
|Right | Passenger | 90 | -1.57079633|
|Back | Rear | 180 | 3.14159265|
|Left | Driver | -90 | 1.57079633|
    
_Delta Values Research from "EX.1" was originally found by Glitch Gamer on LCPDFR_

  

Pay attention to the fact that driver side is actually left and passenger side is actually right

  

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-7F9l4_3ls4/4b5976cc8ed838dbf79a66e640e1ca82b9c85c5f254918fbd671f7a3c6e37d6a67a62cd4b65df69ee90dded72920d5a4f6f4fb32fd7580a2f6646da4a97e8d128f9ecc13d360849ef9f718fd025d108181debe018954bb28c04d53059dac3e154a0ede1b)

_Lightbar Featured in example "EX.2" is a "42" Code 3 Pursuit, Top View" taken from_ [_https://www.code3esg.com/us/en/products/Lightbars/dual-level/Pursuit_](https://www.code3esg.com/us/en/products/Lightbars/dual-level/Pursuit)

  

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-Uy1Gr9c8qa/bc5fd14e9657a648a3a8fb084d88a338f8ffc357fa24bb624d5d9119a13a3c885db963b646d56274ee83c0e0179a99aac822c3e87db51fae210e604cb8ac3a708755c4948d14405ce9c2a03d554defc9a97a40c96791ffc0772b9f7db943552647f6d6cf)

  

## Rotations

Good Rotary BPM is 120 BPM with Flash set to False

  

## Siren Grouping

  

## Light Colors
============

These values go here: `<color value="0xFF0000FF"/>`

> Data gathered by Zero parsed by, HairyMineFart, and Organized by Dawnstar
> 
> Metallic Colors and Matte Colors have been excluded as they serve no purpose in siren colors.
> 
> [Find the full list of colors here](https://www.se7ensins.com/forums/threads/vehicle-colors.1169166/)

  
### Most Used Colors

| Color Name | Hex | RGB |
| --- | --- | --- |
| Red | `0xFFFF0000` |  |
| Blue | `0xFF0000FF` |  |
| White | `0xFFFFFFFF` |  |
| Amber | `0xFFFFD700` |  |
| Yellow | `0xFFFFFF00` |  |
| Green |  |  |
| Purple |  |  |

  

### Standard Colors

> Note: I have no idea why these RGB values seem to be RGBA values with arbitrary A values. Luckily, we don't really need them.
> 

| Color Name | Hex | RGB |
| ---| ---| --- |
| BlackGraphite | `0xFF0F0F0F` | 255, 15, 15, 15 |
| ChocolateBrown | `0xFF3F2D18` | 255, 63, 45, 24 |
| MetallicPurple | `0xFF320642` | 255, 50, 6, 66 |
| HotPink | `0xFFB01259` | 255, 176, 18, 89 |
| FormulaRed | `0xFF6B0000` | 255, 107, 0, 0 |
| MetallicBlue | `0xFF001B57` | 255, 0, 27, 87 |
| UltraBlue | `0xFF2070D8` | 255, 32, 112, 216 |
| RacingGreen | `0xFF00441B` | 255, 0, 68, 27 |
| LimeGreen | `0xFF418503` | 255, 65, 133, 3 |
| RaceYellow | `0xFFD9A600` | 255, 217, 166, 0 |
| ClassicOrange | `0xFFBD4800` | 255, 189, 72, 0 |
| MetallicGold | `0xFFAD7B47` | 255, 173, 123, 71 |
| ClassicWhite | `0xFFF0F0F0` | 255, 240, 240, 240 |

### Classic Colors
| Color Name | Hex | RGB |
|---|---|---|
| RED | 0xFF690000 | 255, 105, 0, 0 |
| TORINO_RED | 0xFF8A0B00 | 255, 138, 11, 0 |
| FORMULA_RED | 0xFF6B0000 | 255, 107, 0, 0 |
| LAVA_RED | 0xFF6B0B00 | 255, 107, 11, 0 |
| BLAZE_RED | 0xFF611009 | 255, 97, 16, 9 |
| GRACE_RED | 0xFF4A0A0A | 255, 74, 10, 10 |
| GARNET_RED | 0xFF470E0E | 255, 71, 14, 14 |
| SUNSET_RED | 0xFF380C00 | 255, 56, 12, 0 |
| CABERNET_RED | 0xFF26030B | 255, 38, 3, 11 |
| WINE_RED | 0xFF080000 | 255, 8, 0, 0 |
| CANDY_RED | 0xFF630012 | 255, 99, 0, 18 |
| HOT PINK | 0xFFB01259 | 255, 176, 18, 89 |
| PINK | 0xFF8F2F55 | 255, 143, 47, 85 |
| SALMON_PINK | 0xFFF69799 | 255, 246, 151, 153 |
| SUNRISE_ORANGE | 0xFF802800 | 255, 128, 40, 0 |
| BRIGHT_ORANGE | 0xFFC26610 | 255, 194, 102, 16 |
| GOLD | 0xFF5E5343 | 255, 94, 83, 67 |
| BRONZE | 0xFF4A341B | 255, 74, 52, 27 |
| YELLOW | 0xFFF5890F | 255, 245, 137, 15 |
| FLUR_YELLOW | 0xFFA2A827 | 255, 162, 168, 39 |
| DARK_GREEN | 0xFF001207 | 255, 0, 18, 7 |
| SEA_GREEN | 0xFF00211E | 255, 0, 33, 30 |
| OLIVE_GREEN | 0xFF1F261E | 255, 31, 38, 30 |
| BRIGHT_GREEN | 0xFF003805 | 255, 0, 56, 5 |
| PETROL_GREEN | 0xFF0B4145 | 255, 11, 65, 69 |
| LIME_GREEN | 0xFF568F00 | 255, 86, 143, 0 |
| MIDNIGHT_BLUE | 0xFF000108 | 255, 0, 1, 8 |
| GALAXY_BLUE | 0xFF000D14 | 255, 0, 13, 20 |
| DARK_BLUE | 0xFF001029 | 255, 0, 16, 41 |
| SAXON_BLUE | 0xFF1C2F4F | 255, 28, 47, 79 |
| BLUE | 0xFF001B57 | 255, 0, 27, 87 |
| MARINER_BLUE | 0xFF3B4E78 | 255, 59, 78, 120 |
| HARBOR_BLUE | 0xFF272D3B | 255, 39, 45, 59 |
| DIAMOND_BLUE | 0xFF95B2DB | 255, 149, 178, 219 |
| SURF_BLUE | 0xFF3E627A | 255, 62, 98, 122 |
| NAUTICAL_BLUE | 0xFF1C3140 | 255, 28, 49, 64 |
| RACING_BLUE | 0xFF0E316D | 255, 14, 49, 109 |
| LIGHT_BLUE | 0xFF395A83 | 255, 57, 90, 131 |
| PURPLE | 0xFF1A182E | 255, 26, 24, 46 |
| SPIN_PURPLE | 0xFF161629 | 255, 22, 22, 41 |
| MIGHT_PURPLE | 0xFF050008 | 255, 5, 0, 8 |
| BRIGHT_PURPLE | 0xFF320642 | 255, 50, 6, 66 |
| CREAM | 0xFFCFC0A5 | 255, 207, 192, 165 |
| FROST_WHITE | 0xFFB3B9C9 | 255, 179, 185, 201 |

## Values

  

### `id value=`

Value must match siren ID value in [Carvariations.meta](https://github.com/dwnstr/vehicle-docs/wiki/Carvariations) for the same vehicle.

Should be between 1000-40000 for most consistent results. Some numbers don't work inexplicably.

  

ex. <id value="2121"/>

### `timeMultiplier value=`

Multiplies the BPM by the value specified.

  

ex.  <timeMultiplier value="1.00000000"/> Time x BPM (Ex. 1.0 x 600 = 600 BPM)

  

### Environment Lighting

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-_tjAgQWRtn/e151c016eeec2162f59c60f62d688f70c3bb7eb3094241fc667105f1ae358f236ee00911d3ed3adde344e4c6570158689af0224637472323f949a5df02253526b328f9860bdf2afc98b53ba952720860a41c4b0224a012bda264fbb3ca349aaecd9b1f22)

  

### ``lightFalloffMax value=``

Controls the maximum distance that the light can reach. Works like a “power” value in the right conditions.

Value should be between 40 and 100 for best results.

``<lightFalloffMax value="100.00000000"/>``

### ``lightFalloffExponent value=``

Controls how fast light reaches 0% after traveling away from source.

Value should ALWAYS be lower than FalloffMax!!!!!!

Value should be about 65% of FalloffMax for best results.

  

```plain
<lightFalloffExponent value="100.00000000"/>
```

### `lightInnerConeAngle value=`

  

Controls where light starts to fall off . Before this point, light will be at 100% horizontally/parallel to the source/inside to outside.

Value should ALWAYS be LOWER than LightOuterConeAngle!!!!

Value should be between 2 and 10 for best results.

  

     <lightInnerConeAngle value="2.29061000"/> (in degrees)       --Values that effect Environment Lighting

### `lightOuterConeAngle value=`

Controls the maximum width of the light cone, where light will be 0%

Value should be between 60 and 90 for best results

     <lightOuterConeAngle value="70.00000000"/> (in degrees)

### `lightOffset value=`

     <lightOffset value="0.00000000"/>

  

Texture Name
------------

### `textureName`

Don't Change this! Specifies corona texture.

ex. <textureName>VehicleLight\_sirenlight</textureName>

  

     <sequencerBpm value="600"/> --Light Flash Frequency

  

Headlights and Taillights
-------------------------

```sql
      <leftHeadLight>
        <sequencer value="0"/>
      </leftHeadLight>
      <rightHeadLight>
        <sequencer value="0"/>
      </rightHeadLight> --This section controls headlight and Tailight Flashes, 
      <leftTailLight> -- In Binary make sure itflashes NO MORE than 4 times in a row!
        <sequencer value="0"/>      
      </leftTailLight> --Ex. 10101010000000001010101000000000 
      <rightTailLight> --00000000101010100000000010101010
        <sequencer value="0"/>
      </rightTailLight>
      <leftHeadLightMultiples value="1"/> --How many times the Corona to flash within the BPM
      <rightHeadLightMultiples value="1"/> --For example BPM is 600 if you change the Multiple to 5
      <leftTailLightMultiples value="1"/> --It would be 600*5 = 3000 Corona Flashes
      <rightTailLightMultiples value="1"/>   --(TOO EXCESSIVE!!)
      <useRealLights value="true"/>     --If you want the Flashes to actually use the Headlights
```

  

Custom Light IDs
================

```plain
<CVehicleModelInfoVarGlobal>
      <Kits />
    <Lights>
    <Item>
      <id value="Custom Light Settings"/>
_      
<indicator>                                                                         The main section of your indicators
        <intensity value="0.37500000"/>                           Intensity change, how bright, and strong the light will be.
        <falloffMax value="2.50000000"/>
        <falloffExponent value="8.00000000"/>
        <innerConeAngle value="45.00000000"/>
        <outerConeAngle value="90.00000000"/>
        <emmissiveBoost value="false"/> It will affect the brightness multiplier, color and intensity of the corona. Its like Emissive Multiplier 
        <color value="0xFFFF8000"/>
        <textureName/>
        <mirrorTexture value="true"/>
      </indicator>
_
      <rearIndicatorCorona>
        <size value="0.70000000"/>                              This will set the size of your corona when you are near the vehicle 
        <size_far value="7.00000000"/>
        <intensity value="2.00000000"/>                                       This will change the corona itensity
        <intensity_far value="9.00000000"/>
        <color value="0x00000000"/>                                                     Color of the Corona
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>                               This set the bias of the dist Between Coronas positioning. Changing this, is good for fine tuning
        <pullCoronaIn value="false"/>                                               Allows to have 2 Coronas at the same position.
      </rearIndicatorCorona>
_
      <frontIndicatorCorona>
        <size value="0.00000000"/>
        <size_far value="0.00000000"/>
        <intensity value="0.00000000"/>
        <intensity_far value="0.00000000"/>
        <color value="0x00000000"/>
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>
        <pullCoronaIn value="false"/>
      </frontIndicatorCorona>
_
      <tailLight>
        <intensity value="0.25000000"/>
        <falloffMax value="4.00000000"/>
        <falloffExponent value="8.00000000"/>
        <innerConeAngle value="45.00000000"/>
        <outerConeAngle value="90.00000000"/>
        <emmissiveBoost value="false"/>
        <color value="0xFFFF0000"/>
        <textureName/>
        <mirrorTexture value="true"/>
      </tailLight>
_
     <tailLightCorona>
        <size value="0.70000000"/>
        <size_far value="7.00000000"/>
        <intensity value="2.00000000"/>
        <intensity_far value="9.00000000"/>
        <color value="0xFFFF0F05"/>
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>
        <pullCoronaIn value="false"/>
      </tailLightCorona>
_
      <tailLightMiddleCorona>
        <size value="0.00000000"/>
        <size_far value="0.00000000"/>
        <intensity value="0.00000000"/>
        <intensity_far value="0.00000000"/>
        <color value="0x00000000"/>
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>
        <pullCoronaIn value="false"/>
      </tailLightMiddleCorona>
_
      <headLight>
        <intensity value="2.00000000"/>
        <falloffMax value="16.00000000"/>
        <falloffExponent value="128.00000000"/>
        <innerConeAngle value="22.68000000"/>
        <outerConeAngle value="37.53000000"/>
        <emmissiveBoost value="false"/>
        <color value="0xFFFFFFCC"/>
        <textureName>VehicleLight_misc_squarelight</textureName>
        <mirrorTexture value="false"/>
      </headLight>
_
      <headLightCorona>
        <size value="0.10000000"/>
        <size_far value="7.00000000"/>
        <intensity value="5.00000000"/>
        <intensity_far value="10.00000000"/>
        <color value="0xFFFFFFFF"/>
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>
        <pullCoronaIn value="false"/>
      </headLightCorona>
_
      <reversingLight>
        <intensity value="0.50000000"/>
        <falloffMax value="4.00000000"/>
        <falloffExponent value="32.00000000"/>
        <innerConeAngle value="45.00000000"/>
        <outerConeAngle value="90.00000000"/>
        <emmissiveBoost value="false"/>
        <color value="0xFFFFFFFF"/>
        <textureName/>
        <mirrorTexture value="true"/>
      </reversingLight>
_
      <reversingLightCorona>
        <size value="0.80000000"/>
        <size_far value="2.00000000"/>
        <intensity value="1.50000000"/>
        <intensity_far value="1.00000000"/>
        <color value="0x00F7F7F7"/>
        <numCoronas value="1"/>
        <distBetweenCoronas value="128"/>
        <distBetweenCoronas_far value="255"/>
        <xRotation value="0.00000000"/>
        <yRotation value="0.00000000"/>
        <zRotation value="0.00000000"/>
        <zBias value="0.25000000"/>
        <pullCoronaIn value="false"/>
      </reversingLightCorona>
_
      <name>Custom Lights 911</name></Item> Add this to the Carcols 
    </Lights>
</CVehicleModelInfoVarGlobal>
   
<name>Custom light name</name> - Add this to the Carcols 

<textureName>VehicleLight_car_LED1</textureName>
<textureName>VehicleLight_car_LED2</textureName>
<textureName>VehicleLight_car_standardmodern</textureName>
<textureName>VehicleLight_car_oldsquare</textureName>
<textureName>VehicleLight_car_antique</textureName>
<textureName>VehicleLight_car_standard70s</textureName>
<textureName>VehicleLight_car_utility</textureName>
<textureName>VehicleLight_bike_sport</textureName>
<textureName>VehicleLight_bike_sport</textureName>
<textureName>VehicleLight_bike_round</textureName>
<textureName>VehicleLight_bicycle</textureName>
<textureName>VehicleLight_misc_squarelight</textureName>
<textureName>VehicleLight_misc_searchlight</textureName>
<textureName>VehicleLight_misc_searchlight2</textureName>
<textureName>VehicleLight_sirenlight</textureName>
```

Siren Walkthrough
=================

  

```sql
<Item> --siren#
  <rotation>
    <delta value="0.000000"/> --Rotation of Emissive
    <start value="0.000000"/>
    <speed value="1.500000"/> --Speed of rotation
    <sequencer value="40285525"/> --Light Flash, Sequencer is Decimal of Binary value
    <multiples value="1"/> --Number of time corona slashes in BPM Sequence
    <direction value="false"/> (Not Sure)
    <syncToBpm value="true"/> --If True Sync to Pre-Siren or Light Group (Under Color)
  </rotation>

  <flashiness>
    <delta value="0.000000"/> --Rotation of ENV Lighting
    <start value="4.71238900"/>
    <speed value="1.000000"/>
    <sequencer value="40285525"/> --Light Flash, Sequencer is Decimal of Binary value
    <multiples value="1"/> --Number of time ENV Light flashes in BPM Sequence
    <direction value="true"/> (Not Sure)
    <syncToBpm value="true"/> --If True Sync to Pre-Siren
   </flashiness>

   <corona>
    <intensity value="0.000000001"/>
    <size value="1.10000000"/>   -Corona Values
    <pull value="0.20000000"/>
    <faceCamera value="false"/> --If set to True Corona will follow Camera, regardless of rotation
   </corona>

   <color value="0xFF0000FF"/> --Color of the Corona and ENV Lighting
   <intensity value="0.50000"/> --Intensity of the light color
   <lightGroup value="0"/> --SET LIGHTGROUP HERE
   <rotate value="false"/>
   <scale value="true"/   --If True Light will scale up to value
   <scaleFactor value="10"/> --Value light will scale to
   <flash value="true"/> --If False Light will Rotate 
   <light value="true"/> --If True Light will emit from the corona
   <spotLight value="true"/> --If True = 180 Degrees | False = Light angle set in Pre-Siren
   <castShadows value="false"/> --If True = Light will cast shadows of Player/Car
</Item>
```
