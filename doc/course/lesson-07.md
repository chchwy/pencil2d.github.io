---
layout: page
title: "Lesson 7: The Walk Cycle"
tagline: Contact, down, passing, up, and a walk that loops forever
comments: false
---

A walk cycle is a short set of drawings that loops: after the last drawing, the first one follows
and the character keeps walking. It is one of the most useful things an animator can learn, and it
brings together what students already know about key poses, in-betweens, onion skin and timing. In
this lesson students build a side-view walk in place on 16 frames.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | One session, 60–90 minutes (clean-up and color can be homework or a second session) |
| **Level** | Intermediate, after Lessons 1–6 |
| **Animation principle** | Cycles; the four walk positions; weight shifting up and down; opposing arm and leg swing |
| **Pencil2D skills** | Guide layers, placing keyframes on twos, onion skin in both directions, **Flip Rolling**, **Loop** and **Range** playback, copy and paste of keyframes |
| **What students make** | A looping walk in place, 12–16 drawings, side view |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Name and draw the four walk positions: contact, down, passing and up.
2. Explain why the body goes up and down during a walk and why arms swing opposite to legs.
3. Build a cycle whose last drawing flows smoothly into the first.
4. Spot and fix common walk mistakes by playing the cycle in a loop.

## Before Class {#before-class}

- **Walk it yourself.** Walk slowly across the room and notice when your head is lowest and highest.
- **Materials:** a projected or printed copy of the positions table below; optionally a strip of
  masking tape on the floor for the demo walk.
- **Optional starter file** (`walk-start.pclx`, 12 fps) with two layers:
  - **Guide**: a ground line with evenly spaced tick marks, and three faint horizontal lines at head
    height (high, middle, low), all on frame 1;
  - **Rough**: an empty layer for the walk.
- Encourage **simple characters**: a stick figure or a bean-shaped body with stick legs. A detailed
  character slows students down and hides mistakes in the motion.

## Key Ideas {#key-ideas}

**A walk is a controlled fall.** You lean forward, start to fall, and catch yourself with a foot.
Then you do it again with the other foot. Every step has the same four positions:

| Position | Legs | Body | Arms |
|---|---|---|---|
| **Contact** | Both feet on the ground: front heel down, back toe down; the legs make a wide upside-down V | Middle height | Widest swing, opposite to the legs |
| **Down** | The front leg bends as it takes the weight; the back foot lifts | **Lowest** | Starting to swing back |
| **Passing** | The standing leg is straight under the body; the free leg passes it with the knee bent | Middle, rising | Passing the body |
| **Up** | The standing leg pushes off from its toes; the free leg reaches forward | **Highest** | Swinging toward the other side |

After **up** comes the next **contact**, with the other foot in front. Two steps, with left and right
swapped, make one full **cycle**.

**Opposition.** When the right leg is forward, the left arm is forward. Try walking with the same arm
and leg forward: it feels like a robot.

**The head bobs.** Drawn as a chart, the height of the head over one cycle looks like this:

```
frame:    1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16  1
pose:     C     D     P     U     C     D     P     U     C
high                        *                       *
                         .     .                 .     .
middle    *           *           *           *           *
             .     .                 .     .
low             *                       *
```

(C = contact, D = down, P = passing, U = up. Stars are key poses, dots are in-betweens. After frame
16 the cycle starts again at frame 1.)

**Walking in place.** In this lesson the character walks on the spot, like on a treadmill. The foot
on the ground slides backward at a steady speed, so the tick marks on the ground line help to space
it evenly.

**Timing.** At 12 fps, 16 frames make one cycle of 1⅓ seconds, a relaxed walk. Fewer frames per step
make a hurried walk, more make a slow stroll.

| Word | Meaning |
|---|---|
| Cycle | A set of drawings that loops smoothly |
| Contact, down, passing, up | The four positions of every step |
| Stride | The distance covered by one step |
| Opposition | Arms swinging opposite to the legs |
| Hitch | A visible jump where a loop joins up, often caused by a doubled drawing |

## Demo {#demo}

About 10 minutes.

1. **Slow-motion walk.** Walk slowly along the tape line. Freeze on each position while the class
   calls out its name: *contact, down, passing, up*. Ask: *"When was my head lowest?"* (On down,
   just after the foot lands.)
2. **The four poses.** In Pencil2D, draw stick-figure poses for one step on frames 1, 3, 5 and 7,
   talking through each one. Use onion skin (<kbd>O</kbd>) so the class sees you comparing drawings.
