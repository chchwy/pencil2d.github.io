---
layout: page
title: "Lesson 3: Squash, Stretch and Easing"
tagline: Make the ball bouncy, give it a shadow, and share it as an animated GIF
comments: false
---

In Lesson 2 the ball moved with good timing and spacing, but it still looked like a hard, stiff object. In this lesson students improve the same ball with three classic principles: **squash and stretch**, **slow in and slow out** (easing) and **arcs**. They add a shadow on its own layer and export the result as an animated GIF they can share.

> **Note:** On macOS, use <kbd>Cmd</kbd> wherever this lesson says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> for <kbd>Alt</kbd>. On many laptops, <kbd>F6</kbd> and <kbd>F7</kbd> need <kbd>Fn</kbd> held down.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | 75–90 minutes |
| **Level** | Beginner (after Lesson 2) |
| **Animation principle** | Squash and stretch; slow in and slow out; arcs |
| **Pencil2D skills** | Editing existing keyframes, Clear Frame, Flip In-Between, adding and ordering layers, layer opacity, exporting an animated GIF |
| **What students make** | The Lesson 2 ball with squash, stretch and a shadow, exported as a looping GIF |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Explain squash and stretch, and keep the ball's size (its "volume") believable while it changes shape.
2. Read a spacing chart and point out where an action slows in, slows out, or has even spacing.
3. Explain why natural movement follows arcs.
4. Put a new layer in the right order in the layer stack.
5. Export an animation as a looping animated GIF and check it outside Pencil2D.

## Before Class {#before-class}

- Students need their Lesson 2 project. Anyone who missed it can use a finished bounce you prepare in advance (see below).
- Work through **Step by Step** yourself, including the GIF export, on a lab computer (about 20 minutes).
- Decide where GIFs should go: the class folder, or a learning platform where students upload them.
- **Optional starter file** (`lesson03-start.pclx`): a copy of your own finished Lesson 2 bounce, with a **Ball** layer (keyframes on 1, 3, 5, 7, 9, 11 and 12) and a **Ground** layer.
- **Optional:** a squishy ball or a water balloon to show squash, and a short clip of a cartoon character landing from a jump.

## Key Ideas {#key-ideas}

**Squash and stretch.** A soft object *squashes* (flattens) when it hits something and *stretches* when it moves fast. The trick is to keep the same amount of object: when the ball gets flatter it must also get wider, and when it gets taller it gets thinner. A rubber ball squashes a lot; a bowling ball hardly at all. Squash and stretch shows what something is made of.

**Slow in and slow out (easing).** Things rarely start or stop at full speed. They speed up gradually (*slow out* of a pose) and slow down gradually (*slow in* to a pose). On a spacing chart, easing shows as drawings bunched close together near the pose:

```
Even spacing (mechanical, like a robot):
1         3         5         7
|---------|---------|---------|

Slow out (starts slowly, speeds up):
1  3      5                   7
|--|------|-------------------|

Slow in (slows down to a stop):
1                   3      5  7
|-------------------|------|--|
```

The bouncing ball has both: it **slows in** to the top of the bounce and **slows out** of it. At the ground there is no easing at all: the ball changes direction instantly, and that sudden stop is exactly where the squash goes.

**Arcs.** Most natural movements follow curved paths, not straight lines: a thrown ball, a swinging arm, a head turning. A ball bouncing across the screen travels in a row of arcs, each one lower than the last:

```
O
 .            . .
  .         .     .          . .
   .       .       .       .     .      . .
    .     .         .     .       .   .     .
-----V---------------V-------------V----------V---
```

| Word | Meaning |
|---|---|
| **Squash** | Flattening when an object hits something or lands |
| **Stretch** | Getting longer in the direction of travel when moving fast |
| **Volume** | The amount of object. It should look the same whatever the shape |
| **Slow in / ease in** | Drawings get closer together as the object comes to a stop |
| **Slow out / ease out** | Drawings start close together as the object starts moving |
| **Arc** | The curved path a moving object follows |
| **GIF** | An image file that can contain a short looping animation; it plays in any web browser |

**What to say:** "Squash and stretch shows what something is made of. Easing shows that it has weight. Arcs make it feel natural. Every good animation uses all three."

## Demo {#demo}

About 10 minutes.

