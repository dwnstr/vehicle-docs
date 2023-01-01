# handling.meta

The content of [Handling.meta](https://github.com/Flohhhhh/vehicle-docs/new/main/docs#handlingmeta) is excessively long and complex, we have excluded uncommon variables from our documentation. [Click here](https://forums.gta5-mods.com/topic/3842/tutorial-handling-meta) or [here](https://gtamods.com/wiki/Handling.meta) to view full documentation elsewhere.

> _Everything in the Handling Variables section was initially found and compiled by_ [_V4D3R_](https://forums.gta5-mods.com/user/v4d3r) _and can be found_ [_here on 5MODS_](https://forums.gta5-mods.com/topic/3842/tutorial-handling-meta)_. We have made edits to add more information._

## Handling Variables

### Physical Attributes

The following values represent a vehicle's physical traits

#### handlingName

Used by the Vehicles.meta file, to identify the handling line of the particular vehicle and bind them.

* A string with max length of 14 characters. The Vanilla vehicles use uppercase letters by default.
* Examples:
  * `ADDER`
  * `DINGHY`

#### fMass

The weight of the vehicle. Values should be given in Kilograms.

* Used when the vehicle collides with another vehicle or a non-static object.

#### fInitialDragCoeff

Sets the drag coefficient of the vehicle. Increase to simulate aerodynamic drag.

* Value: 10-120

#### vecCentreOfMassOffset

Shifts the center of gravity in meters from side to side.

Values:

(0 means that the center of gravity will be in the center of the vehicle.)

* X: -10.0 to 10.0. Positive values move the center of gravity **right**.
* Y: -10.0 to 10.0. Positive values move the center of gravity **forwards**.
* Z: -10.0 to 10.0. Positive values move the center of gravity **upwards**.

#### vecInertiaMultiplier

This value is resistance to rotation around each axis. Therefore, the x axis affects how quickly the car shifts forward and back under braking and acceleration and how it rotates end over end in the air, the y axis affects how quickly the car shifts from side to side when cornering (or in the air) and the z axis affects how the car rotates around the middle. Recommend keeping the z value above 2.0 unless you want arcade style immediate reaction to steering inputs

Value x: < 0.0 to > 4.0. Value y: < 0.0 to > 4.0. Value z: < 0.0 to > 4.0.

***

### Transmission

These values represent the vehicle's **straight line** performance.

#### fDriveBiasFront

This is used to determine whether a vehicle is front, rear, or four wheel drive.

_Thanks for_ [_@FoxtrotDelta_](https://forums.gta5-mods.com/uid/734) _for telling me about this value._

Values:

* 0.0 means that the vehicle is rear wheel drive.
* 1.0 means that the vehicle is front wheel drive.
* Any value between 0.01 and 0.99 is four wheel drive.
* 0.5 give both front and rear axles equal force, being the perfect 4WD.

#### nInitialDriveGears

Obviously, this line determines how many forward speeds/gears a vehicle's transmission contains.

Values: 1 or more.

#### fInitialDriveForce

This modifies the game's calculation of drive force (from the output of the transmission).

Values: 0.01 - 2.0 and _above_.

* 1.0 uses drive force calculation unmodified.
* Values less than 1.0 will in effect give the vehicle less drive force.
* Values greater than 1.0 will produce more drive force.

#### fDriveInertia

Describes how fast an engine will rev.

Values: 0.01 - 2.0.

* Default value is 1.0, (or no modification of drive intertia).
* Bigger values = quicker Redline (maximum engine speed)

#### fClutchChangeRateScaleUpShift

Clutch speed multiplier on **up** shifts.

* Bigger numbers = faster shifts.

#### fClutchChangeRateScaleDownShift

Clutch speed multiplier on **down** shifts.

* Bigger numbers = faster shifts

#### fInitialDriveMaxFlatVel

This determines the vehicle speed at redline in the top gear (_not the show_).

**Setting this value DOES NOT guarantee the vehicle will reach the given speed.**

* Multiply the number in the file by 0.82 to get the speed in mph.
* Multiply by 1.32 to get the speed in KPH.

Values: 0.00 and above.

#### fBrakeForce

Obvious one. Multiplies the game's calculation of deceleration.

* Bigger numbers = harder braking.

Values: 0.01 - 2.0 and above.

* 1.0 uses brake force calculation unmodified.

#### fBrakeBiasFront

This line controls the distribution of braking force between the front and rear axles.

Values:

Similar to `fDriveBiasFront`,

* 0.0 means the rear axle only receives brake force.
* 1.0 means the front axle only receives brake force.
* 0.5 gives both axles equal brake force.
* Values between 0.01 and 0.49 means the rear axle will receive more brake force.
* Values between 0.51 and 0.99 means the front axles will receive more brake force than the rear.

#### fHandbrakeForce

_Another_ obvious one. Braking power of the handbrake.

* Bigger numbers = harder braking.
* Values: 0.0 or above.

#### fSteeringLock

This multiplies the game's calculation of the **angle of the steer wheel** will turn while at full turn.

Steering lock is directly related to over/under-steer.

Values:

0.01 and above.

* Values between 0.1 - 0.2 will simulate a **long wheelbase**.
* Values around 0.75 and above will turn extremely fast. Higher values will cause the vehicle to spin out easily.

***

### Wheel Traction

The following attributes describe how the vehicle will behave when cornering, accelerating and decelerating etc.

#### fTractionCurveMax

Cornering grip of the vehicle as a multiplier of the tire surface friction.

#### fTractionCurveMin

Accelerating/braking grip of the vehicle as a multiplier of the tire surface friction.

#### fTractionCurveLateral

Shape of lateral traction curve.

#### fLowSpeedTractionLossMult

How much traction is reduced at low speed.

* 0.0 means normal traction. It affects mainly car burnout when pressing gas (W/UP).
* Decreasing value will cause less burnout, less sliding at start.
* Higher value will cause more burnout.

#### fCamberStiffness

This value modify the grip of the car when you're **drifting**.

* More than 0 make the car sliding on the same angle you're drifting.
* Less than 0 make your car oversteer
* **Not recommended to modify it for grip.**

#### fTractionBiasFront

Determines the distribution of traction from front to rear.

Values: 0.01 - 0.99.

* 0.01 = only rear axle has traction.
* 0.99 = only front axle has traction.
* 0.5 = both axles have equal traction.
* Entering a value of 0.0 or 1.0 causes the vehicle to have no traction.
*

#### fTractionLossMult

Affects how much grip is changed when driving on asphalt and mud

* Higher values make the car less responsive and prone to sliding.

***

### Suspension

#### fAntiRollBarForce

Larger Numbers = less body roll.

#### fAntiRollBarBiasFront

The bias between front and rear for the anti-roll bar

* 0 = front
* 1 = rear

#### fRollCentreHeightFront

* Larger Numbers = less rollovers.

Values: (Recommended) -0.15 to 0.15.

#### fRollCenterHeightRear

This value modify the weight transmission during an acceleration between the front and rear. _high positive value can make your car able to do wheelies._

* Larger Numbers = less rollovers.

Values: (Recommended) -0.15 to 0.15.

***

### Damage

#### fCollisionDamageMult

Multiplies the game's calculation of damage to the vehicle by collision.

#### fWeaponDamageMult

Multiplies the game's calculation of damage to the vehicle by weapons.

#### fDeformationDamageMult

Multiplies the game's calculation of deformation damage.

#### fEngineDamageMult

Multiplies the game's calculation of damage to the engine, causing explosion or engine failure.

* Values for the above four: 0.0 - 10.0.

#### fPetrolTankVolume

Amount of petrol that will leak after damaging a vehicle's tank.

#### fOilVolume

Amount of oil.

***

### Misc.

#### fMonetaryValue

Not sure.

#### strModelFlags

The following are written in HEX.

Rightmost digit is the first one.

Example:

```
<strModelFlags>20840018</strModelFlags>
```

| Digit | 1                   | 2                | 4                    | 8                            |
| ----- | ------------------- | ---------------- | -------------------- | ---------------------------- |
| 1st   | IS\_VAN             | IS\_BUS          | IS\_LOW              | IS\_BIG                      |
| 2nd   | ABS\_STD            | ABS\_OPTION      | ABS\_ALT\_STD        | ABS\_ALT\_OPTION             |
| 3rd   | NO\_DOORS           | TANDEM\_SEATS    | SIT\_IN\_BOAT        | HAS\_TRACKS                  |
| 4th   | NO\_EXHAUST         | DOUBLE\_EXHAUST  | NO1FPS\_LOOK\_BEHIND | CAN\_ENTER\_IF\_NO\_DOOR     |
| 5th   | AXLE\_F\_TORSION    | AXLE\_F\_SOLID   | AXLE\_F\_MCPHERSON   | ATTACH\_PED\_TO\_BODYSHELL   |
| 6th   | AXLE\_R\_TORSION    | AXLE\_R\_SOLID   | AXLE\_R\_MCPHERSON   | DONT\_FORCE\_GRND\_CLEARANCE |
| 7th   | DONT\_RENDER\_STEER | NO\_WHEEL\_BURST | INDESTRUCTIBLE       | DOUBLE\_FRONT\_WHEELS        |
| 8th   | RC                  | DOUBLE\_RWHEELS  | MF\_NO\_WHEEL\_BREAK | IS\_HATCHBACK                |

#### strHandlingFlags

The following are written in HEX.

Rightmost digit is the first one.

Example:

```
<strHandlingFlags>400000</strHandlingFlags>
```

| Digit | 1                         | 2                            | 4                                         | 8                  |
| ----- | ------------------------- | ---------------------------- | ----------------------------------------- | ------------------ |
| 1st   | SMOOTH\_COMPRESN          | REDUCED\_MOD\_MASS           |                                           |                    |
| 2nd   | NO\_HANDBRAKE             | STEER\_REARWHEELS            | HB\_REARWHEEL\_STEER                      | STEER\_ALL\_WHEELS |
| 3rd   | FREEWHEEL\_NO\_GAS        | NO\_REVERSE                  |                                           | STEER NO WHEELS    |
| 4th   | CVT                       | ALT\_EXT\_WHEEL\_BOUNDS\_BEH | DONT\_RAISE\_BOUNDS\_AT\_SPEED            |                    |
| 5th   | LESS\_SNOW\_SINK          | TYRES\_CAN\_CLI              |                                           |                    |
| 6th   | OFFROAD\_ABILITY          | OFFROAD\_ABILITY2            | HF\_TYRES\_RAISE\_SIDE\_IMPACT\_THRESHOLD |                    |
| 7th   | ENABLE\_LEAN              | HEAVYARMOUR                  |                                           | ARMOURED           |
| 8th   | SELF\_RIGHTING\_IN\_WATER | IMPROVED\_RIGHTING\_FORCE    |                                           |                    |

#### strDamageFlags

Mentioned doors will be unbreakable.

The following are written in HEX.

Rightmost digit is the first one.

Example:

```
<strDamageFlags>20</strDamageFlags>
```

| Digit | 1                         | 2                        | 4                                    | 5                                   |
| ----- | ------------------------- | ------------------------ | ------------------------------------ | ----------------------------------- |
| 1st   | DRIVER\_SIDE\_FRONT\_DOOR | DRIVER\_SIDE\_REAR\_DOOR | DRIVER\_PASSENGER\_SIDE\_FRONT\_DOOR | DRIVER\_PASSENGER\_SIDE\_REAR\_DOOR |
| 2st   | BONNET                    | BOOT                     |                                      |                                     |

#### aiHandling

There are 4 profiles, which AI use when driving the vehicle.

* AVERAGE
* CRAP
* TRUCK
* SPORTS\_CAR

***

The **SubHandlingData** section has been entirely excluded.\
This section covers less common variables and special vehicles like boats and bikes.\
[Click here](https://forums.gta5-mods.com/topic/3842/tutorial-handling-meta) or [here](https://gtamods.com/wiki/Handling.meta) to view full documentation by other authors.

***

## Handling File Example

```
<?xml version="1.0" encoding="UTF-8"?>
 <CHandlingDataMgr>
    <HandlingData>
    <Item type="CHandlingData">
      <handlingName>oycdefender</handlingName>
      <fMass value="2000.000000" />
      <fInitialDragCoeff value="3.800000" />
      <fPercentSubmerged value="85.000000" />
      <vecCentreOfMassOffset x="0.000000" y="0.010000" z="-0.1000000" />
      <vecInertiaMultiplier x="1.000000" y="1.600000" z="2.000000" />
      <fDriveBiasFront value="0.400000" />
      <nInitialDriveGears value="6" />
      <fInitialDriveForce value="0.300000" />
      <fDriveInertia value="1.000000" />
      <fClutchChangeRateScaleUpShift value="3.000000" />
      <fClutchChangeRateScaleDownShift value="3.000000" />
      <fInitialDriveMaxFlatVel value="175.000000" />
      <fBrakeForce value="1.500000" />
      <fBrakeBiasFront value="0.600000" />
      <fHandBrakeForce value="1.500000" />
      <fSteeringLock value="41.000000" />
      <fTractionCurveMax value="2.40000" />
      <fTractionCurveMin value="2.2700000" />
      <fTractionCurveLateral value="19.500000" />
      <fTractionSpringDeltaMax value="0.10000" />
      <fLowSpeedTractionLossMult value="0.700000" />
      <fCamberStiffnesss value="0.000000" />
      <fTractionBiasFront value="0.495000" />
      <fTractionLossMult value="0.600000" />
      <fSuspensionForce value="1.600000" />
      <fSuspensionCompDamp value="0.8000000" />
      <fSuspensionReboundDamp value="1.2500000" />
      <fSuspensionUpperLimit value="0.100000" />
      <fSuspensionLowerLimit value="-0.140000" />
      <fSuspensionRaise value="0.000000" />
      <fSuspensionBiasFront value="0.520000" />
      <fAntiRollBarForce value="0.800000" />
      <fAntiRollBarBiasFront value="0.500000" />
      <fRollCentreHeightFront value="0.220000" />
      <fRollCentreHeightRear value="0.220000" />
      <fCollisionDamageMult value="0.600000" />
      <fWeaponDamageMult value="1.000000" />
      <fDeformationDamageMult value="0.600000" />
      <fEngineDamageMult value="1.000000" />
      <fPetrolTankVolume value="65.000000" />
      <fOilVolume value="5.000000" />
      <fSeatOffsetDistX value="0.000000" />
      <fSeatOffsetDistY value="-0.100000" />
      <fSeatOffsetDistZ value="0.000000" />
      <nMonetaryValue value="50000" />
      <strModelFlags>440010</strModelFlags>
      <strHandlingFlags>20000</strHandlingFlags>
      <strDamageFlags>0</strDamageFlags>
      <AIHandling>AVERAGE</AIHandling>
      <SubHandlingData>
        <Item type="CCarHandlingData">
          <fBackEndPopUpCarImpulseMult value="0.100000" />
          <fBackEndPopUpBuildingImpulseMult value="0.030000" />
          <fBackEndPopUpMaxDeltaSpeed value="0.600000" />
        </Item>
        <Item type="NULL" />
        <Item type="NULL" />
      </SubHandlingData>
    </Item>
   </HandlingData>

</CHandlingDataMgr>
```