3. **The loop.** Explain that the second step is the same four poses with the legs and arms swapped.
   Tick **Range**, set 1 to 16, turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>) and play a finished
   cycle (yours from before class). Say: *"Watch the place where it loops. You shouldn't be able to
   see where it starts."*

## Step by Step {#steps}

Shortcuts are given for Windows and Linux. On macOS, use <kbd>Cmd</kbd> instead of <kbd>Ctrl</kbd>
and <kbd>Option</kbd> instead of <kbd>Alt</kbd>.

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the
> frame you want. The playhead shows the number of the frame it is on. A single click on a cell in a
> layer's track selects that keyframe; it does not move the playhead.

**Part A: Guides (5 minutes)**

1. Open the starter file, or create a new project at 12 fps with a layer called **Guide** and one
   called **Rough** above it. Save it as `walk-yourname.pclx`.
2. Without the starter file: on the **Guide** layer, frame 1, draw a ground line across the camera
   frame and three light horizontal lines at head height: high, middle and low. Optionally turn on the
   center overlay: **View → Overlays → Center**.

**Part B: The eight key poses (25 minutes)**

{: start="3"}
3. On the **Rough** layer, frame 1, draw **contact** with the character facing right and the **right**
   leg in front. Draw the far leg and far arm (the ones on the other side of the body) in a different
   color, so you never mix them up.
4. On the ground line, mark where the front heel is (A) and where the back toe is (B). On the ground,
   the front foot slides back from A to B over the next 8 frames. Add 7 evenly spaced tick marks
   between A and B on the **Guide** layer, one for each frame.
5. Turn on onion skin for previous frames (<kbd>O</kbd>). Go to frame **3**, press
   <kbd>F7</kbd> (**Animation → Add Frame**) and draw **down**: head on the low line, the right leg
   bent, its foot moved back two ticks.
6. Frame **5**, <kbd>F7</kbd>: **passing**. Frame **7**, <kbd>F7</kbd>: **up**, head on the high line.
7. Frame **9**, <kbd>F7</kbd>: **contact** again, but now with the **left** leg in front and the arms
   swapped. The planted right foot has reached B. Do **not** use **Edit → Selection → Flip X** to
   make this drawing: flipping turns the character around to face left.
8. Frames **11**, **13** and **15**: **down**, **passing** and **up** with the legs swapped.
9. Check the positions with **Flip Rolling** (<kbd>Alt</kbd>+<kbd>X</kbd>), which flips through the
   last few drawings before the playhead.

<!-- SCREENSHOT: Onion skin view of the eight key poses of a stick-figure walk (contact, down, passing, up, then the same with legs swapped) overlaid on a ground line with tick marks and three head-height guide lines -->

**Part C: The loop (10 minutes)**

{: start="10"}
10. Tick **Range** on the timeline and type **1** and **16** in the two boxes next to it. Without a
    range, playback stops at the last keyframe (frame 15), so that drawing would be shown for only
    one frame.
11. Turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>) and play (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). Each
    key pose is on screen for two frames ("on twos"). Watch the moment where frame 16 goes back to
    frame 1: it should look like every other step.
12. **Don't add a copy of frame 1 at the end.** Frame 1 already follows frame 16; a copy on frame 17
    would show the same pose twice and cause a hitch.

**Part D: In-betweens (20 minutes)**

{: start="13"}
13. Turn on onion skin for next frames too (<kbd>Alt</kbd>+<kbd>O</kbd>). Now you see the drawing
    before and after each gap.
14. Start with the in-betweens next to the passing positions, where the free leg moves fastest:
    frames **4**, **6**, **12** and **14**. Go to the frame, press <kbd>F7</kbd>, and draw.
    That gives 12 drawings.
15. If there is time, add frames **2**, **8**, **10** and **16** for 16 drawings. The walk now plays
    "on ones" and looks smoother.
16. Check each in-between with **Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>) before you move
    on: with the playhead on the in-between, Pencil2D flips it against its neighbors. Play the loop
    and save.

For more detail, see [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }}),
[Onion skin modes]({{ '/doc/manual/onion-skin.html#modes' | relative_url }}) and
[Copy and paste]({{ '/doc/manual/timeline.html#copy-paste' | relative_url }}).

### Optional: make it travel {#travel}

A walk in place can be turned into a walk through a scene in two ways. Both take extra time, so
treat them as an extension.

**A. Scroll the background.** The character stays in the middle of the screen and the world moves
past, as in many TV cartoons.

1. Make the walk longer by pasting the cycle. Save first, since pasting frames can't be undone yet.
   Click the first keyframe of the **Rough** track, <kbd>Shift</kbd>+click the last one,
   press <kbd>Ctrl</kbd>+<kbd>C</kbd>, go to frame **17** and press
   <kbd>Ctrl</kbd>+<kbd>V</kbd>. Change the **Range** to 1–32.