1. **Squash a real soft ball** in your hand or show a landing clip in slow motion. Ask: "What happens to its shape?"
2. **Open your Lesson 2 bounce.** Go to the contact frame (7), clear it with **Edit → Clear Frame**, and draw a squashed ball: flat on the bottom, wider than before. Play it.
3. **Stretch frame 5** into a tall oval. Play again. Ask: "Is it more fun? Does it look softer?"
4. **Show the onion skin** at frame 7: the drawings above are close together at the top and far apart near the ground. Name it: "Slow in and slow out at the top, no easing at the bottom."
5. **Add a shadow layer** under the ball and draw two shadows: small and pale at the top, big and dark at contact.
6. **Export a GIF** with **File → Export → Animated GIF...** and open it in a web browser.

<!-- SCREENSHOT: The ball at contact (frame 7) squashed flat on the ground with a dark shadow under it; onion skin showing round and stretched balls above it -->

## Step by Step {#steps}

### Make a copy of your ball {#steps-copy}

1. **File → Open** your Lesson 2 project (for example `lesson02-ball-yourname.pclx`).
2. Save a copy with **File → Save As...** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>) named `lesson03-ball-yourname.pclx`. Now you can change it freely and still keep the original.
3. Check the onion skin is on: in the **Onion Skins** panel, **Previous Frames** and **Next Frames** ticked, **Show Keyframes Only** ticked.

### Squash on the contact frame {#steps-squash}

4. Click the name **Ball** in the timeline. Then click above frame **7** in the frame-number row to go to the contact drawing.
5. Choose **Edit → Clear Frame** to erase the drawing on this keyframe.
6. Draw the squashed ball: the bottom sits flat on the ground line; the ball is lower and wider than the round ball. Use the onion skin of the round balls to keep the amount of ball about the same.
7. Play (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>, with **Loop** on). The ball should now "hit" the ground.

### Stretch on the fast frames {#steps-stretch}

8. Go to frame **5**, clear the frame, and draw the ball as a slightly tall oval, a bit narrower, stretched in the direction it's moving (up and down).
9. Do the same on frame **9**.
10. Leave frames **1**, **3**, **11** and **12** round. The ball is moving slowly there, so it keeps its normal shape.
11. Play it. Then go to frame 7 and choose **Animation → Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>). Pencil2D quickly flips between frames 5, 7 and 9 so you can check the change of shape.

> **Tip:** A little stretch goes a long way. If the ball looks like a sausage, make the stretch smaller. Exaggerate more only for a very soft ball.

### Check the easing {#steps-ease}

12. Stay on frame 7 and look at the red onion skin of frames 1, 3 and 5. The balls are close together at the top and far apart near the ground. That's the slow in and slow out at the top of the bounce.
13. If two drawings look evenly spaced, move the in-between: go to it, clear it and redraw it closer to the top.

### Add a shadow {#steps-shadow}

14. Choose **Layer → New Bitmap Layer** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd>), name it `Shadow` and click **OK**. It appears at the top of the layer list.
15. Put the layers in order by dragging their names up or down in the timeline. From top to bottom you want: **Ball**, **Shadow**, **Ground**, **Camera Layer**. Layers higher in the list are drawn in front. If you have a **Guide** layer from the Lesson 2 starter file, hide it.
16. Click **Shadow** to select it. Choose a medium grey: pick one in the **Color Palette**, or click the left edge of the square in the **Color Box**, where the greys are.
17. Choose the **Brush** (<kbd>B</kbd>) and set a large **Width** in the **Options** panel.
18. On frame 1, paint a small, flat oval on the ground line under the ball. The ball is high, so the shadow is small.
19. Go to frame **3**, press <kbd>F7</kbd>, and paint a slightly bigger shadow. Repeat on **5**, **7** (the biggest, right under the squashed ball), **9** and **11**. On frame 11 press <kbd>F6</kbd> to copy it to frame 12.
20. **Optional, softer shadow:** with the Shadow layer selected, choose **Layer → Layer / Keyframe opacity**. Under **Set opacity for:** choose **Layer**, set the value to 50 %, then click **Close**. Do this after drawing all the shadows: it changes the keyframes that exist now, not ones you add later.
21. Play it and save (<kbd>Ctrl</kbd>+<kbd>S</kbd>).

<!-- SCREENSHOT: Timeline showing layers Ball, Shadow, Ground, Camera Layer (top to bottom), with keyframes on 1, 3, 5, 7, 9, 11, 12 on Ball and Shadow -->

### Export an animated GIF {#steps-gif}

