---
description: >-
  Documentation for default stages, which allow you to set certain stages on or
  off when lights are activated.
---

# Default Stages

## Overview

Default stages allows you to specify stages created as [stage buttons](stage-controls.md) that will either be enabled or disabled when the lighting is activated on the vehicle.

{% embed url="https://medal.tv/games/gta-v/clips/XYMFe22wM5bvB/un35AqpHzGNk?invite=cr-MSxrY0MsMTc0MDk3ODg4LA" %}

As you can see in the video, "STAGE 2" is being manually disabled, but always turns on when vehicle lighting is activated!

## Example Usage

Say I have a button to activate front lighting on my vehicle:

<pre class="language-lua"><code class="lang-lua">{
    label = "FRONT", 
<strong>    key = 1, 
</strong>    extra = 2, 
    linkedExtras = {4}, 
    oppositeExtras = {}, 
    offExtras = {}
}
</code></pre>

I want my front lighting to always be enabled when the lights are activated. I will add this stage to the default stages by adding the key, 1, to `enableKeys`:\


<pre class="language-lua"><code class="lang-lua">defaultStages = {
    useDefaults = false,
<strong>    enableKeys = {1},
</strong>    disableKeys = {}
}
</code></pre>

Now it will be as if the player pressed NUM 1 to activate the stage every time the lights turn on resulting in the stage always being active when lights are first activated.

## Conflicts

{% hint style="warning" %}
If 2 stages specified in defaultExtras both reference the same extra as linkedExtras, oppositeExtras, or offExtras, the later key will override the earlier ones!
{% endhint %}

Following the above example, if we had our "FRONT" lighting stage which references Extra 4 as a linkedExtra as well as another stage called "TA" which references Extra 4 as an offExtra, we will run into a conflict.

<pre class="language-lua"><code class="lang-lua">{
    label = "FRONT", 
    key = 1, 
    extra = 2, 
<strong>    linkedExtras = {4}, 
</strong>    oppositeExtras = {}, 
    offExtras = {}
},
{
    label = "TA", 
    key = 2, 
    extra = 3, 
    linkedExtras = {}, 
    oppositeExtras = {}, 
<strong>    offExtras = {4}
</strong>}
</code></pre>

Later keys trigger after earlier ones, so if we listed "FRONT" as a defaultStage and then "TA", the result would be that extra 4 is off.

<pre class="language-lua"><code class="lang-lua">defaultStages = {
    useDefaults = false,
<strong>    enableKeys = {1, 2},
</strong>    disableKeys = {}
}
</code></pre>

If we swap the order, the result would be that extra 4 is on.

<pre class="language-lua"><code class="lang-lua">defaultStages = {
    useDefaults = false,
<strong>    enableKeys = {2, 1},
</strong>    disableKeys = {}
}
</code></pre>

Keep this in mind when using Default Stages!
