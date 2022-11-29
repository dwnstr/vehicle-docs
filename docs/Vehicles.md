# Vehicles.meta

Overview
========

Extras
======

Most of the content here was originally provided by [a63nt-5m1th](https://forums.gta5-mods.com/user/a63nt-5m1th) at the link below!

  

_Source:_ [_\[ Tutorial \] How to make specific vehicle EXTRAS appear on a vehicle EVERY spawn. | GTA5-Mods.com Forums_](https://forums.gta5-mods.com/topic/19786/tutorial-how-to-make-specific-vehicle-extras-appear-on-a-vehicle-every-spawn)

  

Flags
-----

*   **FLAG\_EXTRAS\_REQUIRE -** Always spawns with EXACTLY 1 RANDOM extra.
*   **FLAG\_EXTRAS\_ALL -** Always spawns with ALL extras
*   **FLAG\_EXTRAS\_RARE -** Spawns with only one random extra but ONLY ~15% of the time. (85% of the time, no extras will spawn)

  

Forcing Specific Extras
-----------------------

To make this happen you need to make two small edits to your vehicle in '**vehicles.meta**'.

  

For this example I'm going to force EXTRA\_4 & EXTRA\_11 to always spawn but you can just change these values to the extras you want to have spawn (...'>EXTRA\_3 EXTRA\_5 EXTRA\_10<'... etc for example. You can put as many extras as you like in the lines).

As with the above flags the EXTRAS (below) are separated with a space.

  

1.  Find the line: `<extraIncludes />`
2.  Change it to this format:

```xml
      <extraIncludes>
```

4.  Find the line: `<requiredExtras />`
5.  Change it to this format:

```plain
      <requiredExtras>EXTRA_4 EXTRA_11</requiredExtras>
```

  

That's it. Now every time the vehicle spawns EXTRA\_4 & EXTRA\_11 will ALWAYS spawn also.

  

If either of these edits are missing or incorrect the game will go back to default random extra spawning. Both are required to make it work.

  

**HOW THESE EDITS WORK IN COMBINATION WITH FLAGS:**

  

These two settings above work in combination with any flags set in the '**<flags>**' line.

For example if I was to add '**FLAG\_EXTRAS\_REQUIRE**' to the '**<flags>**' line also, then EXTRA\_4, EXTRA\_11 & one random EXTRA would spawn all together on the vehicle.

  

In this scenario it is also possible for the **FLAG\_EXTRAS\_REQUIRE**'s random extra to also be either EXTRA\_4 or EXTRA\_11 (rather than a different random extra) resulting in only EXTRA\_4 & EXTRA\_11 appearing some of the time.

  

If the '**FLAG\_EXTRAS\_ALL**' flag is used in combination with these edits it will override them & force ALL EXTRAS to appear ALL of the time.

  

For '**FLAG\_EXTRAS\_RARE**' see below.

  

**STOPPING SPECIFIC EXTRAS FROM SPAWNING:**

  

There doesn't seem to be any easy way of doing this in '**vehicles.meta**'. The best I found was using the '**extraIncludes**' & '**requiredExtras**' edits above in combination with '**FLAG\_EXTRAS\_RARE**' so that ~85%>90% of the time the vehicle spawns with only EXTRA\_4 & EXTRA\_11 & ~10%>15% of the time there is an additional random extra as well.

  

**Extra:** I'm not sure how much use this will be or whether it even applies to any cars other than the [Dodge Dart](https://www.gta5-mods.com/vehicles/68-dodge-dart-hemi-add-on-livery-animated-hq) I was testing but I'll mention it anyway.

  

I was able to enter '**FLAG\_EXTRAS\_RARE**' & '**FLAG\_EXTRAS\_SCRIPT**' in the '**<flags>**' line in combination with the two edits & was able to have EXTRA\_4 & EXTRA\_11 spawn all of the time but restict the random (~10%>15% of the time) EXTRA to only be able to select EXTRA\_1, EXTRA\_2 or EXTRA\_3 (no other higher numbered random EXTRAS appeared in ~350 or so spawns). It may be pure luck GTA unicorns but it worked out rather well so try it out if you think that it might suit your need
