# carcols.meta

## Siren Sequencers

### Overview

Siren Sequencers are decimal values that represent 32-bit binary strings. The sequencers are converted to binary and used by emergency vehicles to represent the pattern of their flashing lights.

The patterns are expressed by using each digit of the binary value, one for each of 32 "ticks" (similar to frames) as an on or off value, and using a BPM value to determine the length of each tick.

The sequencer value in Carcols.meta is represented as a decimal value, but a decimal value is unreadable as a pattern to us mere humans, there for we must construct them in binary, and convert them for use.

You can use a converter such as this one to accomplish this. https://www.rapidtables.com/convert/number/binary-to-decimal.html

### Sequencer Example

Binary Sequence: 10101010101010101010101010101010

Decimal Value from Sequence: 2863311530

### Ways to Create Sequencers

There are 2 common methods of creating sequencers for patterns.

* Using [Siren Tool](https://dwnstr.com/sirentool)
* Torture (Straining your eyes in notepad)

## Siren Deltas

Siren deltas determine the rotation of the emissive mesh, and the environment lighting.

There are 8 commonly used delta values.

| Direction   | Side      | Degrees | Delta       |
| ----------- | --------- | ------- | ----------- |
| Front       | Front     | 0       | 0.00000000  |
| Right       | Passenger | 90      | -1.57079633 |
| Back        | Rear      | 180     | 3.14159265  |
| Left        | Driver    | -90     | 1.57079633  |
| Front Right | Passenger | -45     | -0.78539816 |
| Back Right  | Passenger | -135    | -2.35619449 |
| Back Left   | Driver    | 135     | 2.35619449  |
| Front Left  | Driver    | 45      | 0.78539816  |

_Delta Values Research from "EX.1" was originally found by Glitch Gamer on LCPDFR_

Pay attention to the fact that driver side is actually left and passenger side is actually right

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-7F9l4\_3ls4/4b5976cc8ed838dbf79a66e640e1ca82b9c85c5f254918fbd671f7a3c6e37d6a67a62cd4b65df69ee90dded72920d5a4f6f4fb32fd7580a2f6646da4a97e8d128f9ecc13d360849ef9f718fd025d108181debe018954bb28c04d53059dac3e154a0ede1b)

_Lightbar Featured in example "EX.2" is a "42" Code 3 Pursuit, Top View" taken from_ [_https://www.code3esg.com/us/en/products/Lightbars/dual-level/Pursuit_](https://www.code3esg.com/us/en/products/Lightbars/dual-level/Pursuit)

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-Uy1Gr9c8qa/bc5fd14e9657a648a3a8fb084d88a338f8ffc357fa24bb624d5d9119a13a3c885db963b646d56274ee83c0e0179a99aac822c3e87db51fae210e604cb8ac3a708755c4948d14405ce9c2a03d554defc9a97a40c96791ffc0772b9f7db943552647f6d6cf)

## Rotator Lights

