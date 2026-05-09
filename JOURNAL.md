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
