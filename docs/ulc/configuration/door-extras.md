---
description: Details about how to configure door extras for ULC.
---

# Door Extras

Door extras allow you to enable or disable certain extras when doors are open.

```lua
doorConfig = {
    useDoors = false,
    driveSide = {enable = {}, disable = {}},
    passSide = {enable = {}, disable = {}},
    trunk = {enable = {}, disable = {}},
},
```

## Example

If I wanted to disable extras 4 and 5 whenever a door is open, I would set disable to 4 and 5 for both driver side and passenger side.

<pre class="language-lua"><code class="lang-lua">doorConfig = {
    useDoors = false,
<strong>    driveSide = {enable = {}, disable = {4, 5}},
</strong><strong>    passSide = {enable = {}, disable = {4, 5}},
</strong>    trunk = {enable = {}, disable = {}},
},
</code></pre>

{% hint style="info" %}
Door extras are not state aware
{% endhint %}
