---
description: Ultimate Lighting Controller Intro
---

# Getting Started

![](https://user-images.githubusercontent.com/48927090/224608424-52e9505c-adc2-47dd-b5ab-30a5f933427f.png)

## ULC Overview

ULC is an all-in-one lighting controller for Non-ELS vehicles in FiveM! It uses the extra-based lighting stages on your vehicles and adds extra automation and improvements to create amazing, realistic, and fully configurable lighting controls.

The resource aims to make it as seamless as possible for vehicle developers to share ULC functionality with users of their vehicles. Vehicle developers can include a config file with their resource, and users can plug-and-play by adding the vehicle resource name to their ULC resource.

{% hint style="info" %}
See something wrong? Create an issue or edit on GitHub!
{% endhint %}

### Preview

{% embed url="https://youtu.be/f1H6sohjTao" %}

ULC focuses on being as customizable as possible, to fit every possible scenario. You can individually configure every vehicle you choose to use this resource with.

Each vehicle can use just one feature, or 3, or all of them. It's completely up to you.'

### Features

* Stage Controls
* Park Patterns
* Park Pattern Sync
* Smart Cruise Lights
* Brake Extras
* Reverse Extras
* Horn Extras

<details>

<summary>Coming Soon</summary>

* Smart Icons to replace some labels
* TA Display on HUD
* Sound choices

[Join our Discord](https://discord.gg/dwnstr-fivem) to make a suggestion!

</details>

## Installation

1. [Download the latest release from here](https://github.com/Flohhhhh/ultimate-lighting-controller/releases)
2. Extract `ulc` and place it in your resources folder
3. Add `ensure ulc` to your `server.cfg`

## Learn How to Use ULC

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3>Server Owners</h3></td><td>Learn how to configure ULC for your server.</td><td></td><td><a href="configuration/#adding-vehicle-configurations-to-a-server">#adding-vehicle-configurations-to-a-server</a></td></tr><tr><td><h3>Vehicle Devs</h3></td><td>Learn how to configure vehicles for ULC.</td><td></td><td><a href="configuration/#configuring-vehicles-for-ulc">#configuring-vehicles-for-ulc</a></td></tr></tbody></table>

## FAQ

<details>

<summary>Why won't my extras change until my vehicle is repaired?</summary>

Any extra that has collisions requires the vehicle to be repaired in order for it to toggle. That means if your light extra has collisions, ULC will not be able to change the extra.\
\
If you are the one who is making the vehicle simply remove the collisions from your extra.

Alternatively, you can set the repair field on the button to true, which will force the vehicle to repair when the button is pressed. (This is not an ideal solution, the effect will be disabled when the vehicle is damaged or a door is open.)

</details>
