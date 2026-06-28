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



## Actually assembling the vision - 5 Hours

Now that I've created drawings of where I want to position the electronics, I need to functionally place them in to see if everything will work!

The first thing I got in was the base:

![Pasted image 20260522221338.png](images/Pasted%20image%2020260522221338.png)

Doing something like this, will allow me to maximize the motion I can have for my Z, and also make it pretty rigid! I think leadscrews will be significantly better than belts for this, especially considering that the whole system isn't constantly moving up and down, creating backlash.  

Next I need to assemble the X/Y axes! I want to do something like this:

![Pasted image 20260523164039.png](images/Pasted%20image%2020260523164039.png)

But, I'm worried that the steppers on the top are going to intersect the leadscrews on the bottom, so I might have to move the steppers upwards, or switch to leadscrews and flip the steppers to be pointing towards the end!

Anyways, I spent wayyy more time and actually fully fleshed out the motion system after quite a bit of iteration!

![Pasted image 20260524180839.png](images/Pasted%20image%2020260524180839.png)

Every single axis is leadscrews because they're the most space efficient, and I think it'll make all the axes really rigid which is super important for a flimsy, folding printer!  

This is just a mockup of the whole things but it works in theory, and now I just have to properly attach everything! 

## Properly Mounting Everything - 4 Hours

Now that I had everything laid out, I can mount it to the plates. The main things I need to do is create brackets for the motors that will keep them rigidly mounted on a very small profile.

I first created this Nema 14 mount:

![Pasted image 20260528091132.png](images/Pasted%20image%2020260528091132.png)

And then I created the Nema 11 mount:

![Pasted image 20260528091159.png](images/Pasted%20image%2020260528091159.png)

After a bit of trial and error, I got everything nicely mounted on:

![Pasted image 20260528091228.png](images/Pasted%20image%2020260528091228.png)

I still have the X/Y axes to rigid mount, but those require making mounts that'll also be fixed to the leadscrews which is going to be a whole thing to do, so I want to get everything nicely fitted before getting to that! 

The vision is really coming together though, but this is still a pretty rough assembly that needs some tuning on the sizes and spacings.

## Tuning, major improvements and spacers - 7 Hours

I skipped school and go an insane amount of work done on the printer! 

The first thing I needed to do, was mount the other X/Y axes to the top plate:

![Pasted image 20260529223416.png](images/Pasted%20image%2020260529223416.png)

I decided on a little 3D printed block because I think it'll be rigid enough and it also lets me add the spacer directly onto it!

Next, I added an end-stop to all the ends of the linear rails. This is just a small, 5mm printed block that sites on the end of each rail:

![Pasted image 20260529223528.png](images/Pasted%20image%2020260529223528.png)

And then I did an absolute ton of fine-tuning during this process to get everything sitting nicely within the footprint. This took most of my time, but it came out really nicely:

![Pasted image 20260529223620.png](images/Pasted%20image%2020260529223620.png)

It took me a ton of time to elegantly do this, but all of this is basically a finished product now. 

Next I figured out how I wanted the cross-cantilever to sit. I did a basic alignment which gave me the outline for how I'm actually going to attach it, but I'm going to leave this for now and onto more pressing matters:

![Pasted image 20260601205931.png](images/Pasted%20image%2020260601205931.png)

All I have left is to do the actual cross-cantilever aspect and to add on the extruder, and then I'll be onto doing the electronics! 

## Pause on the X/Y axes - 4 Hours

Now before I actually finish up the XY axes, I need to figure out what motors I'm actually going to use. I spent many hours searching and comparing prices, and the best I found were 2 steppers that were identical to what I already had, the only difference was the leadscrews, and the length of the Nema 14, which were perfectly fine.

My steppers have the final specs of :
- Nema 11: 28x28mm, TR5x4, 100mm travel
- Nema 14: 35x34mm, TR5x2, 150mm travel

The nema 14 isn't ideal, but it works ya know. 