22. Save first (<kbd>Ctrl</kbd>+<kbd>S</kbd>).
23. Choose **File → Export → Animated GIF...**. The **Export Animated GIF** window opens.
24. Under **File**, click **Browse...**, go to your class folder, name the file `lesson03-ball-yourname.gif` and click **Save**.
25. Under **Range**, check that **Start Frame** is 1 and **End Frame** is 12. Make sure **Loop** is ticked.
26. Click **OK** and wait for the export to finish.
27. Open the GIF from your folder in a web browser. It should bounce forever at the same speed as in Pencil2D.

Only the part of the drawing inside the camera frame is exported, and hidden layers are left out. See [Exporting an animated GIF]({{ '/doc/manual/import-export.html#export-gif' | relative_url }}) for all the options.

## Practice Challenge {#challenge}

**Basic:** Finish the bounce with squash on contact, stretch on the fast frames, round drawings at the slow top, and a shadow that grows and darkens as the ball lands. Export it as a looping GIF.

**Stretch: bounce across the screen.** Start a new project (12 fps) and make the ball enter on the left and bounce three times to the right, each bounce lower and shorter than the one before, then roll to a stop.

1. Add a layer called `Guide` and draw the path of the ball: a row of arcs like the one in **Key Ideas**. Mark where each contact goes.
2. On a `Ball` layer, draw the contacts and the tops of each arc first (the keys), then the in-betweens on twos.
3. Squash on each contact, a little less each time as the ball loses energy. Ease at the top of each arc.
4. Hide the Guide layer before exporting: click the small round dot at the left of its name so it's empty. Hidden layers are not exported.

## Wrap-up {#wrap-up}

Open a few GIFs in a browser on the projector, side by side if you can. Questions:

- Which balls look soft and which look hard? What did the animator do differently?
- Did anyone overdo the stretch? How can you tell?
- Where does the ball ease, and where doesn't it? Why is the squash on the frame that has no easing?
- What does the shadow add? Could you tell how high the ball is without it?
- Where else do you see arcs? (Swinging arms, jumping characters, a pendulum, a thrown paper plane.)

## Assessment Checklist {#assessment}

| Look for | Met? |
|---|---|
| Squash on the contact frame, touching the ground | |
| Stretch on the fast frames only; round at the slow top | |
| The ball keeps about the same volume when it squashes and stretches | |
| Spacing shows slow in and slow out at the top | |
| A shadow layer below the ball that changes with the ball's height | |
| Layers named and in the right order | |
| A looping GIF was exported and plays in a browser | |
| Stretch challenge: the ball follows decreasing arcs | |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| **Clear Frame** erased the wrong drawing | You were on a frame without a keyframe, so it cleared the drawing held from an earlier keyframe | Undo (<kbd>Ctrl</kbd>+<kbd>Z</kbd>), go to the keyframe's frame, try again |
| The shadow covers the ball | The Shadow layer is above the Ball layer | Drag the **Ball** name to the top of the list |
| The ground line shows through the squashed ball | The Ground layer is above the Ball layer | Drag **Ball** above **Ground** |
| The shadow is the same on every frame | The Shadow layer only has one keyframe, which is held | Add a keyframe with <kbd>F7</kbd> on each ball frame and draw a new shadow |
| New shadows are darker than the old ones | Layer opacity only changed the keyframes that existed then | Set the layer opacity again after drawing |
| The squashed ball floats or sinks | Its bottom isn't on the ground line | Redraw it so the flat bottom sits exactly on the line |
| The ball looks like it grows at contact | The squash is wider but not flatter | Make it lower as well as wider |
| The GIF doesn't loop | **Loop** was unticked in the export window | Export again with **Loop** ticked |
| Part of the drawing is missing in the GIF | It was outside the camera frame, or on a hidden layer | Move the drawing inside the frame; show the layer |
| The GIF file is very large | The export resolution is large | Lower the **Width** and **Height** under **Resolution** when exporting |

If the export fails completely, see the [video export troubleshooting guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

## Going Further {#going-further}

- Animate three different balls with the same timing but different squash: a water balloon, a tennis ball and a bowling ball.
- Make the shadow softer with the Brush's **Feather** setting, or draw an outline and fill it with the Bucket (you'll learn it in the next lesson). See [Tools]({{ '/doc/manual/tools.html#brush' | relative_url }}).
- Read about [layer opacity]({{ '/doc/manual/layers.html#opacity' | relative_url }}) and [managing layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}).
- Watch a classic cartoon and freeze-frame a landing. Can you find the squash drawing?
- Next lesson: [Layers, Line and Color]({{ '/doc/course/lesson-04.html' | relative_url }}), where the ball gets clean lines and color.

{% include series-nav.html series=site.data.course %}
