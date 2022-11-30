# Workflow / Tutorial

This page will be the home of a walkthrough of Floh's _workfloh_ using Blender , [Siren Tool](https://www.nightshiftstudios.us/p/sirentool), and zModeler. Full disclosure, some details are left out, as they will likely be included as part of a future paid course.

- [Workflow / Tutorial](#workflow--tutorial)
- [Intro](#intro)
- [Workfloh Overview](#workfloh-overview)
  - [Siren Tool](#siren-tool)
  - [Blender](#blender)
  - [Photoshop](#photoshop)
  - [Substance Painter](#substance-painter)
  - [ZModeler3](#zmodeler3)
- [What is Actually Happening?](#what-is-actually-happening)
- [Steps](#steps)
  - [1. Get Assets](#1-get-assets)
  - [2. Make Assets](#2-make-assets)
  - [3. Plan Vehicle](#3-plan-vehicle)
  - [4. Make Pattern](#4-make-pattern)
  - [5. Create Emissive Meshes in Blender](#5-create-emissive-meshes-in-blender)
  - [6. Position Lights in Blender](#6-position-lights-in-blender)
  - [7. Export Assets to ZModeler3](#7-export-assets-to-zmodeler3)
  - [8. Do ZModeler3 Things](#8-do-zmodeler3-things)
  - [9. Position Other Assets in Blender](#9-position-other-assets-in-blender)
  - [10. Model Wiring and Other Details in Blender](#10-model-wiring-and-other-details-in-blender)
  - [11. Export Interior Assets and Details to ZModeler3](#11-export-interior-assets-and-details-to-zmodeler3)
  - [12. Meta Files](#12-meta-files)


# Intro


Hello! Welcome to the guide/documentation/walkthrough on how to create Non-ELS based emergency vehicle lighting for GTA and FiveM. Though the name "Non-ELS" implies that it's less useful than ELS, this is completely false. Non-ELS is harder (easier than it looks), but far more versatile, and powerful than ELS. Especially for FiveM, since ELS barely works for it.

This walkthrough will follow MY SPECIFIC workflow. You can use whatever workflow you want and/or not follow mine at all. The value from this walkthrough will be more from gaining an understanding of how Non-ELS works and learning basic 3D skills and concepts rather than just a step by step guide.

# Workfloh Overview

My motto when it comes to software and your time spent is:

> Spend as little time in ZModeler 3 as possible.

If you do this, you've already improved.

The software I use for my workflow includes:

*   Dawnstar Siren Tool
*   Blender
*   Photoshop
*   Substance Painter (Rarely)
*   ZModeler 3 :(
  
Notice how ZModeler 3 is last on my list. That's because I do literally as much as possible before ever going into ZModeler. This may sound harsh, but the program is literal trash. Anything you can do in **1 hour** in ZModeler you can do it **15 seconds** in Blender or any other 3D software.  
  
Obviously ZModeler is required in order to create a functioning vehicle with lighting for GTA, but again, use it only as much as you absolutely must. If you gain nothing else from this tutorial, please remember this tip.

## Siren Tool

If you're not familiar with Siren Tool, it's an application I made to aid in this exact workflow, or any workflow where you are making custom sequencers. It works especially well for the Blender workflow and when used properly, becomes immensely powerful.

Here's a basic tutorial for Siren Tool so you can see how it works, and the basic controls.

[https://www.youtube.com/watch?v=9o2ZMGoNrgM](https://www.youtube.com/watch?v=9o2ZMGoNrgM)


When Siren Tool becomes really powerful is when you are trying to use complex techniques like siren layering, and siren reusing.

**Reusing sirens** is easy without Siren Tool (ST), but with ST it's possible to make it much more useful, and intentional.

**Stacking sirens** without Siren Tool is doable, but difficult and impractical, but ST makes it easier and more useful.

I will cover these more in depth later (or in course)

## Blender

If you haven't heard of Blender, you may be living under a rock. It's an open-source 3D modeling software on its way to become the industry standard.

I cannot understate how useful and helpful Blender is for this process, if you are on the edge about learning it, do it. It's not as intimidating as it looks, 75% of the features in Blender you will not need for what you're doing for GTA and FiveM.

[Here's the link.](https://www.blender.org/features/)

Not only does Blender allow you to create your own custom assets, which makes everything both easier for you and look better in the end, but it can contribute to every step of the process except for the actual scaling and compounding of your Sirens.

Used in conjunction with Siren Tool you can make some extremely advanced patterns, make lighting stages with ease, position props and lights in seconds, unwrap and UV objects in minutes, and much more.

Not to mention, you can make some really sexy **renders** of your vehicles in Blender like this one...

which will make you feel like this:

![](https://t8521189.p.clickup-attachments.com/t8521189/bd3d3d80-bba3-46d1-a5e3-78f1e5aedd6c/giphy.gif)


You can use any other 3D software and accomplish all of the same things as Blender.

## Photoshop

Photoshop is used for editing images.

Nice.

This is useful for Non-ELS vehicles if you're making your own assets, making your own textures for someone else's assets, fixing textures that someone messed up, or making small adjustments to textures.

Example: Sometimes white textures are too blinding and lack contrast, so you can take the texture into Photoshop and mess with the levels so you can turn down the sun a bit.

Most devs make their white textures look like this:

![](https://t8521189.p.clickup-attachments.com/t8521189/12e82878-ab9c-4296-a1c0-d69b21660661/image.png)

In reality, this is the ideal value range for a white emissive:

![](https://t8521189.p.clickup-attachments.com/t8521189/647ce2c3-8518-4693-93af-f91b2c9ae4d9/image.png)

Photoshop is great for fixing "issues" like this.

Sometimes it's easier and better to just make your own textures, which Photoshop will allow you to do, and sometimes it's just for adjustments. It's pretty simple, but makes a big difference in your final result.

Also if you are skinning your cars yourself, this is a good tool for that.

[Here's the link if you're interested.](https://www.adobe.com/products/photoshop.html)

Pretty sure there's a discount for students on the full Adobe Suite.

## Substance Painter

Substance Painter is a 3D texture painting software. I almost never need to use this for GTA or FiveM.

Substance Painter would come into play if you were making your own assets. If you make your own assets, or you knew what Substance Painter was before this, you probably don't need any further explanation.

If you don't make your own assets you don't need to worry about this, and even if you do, it's only needed for more complex assets like full lightbars or interior parts. Most simple assets can be done using simple materials and UV mapping in Blender.

[Here's a preview!](https://youtu.be/RLRqUs0rSp8)

[Here's the link to purchase if you're interested.](https://www.adobe.com/products/substance3d-painter.html)

I think it's still free for students with a school email.

## ZModeler3

I don't want to talk about it for very long.

Basically it fills in the rest of the things you can't do in the preceding software.

It sucks, but it's required for the final steps of making a Non-ELS vehicle. If you follow my advice, and use other software as much as possible, you might survive making a car with all of your hair still on your head.

Stay away from this software as much as possible

Even if you get the hang of it, it's a pain in the butt.

Tips:

*   save backups often
*   save a new file, don't overwrite your old one
*   use as little as possible
*   work very carefully and slowly (otherwise you will touch something that breaks everything permanently.)

# What is Actually Happening?

If the most important tip in this tutorial is to use ZModeler as little as possible, this is the second most important... Actually this is probably the most important. If you are only going to take one thing from this tutorial, forget the thing about ZModeler and remember this section.

Most of the tutorials you have seen by now on Youtube or elsewhere have probably spent a few seconds explaining **HOW** things work, and they definitely didn't explain **WHY** they work that way.

With just this small piece of fundamental 3D knowledge, everything will make much more sense. Don't be scared if things start to click over and over again while you read this.

When Sirens "flash" in GTA/FiveM, they're not actually "flashing". What they're actually doing is scaling up and scaling down really quickly.

Now you're probably saying:

> Woah! "Scaling" I've heard that before, that's what I do to the sirens in ZModeler!
> 
![](https://t8521189.p.clickup-attachments.com/t8521189/5b3042ec-65f5-419f-a164-6809fcf958aa/giphy.gif)

Very good, your brain is on the right track.

Imagine this is your emissive mesh:

![](https://t8521189.p.clickup-attachments.com/t8521189/6ecebedb-8cb7-4b55-a0ea-7fbd23747eea/image.png)

Let's make it look nicer so you don't have to imagine as hard,

This is your emissive mesh scaled at 1.0 (or 100%):

![](https://t8521189.p.clickup-attachments.com/t8521189/738b974c-3b9f-443f-a3ee-c3b27aca6f3a/image.png)

This is your emissive mesh scaled to 0.1 (or 10%):

![](https://t8521189.p.clickup-attachments.com/t8521189/e491df7c-4387-428e-bc8d-bcd82cb6ef52/image.png)

This is what your mesh does in game when the pattern is running:

![](https://t8521189.p.clickup-attachments.com/t8521189/9ac3223a-e4cb-4c18-8810-3791229e6dc1/scaling.gif)

See that orange dot? That's called the **origin** of the object (the mesh (the emissive)).![](https://t8521189.p.clickup-attachments.com/t8521189/9cdd36af-e11a-46d8-bdb6-88077cc2a5b7/image.png)

Notice how when the mesh is scaled, it moves towards the origin.

![](https://t8521189.p.clickup-attachments.com/t8521189/438e1152-47ea-4ec7-98ca-1c7d63f700d5/scaling2.gif)

This is why it's so important to not mess up the "axes"/"pivot" of your mesh in ZModeler after you have positioned your object. Otherwise your mesh will not scale to the proper location.

This is also why rotating your environment lighting and meshes is so complicated and fragile.

In ZModeler the origin is the axis, the red green and blue lines that look something like this.

![](https://t8521189.p.clickup-attachments.com/t8521189/1587f140-e61f-4bb6-a2a6-a79043511aa9/image.png)

So yeah, that's what is happening. **Remember this**.

# Steps

_Still a work in progress and will continue to be updated._

## 1. Get Assets

There many different locations to obtain assets. Some are very high quality and some may not be depending on the creator. Be sure to check the NightShift Studios discord for any released assets. Below are links to assets on various different sites that are free. This list will continue to be updated as new information is released.

| LCPDFR | [https://www.lcpdfr.com/downloads/dev-resources/](https://www.lcpdfr.com/downloads/dev-resources/) |
| ---| --- |
| Modding Forum | [https://www.modding-forum.com/forums/board/47-development-resources/](https://www.modding-forum.com/forums/board/47-development-resources/) |
| GTAPoliceMods | [https://gtapolicemods.com/files/category/11-dev-support/](https://gtapolicemods.com/files/category/11-dev-support/) |

## 2. Make Assets

Couldn’t find the assets you wanted, at the quality you wanted in step 1? Or maybe you just prefer to make your own assets?

This is the time to use Blender or the 3D software if your choice to model your assets and texture them!

I mostly only use my own assets, and I only use Federal Signal lighting, so I don’t usually have to spend much time deciding what assets to use, but if you prefer to mix it up, you may want to visit step 3 below and then come back to step 2. Repeat as needed!

## 3. Plan Vehicle

In this step, spend some time looking at inspiration, and planning out how you want to layout your lights, what features your finished product will have, and what you want your pattern to be.

You may want to draw something simple out on paper or using software like Photoshop if you have a complex idea. Having something to refer back to when you’re confused later will definitely he helpful.

## 4. Make Pattern

There are several steps involved in making a pattern. Prior to the release of SirenTool, creating a siren was a painstaking process. You had to envision the pattern in your head and then attempt to apply that pattern to binary and complete it with many hours of trial and error. This section of the guide will help to create a pattern mostly using the SirenTool but will offer support for non-owning developers as well.

## 5. Create Emissive Meshes in Blender

Steps 5 and 6 are interchangeable!

It's best to have your lights cleaned up and with emissive meshes for each module before positioning them.

This is helpful when it's something you will have to rotate, as once a mesh is rotated it becomes a huge pain to then position emissive meshes later. Also if it's an ion or other light that you will be duplicating, it should be ready to be duplicated.

You can however position your lightbars where they need to be, just don't rotate them at all for now.

## 6. Position Lights in Blender

## 7. Export Assets to ZModeler3

## 8. Do ZModeler3 Things

## 9. Position Other Assets in Blender

## 10. Model Wiring and Other Details in Blender

## 11. Export Interior Assets and Details to ZModeler3

## 12. Meta Files

For more details about the content in each .meta files, you can view the other pages of this documents.

Direct links:

*   [Carcols.meta](https://doc.clickup.com/p/h/841f5-49/fcc06adefbff139)
*   [Carvariations.meta](https://doc.clickup.com/p/h/841f5-56/561f67429883b1c)
*   [Vehicles.meta](https://doc.clickup.com/p/h/841f5-127/d4dca1dd6666ce6)
