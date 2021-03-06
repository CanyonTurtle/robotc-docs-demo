
# Refining Build Skill

> Build Skill is only important *after* a design is figured out - knowing what to build is harder than knowing how to build it. This section is about the 'how', but the 'what' is just as important.

An important part of making competition-level robots is reducing the possible room for error, looseness, etc... that results simply from building without the level of scrutiny that is necessary.

'Slop' refers to building 'sloppily':
* [ ] spacing between parts is not exact
* [ ] don't even know the right number of holes / the right length that the parts should form
* [ ] gears don't mesh with each other perfectly
* [ ] connection is easily twisted apart
etc...
* [ ] so much friction, nothing spins

The key to refining build skill is finding the sources of slop, and eliminating them!

These sections are all about reducing slop, and being more precise:
1. [space out elements correctly](articles/refining-build-skill?id=know-thy-spacing)
2. [align the build](articles/refining-build-skill?id=aligning-made-easy)
3. [make proper joints](articles/refining-build-skill?id=make-proper-joints)

# Know thy Spacing

> See the [Spacing Tables](articles/spacing-table.md) for documented lengths of common spacing scenarios.

**Spacing** refers to putting nylon spacers, teflons, steel washers, shaft collars, and whatever else is going across the screw/axle on a joint, such that the parts can't slide around. Spacing is the only thing standing in between order and chaos on the drivetrain, the lift, and whatever else gets built - with spacing, the fight against slop is real. It is therefore important to be **precise** and **exact** - that means you know what the spacing should be, mathematically!

There are many ways to measure spacing. A ruler is an ok method, but there are more precise ways. For example, [Vex](https://www.vexrobotics.com/channel.html) publishes their part information, complete with dimensions. You might find everything you need to calculate spacing from this. Vex puts what are called `.STEP` files on their part product pages too - this is a complete 3D representation of a part. In combination with a free `.STEP` part viewer [online by autodesk](https://viewer.autodesk.com/), you might be able to space out your design without touching a piece of metal! That being said, having the full CAD program and designing your robot via computer is the most scalable way to space out the robot - it will measure distances for you the easiest.

> 'OD and ID' stand for 'Outside Diameter' and Inside Diameter' respectively.

Here are some basic facts about how VEX distances correlate in real life:

![c channel spacing](_media/refining-build-skill/c-chan-spacing.jpg)

- Holes happen to be exactly 0.5" apart from hole to hole in a straight line.
- The VRC max size limit is usually 18", so a 7-segment (35-hole) C-channel is 0.5" from being the max edge length.
- Screws are NOT exactly the right radius to fit inside the C channel squares. They are a bit smaller, which allows you to shift the metal a bit in a joint (which leads to less exactness.) Except for [shoulder screws](https://www.vexrobotics.com/all-screws.html) which do.
- C channel side-panels are NOT 0.5" exactly (see above). This implies things about how C Channels line up.

As you practice building in VEX, you will see that spacing exactness will determine how professional and how clean the robot 'feels'. Tight, exact, planned spacing is key.

Let's show a very simple scenario where you will need to calculate spacing: gears.

In a simple scenario, perhaps we want to find what spacing should be used to space out two 84-tooth gears on some axles.

![drawing](_media/refining-build-skill/cchandrawing.jpg)

To start, you need to model the problem. See the above picture - now we can solve for the space labeled 'A'. Now we need to find the lengths 'B', 'C', and 'D': we know we can. For this, I used some measurements on an online CAD viewer. You can see instructions on how to do this [in the CAD section](articles/cad.md).

the gear width ('B'):
![gearpic](_media/refining-build-skill/gearview.png)
The width the gear takes up - 0.50"

It is easiest if you can space out one side of both gears with a simple spacer (e.g. 0.25" spacer in this scenario would be appropriate). So There's our 'C'.

the C channel hole spacing: (Part of finding 'D')
![cchanpic](_media/refining-build-skill/c-channel-dimension.PNG)
(the distance from the center of the C channel hole to the inside edge) - 0.30"

Now, the remaining space on this axle just needs to be calculated.

```
Remaining Spacing = Total distance - Gear width - 0.25" spacer
A = D - B - C
A = (2 - 2(0.3)) - 0.5 - 0.25
A = 2 - 1.35
A = 0.65"
```

Let's allow 0.05" of tolerance, and that is a final distance of 0.6"
to fill with more spacers.

Wondering which spacers to use? This problem is solved for you already, you can use a Spacing Calculator.

Some people in our club [have made one already](articles/external.md?id=spacing-calculator).

This example illustrates some monkeying around to find the lengths precisely - it CAN be done! the reward is perfect spacing, and much less slop.

# Aligning Made Easy

There are several tricks you can use to easily 'line up' your build.
This includes the following guidelines:
- There is an integer amount of holes connecting sets of parallel C channels. If you can brace together your lift and your drive with C channels running 'across' the whole side, that is the best way! It is simple.
- The important joints are exact: they are either tightened with locknuts exactly centered, or they are mounted with shoulder screws. This ensures the spacing is exactly what you think it is! exceptions to this rule are when it's impossible to have centered spacing (like wedging a c channel between 2 other ones).

# Make Proper Joints

Firstly, joints that pivot **always** should have bearings on both parts of the joint. This is the **only** way to ensure a joint will be centered around the pivot point you want. Without bearings, you cannot center a screw.

> Shoulder screws are incompatible with bearings. Bearings + normal screws are for *moving joints*, while shoulder screws are for perfectly-aligned *rigid structures*.

Secondly, the distance between the two parts of the joint should be **minimized**. This is a huge way to reduce slop. Axles and screws will bend less and the joint will take up less space.

Thirdly, understand cantilever joints. A cantilever joint is when there is an open end on the pivoting screw/axle. Cantilever joints should only be done with screws, and they should have a middle locknut or keps nut securing the screw tightly to the first piece of metal.

![cantilever](_media/refining-build-skill/cantilever.jpg)

A Cantilever explanation