2. Draw a long background on a new layer below **Rough**, frame 1: a ground and some objects.
3. On the background layer, press <kbd>F6</kbd> (**Duplicate Frame**). The copy goes on the next
   frame. Press <kbd>Ctrl</kbd>+<kbd>A</kbd> (**Select All**), then move the selection left by the
   distance between two tick marks on the ground line (how far the planted foot slides each frame):
   drag it with the **Move** tool, or press the <kbd>Left</kbd> arrow key, which moves it one pixel
   per press. Press <kbd>Enter</kbd> to apply the move. Move it the same distance on every frame,
   and repeat up to frame 32.
4. Play. If the feet seem to skate, the background is moving faster or slower than the foot on the
   ground; change the distance.

**B. Walk across the scene and let the camera follow.** Paste the cycle as in A. Then, on each drawing
from frame 2 on, press <kbd>Ctrl</kbd>+<kbd>A</kbd> and use the **Move** tool to move the whole
drawing forward until the foot on the ground sits exactly on its onion-skin ghost from the frame
before, then press <kbd>Enter</kbd> to apply the move. Finally, give the camera a keyframe on frame 1 and on the last frame, framing the character
the same way on both. A walk has a steady speed, so leave the camera easing on **Linear**. See
[Lesson 6]({{ '/doc/course/lesson-06.html' | relative_url }}) for camera keyframes.

## Practice Challenge {#challenge}

**Basic:** A looping walk in place with the 8 key poses and at least 4 in-betweens (12 drawings),
with a clear up-and-down motion and opposing arms and legs.

**Stretch:** Choose one:

- Finish all 16 drawings, then clean them up on a **Line** layer and color them on a **Color** layer, as
  in Lesson 4.
- Give the walk a personality: a sneak (low, long steps), a proud strut (chest out, big up position),
  or a sad shuffle (head down, small steps, very little up and down).
- Make it travel, using one of the two methods above.

## Wrap-up {#wrap-up}

Put several walks on screen in a loop and watch them for a while. Loops show mistakes that a single
play-through hides.

Discussion questions:

- Where is the head lowest in your walk? Is it on the same position in every step?
- What changes when a character walks sadly or happily? Which of the four positions changes most?
- Did anyone's walk have a hitch where it loops? What caused it?
- Why do games and cartoons use cycles so much?

## Assessment Checklist {#assessment}

| Look for | Evidence |
|---|---|
| Four positions | Contact, down, passing and up can be seen in both steps |
| Up and down | Lowest on down, highest on up, consistently |
| Opposition | Arms swing opposite to the legs |
| Even foot slide | The planted foot moves back at a steady speed with no skating or sticking |
| Clean loop | No hitch or jump where frame 16 goes back to frame 1 |
| Drawing count | At least 12 drawings, placed as planned on the timeline |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| The walk looks like marching | Arm and leg on the same side swing forward together | Swap the arms in the second step |
| The character floats | No up and down, or the lowest point is on passing | Put the head on the low line on down and the high line on up |
| Legs swap places halfway through the cycle | Near and far legs got mixed up | Use a different color for the far leg and far arm |
| The character turned around in the second step | The drawing was flipped with **Flip X** | Redraw it facing the same way, with the legs swapped |
| A hitch where the loop restarts | A copy of frame 1 was added at the end, or the range is wrong | Delete the extra drawing; set **Range** to 1–16 |
| The last drawing flashes for one frame | Playback ends at the last keyframe | Tick **Range** and set the end to 16 |
| Feet skate or slide unevenly | The planted foot doesn't move the same distance every frame | Use the tick marks on the ground line |
| A new drawing appeared on the wrong frame or changed an old one | The playhead wasn't where you thought, or <kbd>F7</kbd> was skipped | Go to the frame first, then press <kbd>F7</kbd>; undo with <kbd>Ctrl</kbd>+<kbd>Z</kbd> |
| The character grows or shrinks | Drawings drift in size | Keep the head between the guide lines; use onion skin |

## Going Further {#going-further}

- Animate a run: the body leans forward, there is a moment where both feet are off the ground, and
  a cycle often has only 8 frames at 12 fps.
- Try a four-legged walk (a dog or a cat). Watch a video of an animal walking frame by frame first.
- *The Animator's Survival Kit* by Richard Williams covers walks in great depth.
- Next: [Lesson 8: Sound and Lip Sync]({{ '/doc/course/lesson-08.html' | relative_url }}).

{% include series-nav.html series=site.data.course %}
