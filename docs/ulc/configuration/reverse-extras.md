# Reverse Extras

Reverse extras will turn on while vehicle is in reverse.\
\
The intended use for this is adding reverse lights to the lightbar.&#x20;

## How to Create Reverse Extras

To create reverse extras, simply create new emissive meshes to use, and parent them to an extra. Then add that extra to the reverse extras in the \`\`ulc.lua\`\`.\
\
If you want the reverse lights to have environment lighting, you should could make them a siren.

## Example

```lua
reverseConfig = {
    useReverse = true,
    reverseExtras = {12}
},
```