Next, I wanted to mount the scissor lift to their respective steppers. This actually took longer than expected, because I had to fix some unconstrained sketches (silly me, don't do that lol), but I got a nice alignment after a lot of fine tuning:

![Pasted image 20260601210301.png](images/Pasted%20image%2020260601210301.png)

And this honestly, isn't really ideal because it only gives me 80mm of travel, but I'll do some fine tuning later, and hopefully we can improve that! 

## Wrapping up the axes and starting on the extruder - 7 Hours

Now that I've constrained the lead-screws to their respective stepper, I need to do the same thing but also constrain it to the XY axes. This if fairly complicated because each axis needs it's own special mount, and then they need to be fine-tuned in order to maximize build volume and make space for the toolhead.

So the first mount I made, was this one for the X axis. It's fairly simple but also pretty complicated and I put a 3.5mm slab of PLA, to hole everything together essentially:

![Pasted image 20260603220525.png](images/Pasted%20image%2020260603220525.png)![Pasted image 20260603220551.png](images/Pasted%20image%2020260603220551.png)

Next, I needed to make the Y mount! This one was a bit simpler because it was above everything, so I could just have one slab that connected everything, but it's definitely not quite as rigid, so I might need to make some modifications later. 

![Pasted image 20260603220703.png](images/Pasted%20image%2020260603220703.png)

Looks gorgeous but took me way too long to wrap my head around.

Now I need to fit an extruder onto this though. I'm thinking that I probably want to mount it right in this little sandwich right here, because it basically stands as one of the corners to my bed, which is very convenient!

![Pasted image 20260603220829.png](images/Pasted%20image%2020260603220829.png)

So I did a lot of exploring, testing different extruders to find the most compact one that could fit within this area, and the best I could come up with so far was this:

![Pasted image 20260603220916.png](images/Pasted%20image%2020260603220916.png)

Definitely needs more exploring because this is clearly too tall, but it's not bad a start. This one's a ProtoXtruder V2 with a X1 hotend, and this is actually a pretty good combo, but still too large sadly. So I might have to explore a bowden extruder or something, but we'll save that for tomorrow!

## Refining, electronics and extruder - 10 Hours

After I created all the leadscrew mounts, I did a lot of brainstorming on how I want the extruder to work. It's very important in a cross-cantilever, to minimize the weight on the end of the cantilever because it's going to have lots of flex, and even more the farther out it is which exponentially increases the forces on it. 

Anyways, before I even think about the extruder some more, I know that I need to figure out where the electronics and bed are going to go. The bed is relatively compact in the area of the printer, so I decided to do that all, and constructed a layer of cork as a heat shield, and then the heater + thermistor, aluminum spreader, and then magnetic plate to stick the PEI sheet onto. 

![Pasted image 20260606022624.png](images/Pasted%20image%2020260606022624.png)

Next, I wanted to get the actual height of how small this printer will be when folded up, so I modified the scissor lift to get the smallest printer height, which is over a centimeter smaller then before:

![Pasted image 20260606022730.png](images/Pasted%20image%2020260606022730.png)

That gave me some problems with my previous mounts, because I had to modify stuff so it didn't hit the bottom Nema 14 here, so I redesigned those with some relative ease:

![Pasted image 20260606022816.png](images/Pasted%20image%2020260606022816.png)

Now my idea is to fit all the electronics underneath the bed. I currently have about 62mm between the top of the bed and the top of the printer, so if my electronics take up 30mm of vertical space, then I'll need to make my hotend, just a mere 32mm, which is only possible with a bowden extruder if I'm being honest.

So I currently have a good vision to actually do that and to put the electronics underneath, and then my bowden extruder in the corner of the printer, and then a really small hotend:

![Pasted image 20260606023045.png](images/Pasted%20image%2020260606023045.png)

So the first thing I decided to do, is re-work my bed so that I can fit the electronics underneath it. I decided to make my electronics architecture be an SKR Mini E3 V3.0 with DC barrel jack for input power so that it's nice and portable with no PSU! 

![Pasted image 20260608225958.png](images/Pasted%20image%2020260608225958.png)

![Pasted image 20260608230015.png](images/Pasted%20image%2020260608230015.png)

The bed is countersunk into the standoffs using machine bolts, and I decided to leave enough space so that the hotend mount would just barely not be glazing the printer bed.

Next, I need to work on the extruder. I was lucky and had barely enough space to squeeze in a Nema 11, and it actually gets pretty close torque to a pancake Nema 14 so it should be good enough to extrude PLA with some finesse:

![Pasted image 20260608230228.png](images/Pasted%20image%2020260608230228.png)

It took me a WHILE and quite a few sketches to come up with an extruder design, but I've decided to use a planetary gearbox with thin, but long extruder gears because they weirdly fit in nicely into the design:

![Pasted image 20260608230333.png](images/Pasted%20image%2020260608230333.png)

*To be adjusted*

I made this nice little custom planetary gearbox (which has a very cool assembly >:) which gives me a 5.33:1 gear ratio, which should be good for getting the around 0.4 N-m of torque I need to extrude PLA:

![Pasted image 20260608230447.png](images/Pasted%20image%2020260608230447.png)

And that's the basics of the extruder concept, finished! Now we can get onto finishing it up, and working on the hotend too.

## Finishing up the custom extruder - 16 Hours

Now the planetary gearbox actually fit decently, but if I'm being honest, there's not too much space left for the actual filament drive gears or I can't even put them in a nice spot. Most extruders don't use planetary gearboxes, and instead, just use spur gears to get their, so let's design a new extruder with gears. 

I'm going to use all the parts from the HGX lite extruder and reference the step model of that extruder throughout my design too.

![Pasted image 20260609232351.png](images/Pasted%20image%2020260609232351.png)

This gives me a much cleaner design that I can more easily customize, because I don't have a clunky planetary gear in my mechanism. It also has better access for the filament to travel through the whole mechanism so that I don't have a twisted PTFE tube!

Anyways, next I needed to essentially build off of this current design, to create something more refined, with everything attached. Building an extruder is like building with lego, and you just keep on adding and cutting down stuff until you get something nice and refined.

So after many hours, I came up with this basic, almost working design:

![Pasted image 20260610223402.png](images/Pasted%20image%2020260610223402.png)

The only thing that this extruder is missing, is the PTFE connector fastened to the extruder, and then the path the filament will take. But everything is pretty much properly attached, albeit, pretty terribly.

And it actually fits very tightly within our printer, but it fits nonetheless!

![Pasted image 20260610223549.png](images/Pasted%20image%2020260610223549.png)

Next I needed to add the actual PTFE connector with it's grub screw and the tensioner screw to the design. This is quite tricky, because I essentially need to separate the extruder's top half into 2 additional parts so that you can adjust the  distance between these 2 parts to adjust the tension at the filament driver. 

And after a lot of research, this is what my design looks like:

![Pasted image 20260611231017.png](images/Pasted%20image%2020260611231017.png)

I also did a lot of minor modifications to the bottom and whatnot, but now I actually need to finish it off:

![Pasted image 20260611231112.png](images/Pasted%20image%2020260611231112.png)

Here's how the extruder currently fits inside of the printer:

![Pasted image 20260611231142.png](images/Pasted%20image%2020260611231142.png)

*Very precisely!*

Next, I need to add the output PTFE connector, and then fix everything together, polish up a little bit and then it'll be good! 

So after a lot of procrastination, I got something pretty decent:

![Pasted image 20260614225722.png](images/Pasted%20image%2020260614225722.png)

There's a lot of refining that still needs to happen, but some good progress is happening.

And then just like that, we have a finished extruder, albeit a terrible one:

![Pasted image 20260615225505.png](images/Pasted%20image%2020260615225505.png)

It all fits nicely, so now I can move onto figuring out the hotend!

![Pasted image 20260615225555.png](images/Pasted%20image%2020260615225555.png)

## Finishing the hotend

Now that I've finished the custom bowden extruder, I need to figure out what hotend I want to use.

I have very little clearance for my hotend, so that means I need to pick my hotend very carefully.

These are 4 extruders I decided to first test out:

![Pasted image 20260616222705.png](images/Pasted%20image%2020260616222705.png)

All of these turned out to be too tall except for the mosquito hotend, and then also the [Deltaprint mini hotend](https://www.deltaprintr.com/product/mini-hotend/) , but these are quite expensive. One of my favorite options was the Phaetus Dragonfly BMS which is the blue one, and is quite small and also cheap, but it's still a bit too tall, but there's still a chance that I can alter the design to make it work.

I've reached out to Slice Engineering to maybe get a free mosquito hotend, but I'm still looking at other options, like potentially making a custom extruder from parts from a normal one, by just bodging it a bit.

After a lot of deliberation, I've decided to just go with the positron or the funssor, 90 degree hotends:

![Pasted image 20260621221831.png](images/Pasted%20image%2020260621221831.png)

The funssor hotend is my first choice to buy because it's cheaper, but the positron hotend would easily be better if I could get it sponsored. 

And with that decision out of the way, I can get to actually designing the hotend mount!

Before I do that though, I actually got some responses back from LDO motors and they said that they would sponsor my project with a positron hotend, and potentially some motors/extruder too, so I'll be designing around that hotend!

I needed to adjust all the mounts to allow the clearance underneath some of the linear rails so that I could fit it underneath, but it fits perfectly. 

Now I just need to attach it on, and fix all the mounts, and then wrap up the BOM and then I'll be all done!

The first thing I decided to tackle was the mechanical stuff:
- I created the actual hotend mount and added the fans. I used a 3510 fan because it was the only one that fit in the form factor
- I modified the X/Y leadscrew mounts so that they don't intersect other parts anymore and so that they also work and look better
- Fully assembled everything and added the nuts and bolts

![[Pasted image 20260627182820.png]]

The printer is actually fully complete now, and I can move onto the BOM! I had been building out my BOM throughout the entire project, so it didn't take long to complete.

I essentially just had to format and then compile all the prices, and that took me a couple hours:

![[Pasted image 20260627182934.png]]

I also included my sponsorships, and the whole projects is actually pretty good, coming in at around $455:

![[Pasted image 20260627183001.png]]

After organizing all the files in my repository and creating my readme, this project is officially done!

![[Pasted image 20260627183031.png]]

