---
layout: page
title: "Lesson 2: The Bouncing Ball"
tagline: Timing and spacing, onion skin, and drawing keys before in-betweens
comments: false
---

The bouncing ball is the first exercise almost every animator learns, because it teaches the two most important ideas in animation: **timing** (how long an action takes) and **spacing** (how far something moves from one drawing to the next). Students plan the key positions first, fill in the in-betweens with the help of onion skin, and end up with a one-second looping bounce.

> **Note:** On macOS, use <kbd>Cmd</kbd> wherever this lesson says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> for <kbd>Alt</kbd>. On many laptops, <kbd>F6</kbd> and <kbd>F7</kbd> need <kbd>Fn</kbd> held down.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | 75–90 minutes |
| **Level** | Beginner (after Lesson 1) |
| **Animation principle** | Timing and spacing |
| **Pencil2D skills** | Renaming and adding layers, onion skin settings, setting the frame rate, placing keyframes on chosen frames, duplicating and moving keyframes, looping |
| **What students make** | A ball bouncing in place, looping once per second |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Explain the difference between timing and spacing.
2. Explain why a falling ball's drawings get further apart as it falls.
3. Draw the key positions first, then the in-betweens.
4. Use onion skin to see the drawings before and after the one they're drawing.
5. Put a keyframe on a chosen frame, and move keyframes to change the timing.
6. Describe what changes when the frame rate goes from 12 to 24 fps.

## Before Class {#before-class}

- Work through **Step by Step** yourself (about 20 minutes).
- Draw a spacing chart like the one in **Key Ideas** on the board.
- **Optional starter file** (`lesson02-start.pclx` in the starter folder). Make it in five minutes: start a new project, set 12 fps, rename **Bitmap Layer** to **Ball**, add a bitmap layer named **Ground** with a ground line near the bottom of the camera frame on frame 1, then add a bitmap layer named **Guide**. On the Guide layer, frame 1, draw a vertical line from near the top down to the ground line. Divide the vertical line into 9 equal steps with small tick marks, and write "1" at the top, "3" at the first tick, "5" at the fourth tick and "7" on the ground. Save it. With this file, students skip steps 1–5, and can hide the Guide layer once the ball is drawn.
- **Optional:** a real rubber ball to drop in front of the class.

## Key Ideas {#key-ideas}

**Timing** is *how many frames* an action takes. At 12 frames per second, a fall that takes 6 frames lasts half a second. More frames means slower; fewer frames means faster. Timing tells us about weight and mood: a balloon floats down slowly; a bowling ball drops fast.

**Spacing** is *how far* the object moves between one drawing and the next.

- Drawings **close together** mean the ball moves **slowly** at that moment.
- Drawings **far apart** mean it moves **fast**.

A dropped ball **speeds up** as it falls, because gravity pulls it faster and faster. So its drawings start close together at the top and get further apart near the ground. On the way back up it **slows down**, so the spacing shrinks again. A handy rule: if the ball falls 1 step between the first two drawings, it falls 3 steps between the next two, then 5.

The spacing chart for the fall, drawn on twos (one drawing every 2 frames):

```
frame 1   O   <- key: top of the bounce
frame 3   O   <- in-between: 1 step down
          :
          :
frame 5   O   <- in-between: 3 more steps
          :
          :
          :
          :
frame 7   O   <- key: contact with the ground (5 more steps)
---------------- ground
```

**Key poses and in-betweens.** Animators draw the most important positions first: the **keys** (here, the top and the contact). Then they draw the **in-betweens** that go from one key to the next. Working this way keeps the timing under control.

| Word | Meaning |
|---|---|
| **Timing** | How many frames an action takes |
| **Spacing** | How far the object moves between drawings |
| **Key (key pose)** | A main, important drawing, such as the top and bottom of the bounce |
| **In-between** | A drawing that goes between two keys |
| **On ones / on twos** | A new drawing every frame / every second frame |
| **Hold (exposure)** | One drawing staying on screen for several frames |
| **Frame rate** | Frames per second. 24 fps is the film standard; 12 fps is common for hand-drawn animation |

**What to say:** "Timing is *when* things happen. Spacing is *how fast* they move in between. A ball that falls with even spacing looks like it's on a string. A ball that speeds up looks like it has weight."

## Demo {#demo}

About 10 minutes on the projector.

