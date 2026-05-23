---
title: Foldup 3D Printer
author: Kai Pereira
description: This is my folding, scissor lift, cross-gantry 3D printer I'm working on for Open Sauce 2026!
created_at: 2026-5-6
---
## An idea was born! - 7 Hours

I design a lot of circuit boards that I do a lot of basic CAD for too. Like if I ever design a keyboard, I'll make a keyboard case, if I make a radio I make a little weather station out of it, etc.

Last summer, I designed my own 3D printer motherboard, and it's made me really antsy to design my own foldup printer! So; I've spent quite a few hours (and a day of skipping school) to come up with the exact type of foldup mechanism I want to do, alongside some other cool specs for it!

My process was fairly simple:
- I wanted to have a decent amount of bed area for if I brought it to hackathons and needed to print something a bit larger
- I wanted it to be able to fit inside of a filament box so it's easy to transport
- Should be made using off-the-shelf parts, and the design shouldn't be insanely overly complex.

After many hours, I came up with my brain-child! A folding, scissor lift, cross/double cantilever 3D printer. It's essentially a combination of this cross-cantilever, and the X-printer:

![Pasted image 20260506172806.png](images/Pasted%20image%2020260506172806.png)

![Pasted image 20260506172814.png](images/Pasted%20image%2020260506172814.png)

It took me a really long time to come up with this sort of concept, but I think it'll be insanely cool, a bit complicated and also sacrificing a bit of bed space, but worth it for the insanely cool project!! 

I went through about 10 different concepts, and while some would definitely work better, I think this one is the coolest by far!

![Pasted image 20260506173001.png](images/Pasted%20image%2020260506173001.png)

So let's get into designing this thing!!

## Setting up my CAD workspace and planning - 6 Hours

I like to spend a lot of time thinking exactly how something will come together before putting it actually together, so the next thing I did was think about what parts I wanted to create the base out of and then build it up from them. 

I initially wanted to go with an extrusion approach and even had a pretty good plan for it, but it had some major problems:
- The extrusion was quite tall, so I wouldn't be able to mount the rails on the top faces of the extrusion, or much else so it would be really hard to build a stable printer
- It would be difficult to mount electronics in such a compact frame, and it might be kind of difficult to cut and assemble the entire thing in such a small area.
- Mostly rigidity concerns, I would be working against gravity instead of with it, and the space constrains were really bad.

![Pasted image 20260508181737.png](images/Pasted%20image%2020260508181737.png)

So i decided to pivot to using 1/8" aluminum plate, just like the X printer, and I came up with a really solid plan for how I want it to work!

![Pasted image 20260508181944.png](images/Pasted%20image%2020260508181944.png)

Nothing's labelled too well but essentially, this gives me a lot of height to work with so I can mount rails to the top and everything else.

Now that I had an actual plan for how I wanted to construct this thing, and a really good vision, I needed to get the basic components in. So I made dynamic models of rails, extrusions, added in bearing models, base plate, just some stuff that would be nice to be able to dynamically add into my model.

![Pasted image 20260508182204.png](images/Pasted%20image%2020260508182204.png)

I did a bit of researching and also decided to use 608 bearings for the scissor lift because they're really accessible, commonly used and a good size. And I also figured out that I wanted to mount my bearings using shoulder bolts, because they would fit really nicely, and they're super strong and polished!

So with all that thinking out of the way, we can get a bit more into designing this thing! 

## Basic scissor lift CAD - 7 Hours

Now that I have lots of the basic components like rails, bearings, and had an idea of the type of mounts I wanted to make, I could actually work on the scissor lift!

The first thing I did, was I made a static mount for the 2 scissor lifts to be fixed to, and then a moving carriage, could move the second part of the scissor lift, allowing it to go up and down.I decided to use a heatset insert + shoulder bolt method because the tolerances are really tight for the bearing to attach onto and it can stiffly attach into the 3D printed block.

![Pasted image 20260509184419.png](images/Pasted%20image%2020260509184419.png)

I've also decided to actively start a BOM, so that I didn't accidentally forget parts, and so I could have all the dimensions, concrete.

![Pasted image 20260509184459.png](images/Pasted%20image%2020260509184459.png)

It wasn't just a smooth process towards creating my mount, but instead lots of revisions and reflecting, while constantly importing the stuff into my assembly and seeing how nicely it fit in.

Next, I made the moving carriage mount for the scissor lift:

![Pasted image 20260509184557.png](images/Pasted%20image%2020260509184557.png)

I'm trying to stick to using M3 bolts for most of this project to minimize my BOM, so you'll notice lots of these components use the same clearances.

And then after lots of revisions, I finally have a simple linear motion system for my scissor lift!

![Pasted image 20260509184659.png](images/Pasted%20image%2020260509184659.png)

