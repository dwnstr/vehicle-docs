# Stage Controls

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## What are Stage Controls?

Stage Controls, or "Buttons" as they are referenced in the code, are the bread and butter of ULC. They enable you to provide the player with key-bindings that will interact directly with vehicle lighting extras in real time.&#x20;

Only the stage buttons you define will appear on screen, if none are defined the ULC ui will be hidden.

## Example Usage

* Traditional Stage Lighting&#x20;
* Traffic Advisors
* Flood/Scene/Alley Lighting
* Alternative Patterns
* Anything else!

## Button Setup Guide

### Things to Keep in Mind before Starting

Planning is key to a great Stage Control Buttons setup.

Due to the nature of sirens and extras, sirens parented to extras only show when the extra is enabled, so those Sirens are effectively eliminated from your workflow. They can't be re-used anywhere else.

This can leave you pretty short on sirens if you commit too many of them to extras that aren't used often. [Siren Tool](broken-reference) can help you with planning out your vehicle to be very efficient with sirens.

Other than that, the process is pretty straight forward.

### Steps

1. Plan, plan, plan!
2. Compound your sirens as usual in ZModeler3.
3. Parent your sirens to extras as needed.
4. Configure your buttons in ULC!

### Values

#### label

The label field represents the text that will be shown on the UI within the button.

It is best to use short labels since longer labels will be cut-off and stretch the UI. Use abbreviations such as "TKD" in place of "Takedowns" whenever possible.

The string will always be rendered in all-caps on the UI.

```lua
label = 'STAGE 2',
```

![](<../../.gitbook/assets/image (1) (1).png>)

#### key

The key defines the numpad key that the button will be bound to.

```lua
key = 5,
```

#### color

Color defines the color of the button when active.

Default value: `'green'`

```lua
color = 'green'
```

Possible values:

* 'green'
* 'blue'
* 'red'
* 'amber'

#### extra

The extra field specifies the primary extra for the button. This extra will always match the state of the button.

```lua
extra = 8,
```

#### linkedExtras

Linked extras specifies extras that will match the state of the main extra when the key is pressed. Consider the example below:

```lua
extra = 8,
linkedExtras = {9, 10},
```

If the player turns on extra 8, then extra 9 and 10 will also turn on. If you turn off extra 9 or 10, then press the key to disable 8, all 3 extras will be off.\
\
&#x20;Linked extras can be controlled independently from the primary extra, but when the state of the primary extra is changed by the player, the linked extras will match it.

#### oppositeExtras

Extras specified as oppositeExtras will be set to the opposite of the state of the button when the key is pressed.

```lua
oppositeExtras = {5}
```

Whenever the stage is enabled extra 5 will turn off.&#x20;

Whenever the stage is disabled extra 5 will turn on.



#### offExtras

Extras in the offExtras field will always turn off when the primary extra is enabled.

When the primary extra is turned off, the offExtras are unaffected.

```lua
offExtras = {6, 7}
```

#### repair

Default value: `false`

Setting repair to `true` will make the vehicle repair itself whenever this stage is enabled. This effect is disabled while the vehicle is damaged, or when a door is open.\
\
This is important for high poly extras, or extras with collisions. If you want to avoid this limitation, make sure to not include collisions in your lighting extras.

```lua
repair = true
-- or
repair = false
```

#### Example button

```lua
{   -- the name/label that will show on the UI
    label = 'STAGE 2',
    -- which numpad key the stage will use by default
    -- players can remap these keys on their own
    key = 5,
    -- the extra that this key will toggle
    extra = 8,
    -- extras that will toggle along with the main extra
    linkedExtras = {9, 10},
    -- extras that will turn off when stage activates
    offExtras = {6, 7}
},
```

## Full Setup Example



Example:&#x20;

```lua
buttons = {
    {label = 'STAGE 2', key = 1, extra = 8, color = 'green', linkedExtras = {10, 11}, offExtras = {}},
    {label = 'TA', key = 2, extra = 9, color = 'amber', linkedExtras = {}, offExtras = {}},
    {label = 'AUX1', key = 3, extra = 10, color = 'green', linkedExtras = {}, offExtras = {}},
    {label = 'AUX 2', key = 4, extra = 11, color = 'green', linkedExtras = {}, offExtras = {}},
    {label = 'SCENE', key = 5, extra = 12, color = 'green', linkedExtras = {}, offExtras = {8}},
}
```



## Tips & Tricks

* Any stages you create can also be used by any other feature of the resource. For example, if you create a stage extra that has an alternate pattern, you can then use that pattern as your brake pattern.
* Stages are fully state aware, meaning if your alt pattern was enabled before you started braking, it will remain on after you finish braking. The same logic applies other features, except park patterns.
* Each vehicle can have a maximum of 9. If none are configured for the vehicle, the UI will not show at all. Only buttons that are configured will appear on the UI.
* No two buttons can share the same primary extra.
* Keys don't have to be listed in order or sequentially. You could use 5, 3, 1, 7, 2 if you wanted. However, they will render on the UI in ascending order left to right.