1. **Drop a real ball** (or play a slow-motion clip). Ask: "Where is it slow? Where is it fast?"
2. **Draw the spacing chart** on the board and explain the 1, 3, 5 steps.
3. In Pencil2D, **show the two keys**: the ball at the top on frame 1, then click above frame **7** in the frame-number row, press <kbd>F7</kbd> and draw the ball on the ground. Play it: "Keys only. It jumps, but the timing is already there."
4. **Turn on onion skin** in the **Onion Skins** panel, tick **Show Keyframes Only**, and show both keys at once.
5. **Add one in-between** on frame 5, a bit less than halfway down. Point out that the gap below it, to the ground, is the biggest one.
6. **Change the fps** from 12 to 24 and play. Ask: "Same drawings, what changed?"

![A bouncing ball at frame 5 with red and blue onion skins, and the Onion Skins panel on the left]({{ "/images/manual/main-window.png" | relative_url }})

*Onion skin on: earlier drawings are red and later ones blue. This ball is on twos, with keyframes on frames 1, 3, 5, 7 and 9.*

## Step by Step {#steps}

### Set up the project {#steps-setup}

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the frame you want. Only some frames are numbered there (1, 12, 24, ...), but the playhead shows the number of the frame it is on. You can also step with <kbd>.</kbd> and <kbd>,</kbd>. Clicking a cell in a layer's row only selects it; it doesn't move the playhead.

If your teacher gave you a starter file, open it with **File → Open**, save your own copy with **File → Save As...**, and skip to step 6.

1. Start a new project: **File → New** (<kbd>Ctrl</kbd>+<kbd>N</kbd>). Save it straight away with **File → Save** (<kbd>Ctrl</kbd>+<kbd>S</kbd>) as `lesson02-ball-yourname.pclx` in your class folder.
2. Check the frame rate box in the timeline says **12 fps**. If not, click in it and type 12.
3. Rename the drawing layer: double-click the name **Bitmap Layer** in the timeline. In the **Layer Properties** window, type `Ball` and click **OK**.
4. Add a layer for the ground: **Layer → New Bitmap Layer** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd>). Name it `Ground` and click **OK**. The new layer appears at the top of the list and is selected.
5. On the Ground layer, frame 1, draw a straight ground line near the bottom of the camera frame. Because it's a keyframe on frame 1, it stays visible for the whole animation.
6. Click the name **Ball** so the Ball layer is selected. Check this every time before you draw!

### Turn on onion skin {#steps-onion}

7. In the **Onion Skins** panel, tick **Previous Frames** and **Next Frames**. (The shortcuts are <kbd>O</kbd> and <kbd>Alt</kbd>+<kbd>O</kbd>, also in **View → Onion Skin**.)
8. Tick **Show Keyframes Only**, so onion skin shows your *drawings*, not every frame.
9. Set the number next to **Previous Frames** to 3 and the number next to **Next Frames** to 1.
10. Click the small red button in the Previous Frames group and the blue button in the Next Frames group. Earlier drawings now show in red and later ones in blue.

### Draw the keys {#steps-keys}

11. On frame 1 of the Ball layer, draw the ball high up, near the top of the camera frame. Make it about the size of a coin on the screen and keep it simple: a circle, maybe with a stripe.
12. Go to frame **7**. Then press <kbd>F7</kbd> (**Animation → Add Frame**) to add a keyframe there.
13. Draw the ball directly below the first one, sitting on the ground line. The red onion skin of frame 1 helps you keep the same size.
14. Play it (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). The ball jumps between two places. That's fine: the keys are done.

### Draw the in-betweens {#steps-inbetweens}

15. Go to frame **5** and press <kbd>F7</kbd>. Draw the ball a bit *less than halfway* down from the top ball to the ground ball. (On the spacing chart it's 4 of the 9 steps down.)
16. Go to frame **3** and press <kbd>F7</kbd>. Draw the ball just a little below the top one (1 step down).
17. Press <kbd>Ctrl</kbd>+<kbd>Enter</kbd>. The ball should now speed up as it falls.
18. Now the way back up, which mirrors the way down. Go to frame **9**, press <kbd>F7</kbd> and draw the ball at the same height as frame 5. Onion skin shows frame 5 in red to trace over.
19. Go to frame **11**, press <kbd>F7</kbd> and draw the ball at the same height as frame 3.
20. Pencil2D stops playing at the last keyframe, so frame 11 would only show for one frame. To give it its second frame, stay on frame 11 and press <kbd>F6</kbd> (**Animation → Duplicate Frame**). A copy appears on frame 12.

Your timeline now has Ball keyframes on frames 1, 3, 5, 7, 9, 11 and 12.

<!-- SCREENSHOT: Timeline of the finished lesson: Ground layer with one keyframe at frame 1, Ball layer with keyframes on 1, 3, 5, 7, 9, 11, 12; loop button on; 12 fps -->

### Loop it and test the frame rate {#steps-play}

21. Turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>, or the Loop button) and play. The ball should bounce smoothly once per second.
22. Watch for jumps. If one drawing looks out of place, go to it and fix it with the Eraser and Pencil, using onion skin to compare.
23. Change the fps box to **24** and play. The same 12 frames now last half a second, so the ball bounces twice as fast. Try **6**: it's slow and choppy.
24. Set it back to **12** and save (<kbd>Ctrl</kbd>+<kbd>S</kbd>).

