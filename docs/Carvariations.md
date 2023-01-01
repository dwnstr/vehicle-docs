# carvariations.meta

**THIS PAGE IS HEAVILY WIP, EXCUSE THE APPEARANCE**

We just dumped documentation here for now, and are refining it slowly.

## _Overview_

```xml
<Item>
  <modelName>Model</modelName> <!-- This needs to be the Model/Stream Name of the Vehicle -->   
  <colors> <!--Color Codes here: https://imgur.com/a/F4Ptk -->
    <Item> <!--Each line is a Separate part of the vehicle that will be colored -->
      <indices content="char_array"> <!--indices are color codes -->
        134 <!--Primary Color -->
        134 <!--Secondary Color -->
        134 <!--Rim Color -->
        156 <!--Not Sure yet -->
        156 <!--Not Sure yet -->
        156 <!--156 is Default Color Code (Grey) -->
       </indices>  <!--These color codes set are just the color that the vehicle WILL spawn in as -->
       <liveries>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>       <!-- 12 livery slots, if you set one to "True" it is possible the car will spawn with that Livery -->
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
         <Item value="false"/>
       </liveries>
    </Item>
  </colors>
  <kits> <!-- These are modkits. Use this for a default modkit and for wheels to work. Remove section for Police Vehicles -->
    <Item>0_default_modkit</Item>
   </kits>
   <windowsWithExposedEdges/> 
   <plateProbabilities>
     <Probabilities> <!-- This controls what plate is used when spawned-->
       <Item>
         <Name>Police guv plate</Name> <!--(Idk the other plate names lol)-->
         <Value value="100"/> <!--(DO NOT CHANGE THIS VALE)-->
       </Item>
     </Probabilities>
   </plateProbabilities>
   <lightSettings value="0"/> <!--This controls the Light ID. Default is 0.-->
   <sirenSettings value="2121"/> <!-- This needs to match up with the Carcols ID that you created for the vehicle. -->
</Item>
```

## Vehicle Colors

There are ONLY 160 Primary colors that the vehicle can spawn in as, All colors can be found here: [https://imgur.com/a/F4Ptk](https://imgur.com/a/F4Ptk)

_(We are unsure of the author, If you know who took the time to discover this please let us know!)_

```xml
<indices content="char_array"> <!--indices are color codes -->
  134 <!--Primary Color -->
  134 <!--Secondary Color -->
  134 <!--Rim Color -->
  156 <!--Not Sure yet -->
  156 <!--Not Sure yet -->
  156 <!--156 is Default Color Code (Grey) -->
</indices>  <!--These color codes set are just the color that the vehicle WILL spawn in as -->
<liveries>
  <Item value="true"/>
  <Item value="true"/> <!-- 12 livery slots, if you set one to "True" it is possible the car will spawn with that Livery -->
  <Item value="false"/> <!-- ONLY SET VALUE TO TRUE IF LIVERY SLOT IS BEING USED, Can potentially crash if no Livery -->
  <Item value="false"/> <!-- Keep in mind this is JUST what the vehicle SPAWNS with -->
  <Item value="false"/>       
  <Item value="false"/>
  <Item value="false"/>
  <Item value="false"/>
  <Item value="false"/>
  <Item value="false"/>
  <Item value="false"/>
  <Item value="false"/>
</liveries>
```

Some basic color codes are below, to change the color simply replace the 3 digit number

`<!-- Black - 000 -->`

`<!-- Red - 027 -->`

`<!-- Blue - 064 -->`

`<!-- Pure White - 134 -->`

`<!-- Default Alloy - 156 -->`

## Light IDs

_Originally found by MrGTAmodsgerman at_ [_https://gtaforums.com/_](https://gtaforums.com/)

`0`

Headlights = default light(White) with extralights

Taillights = modern taillight coronas (bright red)

Brakelights = modern brakelight (bright red)

Indicators = yellow (default) with corona

Reversinglight = white (default)

`1`

Headlights = default light(White) without extralights

Taillights = modern taillight coronas (bright red)

Brakelights = modern brakelight (bright red)

Indicators = yellow (default) with Corona

Reversinglight = white (default)

`2`

Headlights = oldschool(Yellow) with extralights

Taillights = olschool taillight coronas (bright red)

Brakelights = oldschool brakelight (bright red)

Indicators = yellow (default) with Corona

Reversinglight = white (default)

`3`

Headlights = Extreem bright and wide (White) with extralights

Taillights = WITHOUT CORONA

Brakelights = WITHOUT CORONA

Indicators = WITHOUT CORONA

Reversinglight = default (White)

`4`

Headlights = default light(white) with small range and with extralights

Taillights = modern taillight coronas (bright red)

Brakelights = modern brakelight (bright red)

Indicators = yellow (default) with corona

Reversinglight = white (default)

`5`

Headlights = small (White) with extralights

Taillights = WORK AS Headlight (white) with white corona

Brakelights = WORK AS Headlight (white)

Indicators = WORK AS Headlight (white)

Reversinglight = default (White)

`6`

Headlights = xeon light(Blue) with extralights

Taillights = modern taillight with 5 coronas (bright red)

Brakelights = modern brakelight with 5 coronas(bright red)

Indicators = yellow (default) with corona

Reversinglight = white (default)

`7`

Headlights = xeon light(Blue) with extralights

Taillights = modern taillight with 3 coronas (bright red)

Brakelights = modern brakelight with 3 coronas(bright red)

Indicators = yellow (default) with corona

Reversinglight = white (default)

`8`

Headlights = xeon light(Blue) with 2 coronas and extralights

Taillights = modern taillight with 3 coronas (bright red)

Brakelights = modern brakelight with 3 coronas(bright red)

Indicators = yellow (default) with corona

Reversinglight = white (default)

## Custom Light IDs

_Learn how to setup your own Light settings without using basic items, you will have the ability to move the corona and more!_

The definitions for Custom Light IDs go in Carcols.meta ([https://doc.clickup.com/d/h/841f5-35/66cbfa324380b75/841f5-49](https://doc.clickup.com/d/h/841f5-35/66cbfa324380b75/841f5-49))

View that page for more info.

## Siren IDs

Siren IDs are needed to tell the vehicle what lights are supposed to flash at which times. There are 22 Base game siren ids while there are also over 40,000 Custom ids we can choose from. The siren id must match the carcol id otherwise the lights will NOT work.