> For information on rotators click through to the content [originally hosted here](https://www.modding-forum.com/guide/20-emergency-lights-rotator-lightbars-and-wig-wags/) by [Smanbg](https://www.modding-forum.com/user/915-smanbg/), [Cj24](https://www.modding-forum.com/user/2-cj24/) and [PNWParksFan](https://www.modding-forum.com/user/2672-pnwparksfan/). A small snippet is shown below.

> In comparison to your traditional strobe or LED lightbar with flashing lights, rotating lights require quite a different approach when using them, in particular, the sirens have to be covered, rather than scaled down. This guide is going to walk through the two common methods for rotator lightbars.
>
> First and foremost, the rotating modules have to be attached to the emissives, as that is what forms the siren - a rotating module and the emissive itself, and lastly - reset the local axis. After that is done, set your lightbar up as you would any lightbar, this also applies to any modules that are not rotatable.
>
> The next step on the list is covering the emissives. The rotator lightbar is a constant-spinning bar that relies on the rotation section of your siren in the carcols, which is also why it cannot be scaled and why the emissives should be covered when the lights are not on.

### Rotator Speed

It is possible to decrease the speed of rotators without decreasing the BPM and instead using the speed value and adjusted sequencers. In the rotation settings, syncToBpm must be turned off to be able to use the speed value. The exact speed value required depends on your BPM and the sequencer.

To slow down the lights, slower sequencers must be used, the more 1s are in the sequencer, the higher the speed. 1s must always be separated by an equal number of 0s. This results in the following sequencers and speed values:

![](https://i.imgur.com/GDZjwps.png)

The speed value must be set proportionally to the BPM and the sequencer. To calculate the required speed value, use the following formula:

![](https://i.imgur.com/hhlsHs7.png)

Good Rotary BPM is 120 BPM with Flash set to False

## Light Groups

_This section needs contributors_ _If you know anything about Light Groups, fork the repository to contribute!_

_Alternatively, join our Discord and contact us!_

## Light Colors

These values go here: `<color value="0xFF0000FF"/>`

> Data gathered by Zero parsed by, HairyMineFart, and Organized by Dawnstar
>
> Metallic Colors and Matte Colors have been excluded as they serve no purpose in siren colors.
>
> [Find the full list of colors here](https://www.se7ensins.com/forums/threads/vehicle-colors.1169166/)

**Most Used Colors**

| Color Name | Hex          | ARGB |
| ---------- | ------------ | ---- |
| Red        | `0xFFFF0000` |      |
| Blue       | `0xFF0000FF` |      |
| White      | `0xFFFFFFFF` |      |
| Amber      | `0xFFFFD700` |      |
| Yellow     | `0xFFFFFF00` |      |
| Green      |              |      |
| Purple     |              |      |

**Standard Colors**

| Color Name     | Hex           | ARGB               |
| -------------- | ------------- | ------------------ |
| BlackGraphite  | `0xFF0F0F0F`  | 255, 15, 15, 15    |
| ChocolateBrown | `0xFF3F2D18`  | 255, 63, 45, 24    |
| MetallicPurple | `0xFF320642`  | 255, 50, 6, 66     |
| HotPink        | `0xFFB01259`  | 255, 176, 18, 89   |
| FormulaRed     | `0xFF6B0000`  | 255, 107, 0, 0     |
| MetallicBlue   | `0xFF001B57`  | 255, 0, 27, 87     |
| UltraBlue      | `0xFF2070D8`  | 255, 32, 112, 216  |
| RacingGreen    | `0xFF00441B`  | 255, 0, 68, 27     |
| LimeGreen      | `0xFF418503`  | 255, 65, 133, 3    |
| RaceYellow     | `0xFFD9A600`  | 255, 217, 166, 0   |
| ClassicOrange  |  `0xFFBD4800` | 255, 189, 72, 0    |
| MetallicGold   | `0xFFAD7B47`  | 255, 173, 123, 71  |
| ClassicWhite   | `0xFFF0F0F0`  | 255, 240, 240, 240 |

**Classic Colors**

| Color Name      | Hex          | ARGB               |
| --------------- | ------------ | ------------------ |
| RED             | `0xFF690000` | 255, 105, 0, 0     |
| TORINO\_RED     | `0xFF8A0B00` | 255, 138, 11, 0    |
| FORMULA\_RED    | `0xFF6B0000` | 255, 107, 0, 0     |
| LAVA\_RED       | `0xFF6B0B00` | 255, 107, 11, 0    |
| BLAZE\_RED      | `0xFF611009` | 255, 97, 16, 9     |
| GRACE\_RED      | `0xFF4A0A0A` | 255, 74, 10, 10    |
| GARNET\_RED     | `0xFF470E0E` | 255, 71, 14, 14    |
| SUNSET\_RED     | `0xFF380C00` | 255, 56, 12, 0     |
| CABERNET\_RED   | `0xFF26030B` | 255, 38, 3, 11     |
| WINE\_RED       | `0xFF080000` | 255, 8, 0, 0       |
| CANDY\_RED      | `0xFF630012` | 255, 99, 0, 18     |
| HOT PINK        | `0xFFB01259` | 255, 176, 18, 89   |
| PINK            | `0xFF8F2F55` | 255, 143, 47, 85   |
| SALMON\_PINK    | `0xFFF69799` | 255, 246, 151, 153 |
| SUNRISE\_ORANGE | `0xFF802800` | 255, 128, 40, 0    |
| BRIGHT\_ORANGE  | `0xFFC26610` | 255, 194, 102, 16  |
| GOLD            | `0xFF5E5343` | 255, 94, 83, 67    |
| BRONZE          | `0xFF4A341B` | 255, 74, 52, 27    |
| YELLOW          | `0xFFF5890F` | 255, 245, 137, 15  |
| FLUR\_YELLOW    | `0xFFA2A827` | 255, 162, 168, 39  |
| DARK\_GREEN     | `0xFF001207` | 255, 0, 18, 7      |
| SEA\_GREEN      | `0xFF00211E` | 255, 0, 33, 30     |
| OLIVE\_GREEN    | `0xFF1F261E` | 255, 31, 38, 30    |
| BRIGHT\_GREEN   | `0xFF003805` | 255, 0, 56, 5      |
| PETROL\_GREEN   | `0xFF0B4145` | 255, 11, 65, 69    |
| LIME\_GREEN     | `0xFF568F00` | 255, 86, 143, 0    |
| MIDNIGHT\_BLUE  | `0xFF000108` | 255, 0, 1, 8       |
| GALAXY\_BLUE    | `0xFF000D14` | 255, 0, 13, 20     |
| DARK\_BLUE      | `0xFF001029` | 255, 0, 16, 41     |
| SAXON\_BLUE     | `0xFF1C2F4F` | 255, 28, 47, 79    |
| BLUE            | `0xFF001B57` | 255, 0, 27, 87     |
| MARINER\_BLUE   | `0xFF3B4E78` | 255, 59, 78, 120   |
| HARBOR\_BLUE    | `0xFF272D3B` | 255, 39, 45, 59    |
| DIAMOND\_BLUE   | `0xFF95B2DB` | 255, 149, 178, 219 |
| SURF\_BLUE      | `0xFF3E627A` | 255, 62, 98, 122   |
| NAUTICAL\_BLUE  | `0xFF1C3140` | 255, 28, 49, 64    |
| RACING\_BLUE    | `0xFF0E316D` | 255, 14, 49, 109   |
| LIGHT\_BLUE     | `0xFF395A83` | 255, 57, 90, 131   |
| PURPLE          | `0xFF1A182E` | 255, 26, 24, 46    |
| SPIN\_PURPLE    | `0xFF161629` | 255, 22, 22, 41    |
| MIGHT\_PURPLE   | `0xFF050008` | 255, 5, 0, 8       |
| BRIGHT\_PURPLE  | `0xFF320642` | 255, 50, 6, 66     |
| CREAM           | `0xFFCFC0A5` | 255, 207, 192, 165 |
| FROST\_WHITE    | `0xFFB3B9C9` | 255, 179, 185, 201 |

## Carcols Variables

### id

Value must match siren ID value in [Carvariations.meta](https://github.com/dwnstr/vehicle-docs/wiki/Carvariations) for the same vehicle.

Should be between 1000-40000 for most consistent results. Some numbers don't work inexplicably.

`<id value="2121"/>`

### timeMultiplier

Multiplies the BPM by the value specified.

`<timeMultiplier value="1.00000000"/>` Time x BPM (Ex. 1.0 x 600 = 600 BPM)

### Environment Lighting

![](https://codahosted.io/docs/IEZ3CWmYBK/blobs/bl-\_tjAgQWRtn/e151c016eeec2162f59c60f62d688f70c3bb7eb3094241fc667105f1ae358f236ee00911d3ed3adde344e4c6570158689af0224637472323f949a5df02253526b328f9860bdf2afc98b53ba952720860a41c4b0224a012bda264fbb3ca349aaecd9b1f22)

### lightFalloffMax

Controls the maximum distance that the light can reach. Works like a “power” value in the right conditions.

Value should be between 40 and 100 for best results.

`<lightFalloffMax value="100.00000000"/>`

### lightFalloffExponent

Controls how fast light reaches 0% after traveling away from source.

Value should ALWAYS be lower than FalloffMax!!!!!!

Value should be about 65% of FalloffMax for best results.

`<lightFalloffExponent value="100.00000000"/>`

### lightInnerConeAngle

Controls where light starts to fall off . Before this point, light will be at 100% horizontally/parallel to the source/inside to outside.

Value should ALWAYS be LOWER than LightOuterConeAngle!!!!

Value should be between 2 and 10 for best results

`<lightInnerConeAngle value="2.29061000"/>`

### lightOuterConeAngle

Controls the maximum width of the light cone, where light will be 0%

Value should be between 60 and 90 for best results

`<lightOuterConeAngle value="70.00000000"/>`

### lightOffset

`<lightOffset value="0.00000000"/>`

### textureName

Don't Change this! Specifies corona texture.

`<textureName>VehicleLight\_sirenlight</textureName>`

### sequencerBpm

`<sequencerBpm value="600"/>`

## Headlights and Taillights

When working with headlight and taillight sequencers you have to account for a delay for the fade in and out of the lights.

The default/standard sequencers that will give you the typical back and forth wig-wag effect are:

`10000000100000001000000010000000` and `00001000000010000000100000001000`

> If you have other good sequencers please contribute them!

### Headlights Example

```xml
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

## Custom Light IDs

```xml
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

## Siren Walkthrough

```xml
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

## Modkits

### Overview

The carcols controlls the modkits items that are on the vehicle. This includes things like aftermarket parts such as exhausts, trims, steering wheels etc. There are a lot of options avaliable to control what the modkits do.

#### Step 1

To keep the file formatted in a way that aligns with GTA, the modkit items should be put at the very beginning of the carcols file. Below the following lines:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<CVehicleModelInfoVarGlobal>
```

#### Step 2

On line 3 write:

```xml
<Kits>
  <Item>
    
  </Item>
</Kits>
```

This will tell the carcols we are starting the options for the modkits. Once you have this in place, on the line below the opening tag, we will now define the modkit name. This modkit name will allow the modkit set up that you will create be used anywhere as long as the vehicle & modkits are actively streamed.

#### Step 3

```xml
<kitName>myVehicle_modkit</kitName>
<id value="47543" />
<kitType>MKT_SPECIAL</kitType>
```

The modkit name can be anything. Normally, the name will end in \_modkit.

The ID value below it is very similar to the siren ID value. It uniquely identifies the modkit and makes sure the modkits are unique to the vehicle.

For the kitType there isn't a lot of information on what this does, therefore its best to leave it as MKT\_SPECIAL.

#### Step 4

Now we shall get into defining the individual modkit parts. Once you have exported the modkit items and have put them in your stream folder we can move on. First, you will need to define you are making visable mods by opening the following tags:

```xml
<visibleMods>

</visibleMods>
```

This will allow us to create individual items for each individual parts.

#### Step 5

Now we can define individual parts:

```xml
<Item>
  <modelName>MODKIT_NAME</modelName>
  <modShopLabel>MODKIT_SHOP_LABEL</modShopLabel>
  <linkedModels />
  <turnOffBones>
    <Item>misc_*</Item>
  </turnOffBones>
  <type>VMT_*</type>
  <bone>chassis</bone>
  <collisionBone>chassis</collisionBone>
  <cameraPos>VMCP_DEFAULT</cameraPos>
  <audioApply value="1.000000" />
  <weight value="20" />
  <turnOffExtra value="false" />
  <disableBonnetCamera value="false" />
  <allowBonnetSlide value="true" />
 </Item>
```

This is the meat and bones of the modkits.

| Tag Name            | What is is?                                                                                                                                                                                                                      | Accepted value type | Options                                                                            |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ---------------------------------------------------------------------------------- |
| modelName           | This is the name of the file in the stream folder.                                                                                                                                                                               | Name                | N/a                                                                                |
| modShopLabel        | This is the name that will show up in the customization screens. This is not really used in FiveM / GTA unless its being customized within a Los Santos Customs                                                                  | Name                | N/a                                                                                |
| linkedModels        | This links two modkits together allowing you to turn two or more things on when you turn on option on.                                                                                                                           | Items               | Items                                                                              |
| turnOffBones        | This allows you to turn off bones within the car. For example, turning off a mirror when replacing the option. This has to be a misc item.                                                                                       | Item                | Items                                                                              |
| type                | This defines the type of the modkit.                                                                                                                                                                                             | Name                | Find a list of types [here](https://gtamods.com/wiki/Carcols.ymt#type)             |
| bone                | This defines what bone the modkit is linked to. Chassis is standard if you are just adding something on.                                                                                                                         | String              | Find a list of bones [here](https://gtamods.com/wiki/Carcols.ymt#bone)             |
| collisionBone       | This defines what collision the modkit item will use. Once again, the chassis is normally standard but you can add different collisions.                                                                                         | Name                | Fin a lit of collisions [here](https://gtamods.com/wiki/Carcols.ymt#collisionBone) |
| cameraPos           | This allows you to change how the camera works with the modkit enables. This isn't normally changed from VMCP\_DEFAULT though.                                                                                                   | Name                | N/a                                                                                |
| audioApply          | This options isn't used very often alongside that there isn't a lot of information about it. It's best to leave the value at 1.                                                                                                  | Name                | N/a                                                                                |
| weight              | The weight is what is applied to the vehicle once the modkit item is on. For example, if you add a massive wing onto your car you can add a bit more weight to slow the vehicle down. This option directly affects the handling. | String              | N/a                                                                                |
| turnOffExtra        | There isn't a lot of information on this but I'd assume it links with the vehicles.meta turnOffExtra.                                                                                                                            | Boolean             | true / false                                                                       |
| disableBonnetCamera | This option turns off the bonnet camera off when the modkit item in enabled in game.                                                                                                                                             | Boolean             | true / false                                                                       |
| allowBonnetSlide    | This will stop players from sliding over the bonnet when the modkit item is enabled.                                                                                                                                             | Boolean             | true / false                                                                       |

#### Debugging modkits

If in the event your modkits do not work, here are some tips on how to fix it:

* Ensure your modkit ID at [Step 3](Carcols.md#step-3) is unique to the individual vehicle. The values can be from 0-1023 but some may overlap with other vehicles. Just keep changing the ID until your options show up for you. You do not need to restart the server to update this.
* The kiteName at [Step 3](Carcols.md#step-3) is not in the carvariations.meta.
* The .yft modkit is not in the stream folder. Ensure they are all in there.
* The modelName is not the same as the name of the .yft modkit in the stream folder. Ensure they are both the same.