And then finally, I can just repeat this linear motion system on the top to get my scissor lift motion down!

![Pasted image 20260509231229.png](images/Pasted%20image%2020260509231229.png)

But this does pose an interesting problem now, because I can't mount the cross-cantilever rails to the top of the plate, or else the whole thing will be too tall, and if I mount it to the bottom of the plate, next to the scissor lift motion, it'll be shorter which also isn't ideal.

So tomorrow, I'll have to figure out this tricky problem, and then I'll also hopefully add in the actual scissors too!

## Scissor lift arms, nuts and bolts - 5 Hours

Now that I have the scissor lift motion system, I can actually add in the arms! 

I decided to keep the material on the arms to be that 1/8" aluminum plate I'm using for the base and top plate, to minimize my BOM, and also because it'll be perfectly fine and 4 plates shouldn't be bending too much. It's also much lighter, so there's less stress on the joints, which is very convenient!

I did a basic model of the scissor arms first so I could get an idea of how they'll fit, and I think it turned out pretty nice!

![Pasted image 20260511104312.png](images/Pasted%20image%2020260511104312.png)

This gives me about 11cm of Z motion, but I think I can optimize it even more for up to 12/13cm, which I think is pretty good, considering this printer is under 20x20cm! The tolerances are pretty tight and I used -0.001" for the 608 bearing so it's a nice press-fit, and I can thermally expand it if needed.

This only gives me about a mm of spacing which is really tight though, but I think it'll be fine, and might honestly keep everything together, nice and rigidly.

![Pasted image 20260511104501.png](images/Pasted%20image%2020260511104501.png)

And now that I have my scissor arms in, let's actually add in all the nuts and bolts to hold together this mechanism together!

I already had all the holes and counterbores for my socket head cap screws (which are really good for rigidity and vibrations), so it was a matter of just adjusting stuff so they fit in nicely with what I was ordering!

![Pasted image 20260512202150.png](images/Pasted%20image%2020260512202150.png)

All the screws are just M3 socket head cap screws which makes the BOM nice and minimal, and they're just of sizes 10mm, 12mm and 25mm!

Now that I have this the actual linear motions parts for this mechanism, I need to make the moving parts, so let's do that next!

## Belts, idlers, drivers and planning - 6 Hours

Now coming into this project, I had no clue how belts actually worked, or their standard sizes. So this led me down the rabbit holes of belts!

The first thing is that 3D printers typically used GT belts and specifically GT2/GT1.5 belts which have their respective pitches. I've decided to use GT2 belts, because they provide more rigidity, being bigger.

Next, there's the idlers and drivers/timing pulley. The idler simply sits fixed on one end so the belt can move freely and then the driver spins from a stepper to drive the whole belt!

![Pasted image 20260515104410.png](images/Pasted%20image%2020260515104410.png)

The driver is attached directly on to the shaft of the Nema 17 and then you can tighten it using the set screws in the driver. 

Next, I wanted to plan out how I was actually going to put on the X/Y axis, so that it wouldn't intersect with any of my belts.

I was on a flight during this process, and decided that mounting them perpendicular to the top plate would be best to minimize space, but I haven't 100% decided on it yet:

![Pasted image 20260520213309.png](images/Pasted%20image%2020260520213309.png)

Now I also need to decide on what type of steppers I want to use!

But before I do that, I think it'll be a good idea to actually figure out how everything will fit onto the printer. I've come up with 2 main concepts that would both work fairly well.

The first system is a fairly complicated, belt-only system:

![Pasted image 20260521215527.png](images/Pasted%20image%2020260521215527.png)

This one has the advantages of looking cool, and probably being fairly rigid, but it's quite complicated because it uses perpendicular belts, and also takes up quite a lot of space.

The next idea I came up with, with a friend is this leadscrew system:

![Pasted image 20260521215619.png](images/Pasted%20image%2020260521215619.png)

This one has the advantage of having a really rigid, but slower base, that might be a bit harder to fit in. But the top doesn't have any driving electronics, which is a bit risky in case there's backlash. But it also does open up the opportunity to cleanly mount the X/Y electronics.

I also got a suggestion from this friend to maybe double shear my scissor lift axes or to at least make them more rigid somehow, so I'll have to explore this some more later:

![Pasted image 20260521215817.png](images/Pasted%20image%2020260521215817.png)



## Actually assembling the vision

Now that I've created drawings of where I want to position the electronics, I need to functionally place them in to see if everything will work!

The first thing I got in was the base:

![[Pasted image 20260522221338.png]]

Doing something like this, will allow me to maximize the motion I can have for my Z, and also make it pretty rigid! I think leadscrews will be significantly better than belts for this, especially considering that the whole system isn't constantly moving up and down, creating backlash.  