### Experiment with holds {#steps-holds}

25. Hold <kbd>Alt</kbd> and click the keyframe on frame 3 in the Ball row. This selects it and every keyframe after it.
26. Without letting go of the mouse button, drag them 2 frames to the right. Now the top drawing is held for 4 frames instead of 2. Play it: the ball seems to hang in the air.
27. Discuss with your neighbor: does it look better or worse? Then drag the selected keyframes back 2 frames to the left and click an empty part of the timeline to deselect.

> **Tip:** Undo (<kbd>Ctrl</kbd>+<kbd>Z</kbd>) is reliable for drawing. For timeline changes such as moving keyframes, fix things by hand: drag them back, or remove an extra keyframe with **Animation → Remove Frame**.

## Practice Challenge {#challenge}

**Basic:** Finish the one-second bounce so it loops smoothly with no jumps, speeds up as it falls and slows down as it rises. Save it.

**Stretch:** Make a second ball with **different timing** to show a different weight, on a new layer or in a new project:

- A **heavy ball**, such as a bowling ball: falls fast (keys on frames 1 and 5) and bounces only a little.
- A **light ball**, such as a balloon or beach ball: falls slowly (keys on frames 1 and 11), with smaller spacing changes.

Play them side by side and ask a classmate to guess which is which.

## Wrap-up {#wrap-up}

Play several bounces on the projector with loop on. Questions to ask:

- Which balls feel heavy, and which feel light? Is that timing, spacing, or both?
- Where are the drawings closest together? Why there?
- What happened when you changed 12 fps to 24 fps? How could you make a 24 fps animation that is the same speed as your 12 fps one? (Answer: use twice as many frames.)
- What did the hold at the top do? Where might a hold be a good idea?

## Assessment Checklist {#assessment}

| Look for | Met? |
|---|---|
| The ball layer and ground layer are named and the drawings are on the right layer | |
| Keys at the top and contact; in-betweens drawn after | |
| Spacing gets wider as the ball falls and narrower as it rises | |
| The ball keeps the same size and shape in every drawing | |
| The loop plays smoothly with no flash or jump at the loop point | |
| The student can explain timing and spacing in their own words | |
| Saved as `.pclx` in the class folder | |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| The ball was drawn on the Ground layer | The wrong layer was selected (the <kbd>↑</kbd> and <kbd>↓</kbd> arrow keys also change layer) | Undo, click **Ball**, draw again |
| The ground line disappears on some frames | Extra keyframes were added to the Ground layer, and they are blank | Click each extra block in the Ground row and use **Animation → Remove Frame** (<kbd>Shift</kbd>+<kbd>F5</kbd>) |
| Drawing changed an earlier ball | No keyframe on that frame, so Pencil2D drew on the previous one | Undo, press <kbd>F7</kbd>, draw again |
| <kbd>F7</kbd> put the keyframe one frame too late | The current frame already had a keyframe, so the new one went right after it | Remove it with <kbd>Shift</kbd>+<kbd>F5</kbd>, go to the right frame, press <kbd>F7</kbd> |
| Onion skin is confusing or missing | Previous/Next is off, or it's showing every frame | Tick **Previous Frames** and **Next Frames**, tick **Show Keyframes Only** |
| A hitch or flash where the loop restarts | Playback ends at the last keyframe | Duplicate the last drawing with <kbd>F6</kbd> as in step 20 |
| The ball jumps in size or shape | Drawings weren't traced from each other | Use onion skin to match the size; redraw the odd one |
| The animation suddenly plays at the wrong speed | The fps box was changed, for example by scrolling over it | Type 12 in the fps box |
| Play starts from the middle | Playback starts from the current frame | Go to frame 1 first, or just turn on Loop |

## Going Further {#going-further}

- Animate the ball on **ones** (a drawing on every frame) at 24 fps and compare how smooth it is.
- Try **Animation → Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>) on an in-between: it flips between the drawings before and after, like an animator flipping paper.
- Read about [onion skin modes]({{ '/doc/manual/onion-skin.html#modes' | relative_url }}), [frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}) and [exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}), including **Add Exposure** for making holds.
- Next lesson: [Squash, Stretch and Easing]({{ '/doc/course/lesson-03.html' | relative_url }}), where the ball gets bouncy and gets a shadow.

{% include series-nav.html series=site.data.course %}
