---
layout: page
title: "Lesson 5: The Flour Sack Jump"
tagline: Anticipation, follow-through and weight, with a sack of flour as the actor
comments: false
---

Students animate a half-full flour sack that crouches, jumps, lands and settles. The sack has no face,
arms or legs, so all of its personality comes from posing and timing. That makes it a good exercise
for anticipation, follow-through and weight. Students also learn to change timing on the timeline
without redrawing anything.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | One session, 60–90 minutes |
| **Level** | Beginner, after Lessons 1–4 |
| **Animation principle** | Anticipation, follow-through and overlapping action, weight |
| **Pencil2D skills** | Posing on keyframes, **Add Exposure** / **Subtract Exposure**, selecting and dragging keyframes, **Flip In-Between**, playback **Range** |
| **What students make** | A 2–3 second jump of a flour sack, plus one timing variation of it |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Explain anticipation, follow-through and overlapping action in their own words.
2. Plan an action as six key poses before drawing any in-betweens.
3. Change the timing of an animation by lengthening and shortening drawings on the timeline.
4. Describe how timing changes the apparent weight of an object.

## Before Class {#before-class}

- **Try the exercise yourself** (about 30 minutes). Your own rough jump is the best demo.
- **Props:** a bean bag, a sock loosely filled with rice, or a small cloth bag. Dropping it on a desk
  shows follow-through better than any drawing.
- **Print or project** the key-pose table and the timing plan below.
- **Optional starter file** (`flour-sack-start.pclx`): a project at 12 fps with a layer named
  **Ground** (a horizontal line across the lower third of the camera frame on frame 1) and an empty
  layer named **Sack** above it. Copy it to each computer or a shared folder.
- **Check** that the frame rate box on the timeline says **12 fps**. All frame numbers in this lesson
  assume 12 fps.

## Key Ideas {#key-ideas}

**The flour sack.** Imagine a cloth sack, half full of flour, with two corners sticking up like ears.
It can squash, stretch and bend in the middle, but the amount of flour inside never changes. Keep the
sack the same size overall, as with the ball in [Lesson 3]({{ '/doc/course/lesson-03.html' | relative_url }}).

**Anticipation** is a small movement in the opposite direction before the main action. You can't
jump without crouching first. Anticipation gives the action power, and it tells the audience that
something is about to happen. A longer crouch makes the audience expect a bigger jump.

**Follow-through** means that parts of a body keep moving after the main body stops. When the sack
lands, its corners carry on downward, then spring back. **Overlapping action** (or **drag**) means
that the parts don't all move at the same time: when the sack shoots up, its corners trail behind and
catch up later.

**Weight** is shown by timing and by how much things squash. A heavy sack needs a long crouch to get
off the ground, doesn't go very high, lands with a big squash and takes a while to settle. A light
sack pops up quickly and floats at the top.

| Word | Meaning |
|---|---|
| Key pose | A drawing that tells the story of the action (crouch, peak, land) |
| In-between | A drawing that connects two key poses |
| Pose test | Playing only the key poses to check that they read clearly |
| Hold | A drawing that stays on screen for several frames |
| Exposure | How many frames a drawing stays on screen |
| On ones / on twos | Each drawing shown for 1 frame / for 2 frames |

The six key poses:

| # | Pose | What it looks like | Corners (ears) |
|---|---|---|---|
| 1 | Stand | Relaxed, upright, bottom on the ground | Up |
| 2 | Crouch | Squashed low and wide, top bent forward | Flopped forward |
| 3 | Launch | Stretched tall and thin, bottom just leaving the ground | Dragging behind, pointing down |
| 4 | Peak | Highest point, round, relaxed | Catching up, lifting |
| 5 | Land | Squashed flat on the ground, wider than the crouch | Still moving down and forward |
| 6 | Settle | Back to the stand pose | Up again |

<!-- SCREENSHOT: A pose sheet showing the six flour sack key poses side by side on a ground line, numbered 1 to 6, with arrows showing the direction the corners move -->

## Demo {#demo}

About 10 minutes.

1. **Jump without anticipation.** Ask a volunteer to jump without bending their knees first. They
   can't. Say: *"Every big action starts with a small action the other way. Animators call it
   anticipation."*
2. **Drop the bean bag** on a desk. Ask: *"Did it stop all at once?"* Point out how the loose parts
   keep moving after the bag lands. That is follow-through.
3. **Pose test in Pencil2D.** Draw six quick sack poses on frames 1–6, one per frame. Turn on
   **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>) and **Play** (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). It
   flashes by far too fast. Say: *"The poses are right, but the timing is wrong. We fix timing
   without redrawing."*
4. **Time it live.** Put the playhead on the crouch and press <kbd>Ctrl</kbd>+<kbd>+</kbd> a few
   times. Everything after the crouch moves to the right. Play again: the jump now has a wind-up.
5. **Flip In-Between.** Add one in-between and press <kbd>Alt</kbd>+<kbd>Z</kbd> to flip it against
   its neighbors, the way animators flip paper.

<video src="{{ '/images/pencil2d-0.7.0-timeline-keyframe-exposure-showcase.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## Step by Step {#steps}

Shortcuts are given for Windows and Linux. On macOS, use <kbd>Cmd</kbd> instead of <kbd>Ctrl</kbd>
and <kbd>Option</kbd> instead of <kbd>Alt</kbd>. On a laptop you may need to hold <kbd>Fn</kbd> for
<kbd>F7</kbd>.

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the
> frame you want. Only some frames are numbered there (1, 12, 24, ...), but the playhead shows the
> number of the frame it is on. You can also step with <kbd>.</kbd> and <kbd>,</kbd>. A single click
> on a cell in a layer's track selects that keyframe; it does not move the playhead.

**Part A: Set up (5 minutes)**

1. Open the starter file, or start a new project with **File → New** (<kbd>Ctrl</kbd>+<kbd>N</kbd>).
   Save it right away with **File → Save As...** as `jump-yourname.pclx`.
2. Without the starter file: add two layers with **Layer → New Bitmap Layer**
   (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd>), called **Ground** and **Sack**. To rename a layer,
   double-click its name in the timeline. On the **Ground** layer, draw a horizontal line across the
   lower part of the camera frame on frame 1. That single drawing stays on screen for the whole
   animation.

**Part B: Key poses (20 minutes)**

{: start="3"}
3. Click the **Sack** layer. On frame 1, draw pose 1, **Stand**, standing on the ground line. Make the
   sack about a third as tall as the camera frame, and give it two corners at the top.
4. Turn on onion skin for the previous frame: press <kbd>O</kbd>.
5. Go to frame **2**, then press <kbd>F7</kbd>
   (**Animation → Add Frame**). Draw pose 2, **Crouch**. Keep the bottom on the ground line and keep
   the sack about the same size overall: lower means wider.
6. Do the same on frame 3 (**Launch**), frame 4 (**Peak**, up in the air) and frame 5 (**Land**).
7. For pose 6, **Settle**, reuse the stand pose. Save first (<kbd>Ctrl</kbd>+<kbd>S</kbd>), because
   pasting frames can't be undone yet. Click the keyframe on frame 1 of the **Sack** track to select
   it, press <kbd>Ctrl</kbd>+<kbd>C</kbd>, go to frame **6**, and press
   <kbd>Ctrl</kbd>+<kbd>V</kbd>. Then press <kbd>Ctrl</kbd>+<kbd>D</kbd> (**Edit → Deselect All**)
   so that no keyframe stays selected.
8. **Pose test:** turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>) and press **Play**
   (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). It will be too fast. That's fine. Check that each pose is
   clear, then stop playback.

**Part C: Timing with exposure (15 minutes)**

Exposure changes how long a drawing stays on screen. The keyframes after it slide along to make room.
With nothing selected, **Add Exposure** acts on the drawing shown at the playhead. If keyframes are
selected, it acts on those instead.

{: start="9"}
9. Go to frame **1**. Press <kbd>Ctrl</kbd>+<kbd>+</kbd> five times (or use
   **Animation → Timeline Selection → Add Exposure**). The stand pose now lasts 6 frames.
10. Press <kbd>Alt</kbd>+<kbd>.</kbd> (**Next Keyframe**) to jump to the crouch. Add exposure to each
    pose according to this table. The extra frames make room for in-betweens later.

    | Pose | Press <kbd>Ctrl</kbd>+<kbd>+</kbd> | Ends up on frame |
    |---|---|---|
    | 1 Stand | 5 times | 1 |
    | 2 Crouch | 2 times | 7 |
    | 3 Launch | 1 time | 10 |
    | 4 Peak | 3 times | 12 |
    | 5 Land | 3 times | 16 |
    | 6 Settle | (not needed) | 20 |

11. Playback stops at the last keyframe, so the settle pose would flash for only one frame. Tick
    **Range** on the timeline and set the two boxes next to it to **1** and **30**. Play the loop.

**Part D: In-betweens and follow-through (20 minutes)**

{: start="12"}
12. Turn on onion skin for the next frame too: press <kbd>Alt</kbd>+<kbd>O</kbd>. You now see the
    drawings before and after.
13. Add four in-betweens. For each one, go to the frame, press <kbd>F7</kbd> and draw:

    | Frame | In-between | Corners |
    |---|---|---|
    | 5 | Half-way down into the crouch | Starting to flop forward |
    | 11 | Rising, still stretched | Trailing far behind, pointing down |
    | 15 | Falling, stretched a little | Flicked upward by the fall |
    | 18 | Recoil after landing, slightly taller than stand | Flopping down and forward, the follow-through |

14. Frame 18 is not exactly half-way between its neighbors, and that's on purpose. The body has
    stopped but the corners haven't. Follow-through drawings often break the "half-way" rule.
15. Check each in-between with **Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>). Put the playhead
    on the in-between (for example frame 11); Pencil2D flips it against the keyframes before and
    after it.
16. Play the loop and save (<kbd>Ctrl</kbd>+<kbd>S</kbd>).

<!-- SCREENSHOT: Pencil2D timeline for the finished jump: the sack layer with keyframes on frames 1, 5, 7, 10, 11, 12, 15, 16, 18 and 20, Range ticked with 1 to 30 -->

**Part E: Timing experiment (10 minutes)**

{: start="17"}
17. Choose **File → Save As...** and save a copy as `jump-heavy-yourname.pclx`. From now on you are
    editing the copy.
18. Make the sack heavier. Give the crouch 2 more frames, take 2 frames away from the peak with
    **Subtract Exposure** (<kbd>Ctrl</kbd>+<kbd>-</kbd>), and give the land pose 2 more frames.
    Play it. Compare it with the first version.
19. **Another way to move drawings:** <kbd>Alt</kbd>+click a keyframe to select it and every keyframe
    after it, then drag the selection left or right. You can't drop keyframes on top of other
    keyframes.

> **Tip:** If <kbd>Ctrl</kbd>+<kbd>+</kbd> does nothing on your keyboard, use the menu:
> **Animation → Timeline Selection → Add Exposure**.

For more detail, see [Changing exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}),
[Selecting keyframes]({{ '/doc/manual/timeline.html#selecting-frames' | relative_url }}) and
[Onion skin modes]({{ '/doc/manual/onion-skin.html#modes' | relative_url }}).

## Practice Challenge {#challenge}

**Basic:** Finish the jump with six key poses, the four in-betweens and corners that show
follow-through. Save one timing variation (heavy or light) as a second file.

**Stretch:** Make the sack jump *forward* onto a box drawn on the **Ground** layer. It needs a bigger
anticipation, and it lands on a higher level. Or give the sack a mood: a tired sack does a small,
slow hop, and an excited sack does a big bouncy jump. The poses are the same; only the timing and how
far it squashes and stretches change.

## Wrap-up {#wrap-up}

Play the jumps back to back on the projector, or have students walk around and watch each other's
screens. For a few, play the original and the heavy version one after the other.

Discussion questions:

- Which jump feels heaviest? What did the animator change to make it feel that way?
- What happens if you remove the crouch? (Try it: select the crouch keyframe and subtract exposure
  until it lasts one frame.)
- Where else do you see anticipation? (A pitcher winding up, a cartoon character before running off.)
- Why do the corners keep moving after the sack has landed?

## Assessment Checklist {#assessment}

| Look for | Evidence |
|---|---|
| Anticipation | A crouch that is held long enough to notice before the launch |
| Squash and stretch | Stretched on launch and fall, squashed on crouch and landing |
| Volume | The sack doesn't obviously grow or shrink between poses |
| Follow-through / overlap | Corners trail on the way up and keep moving after the landing |
| Timing control | At least one variation made with exposure, not by redrawing |
| Explanation | Student can say how the variation changed the feeling of weight |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| Drawing on a frame changed an earlier drawing | That frame had no keyframe, so the drawing went onto the previous keyframe | Undo (<kbd>Ctrl</kbd>+<kbd>Z</kbd>), press <kbd>F7</kbd> first, then draw |
| Clicking a keyframe doesn't move to that frame | A single click in a track selects the frame | Click in the frame-number row above the frame instead |
| <kbd>Ctrl</kbd>+<kbd>+</kbd> changed the wrong drawing | Exposure works on the selected keyframes, or on the one at the playhead | Deselect with <kbd>Ctrl</kbd>+<kbd>D</kbd>, put the playhead on the right drawing, try again |
| Exposure moved the sack but not the ground | Exposure only changes the current layer | That's expected here; the ground is one held drawing |
| The last pose flashes and the loop jumps | Playback ends at the last keyframe | Tick **Range** and set the end frame a few frames later |
| Pasted frames landed in the wrong place | Frames paste at the playhead; paste can't be undone yet | Remove the extra keyframe with **Animation → Remove Frame** (<kbd>Shift</kbd>+<kbd>F5</kbd>) |
| The sack looks floaty | Peak is held too long | Subtract exposure from the peak |
| The jump has no punch | The crouch is too short, or the launch is held too long | Lengthen the crouch; keep the launch to 1 frame |

## Going Further {#going-further}

- Add a tail or a rope to the sack. It will follow through even more than the corners.
- Try the same jump at 24 fps with each drawing on twos (held 2 frames). Does it look different?
- Read [Timeline and Animation]({{ '/doc/manual/timeline.html' | relative_url }}) for more timeline tools, such as
  **Move Frame Forward** and **Reverse Frames Order**.
- Books for teachers who want more: *The Animator's Survival Kit* by Richard Williams, and *The
  Illusion of Life* by Frank Thomas and Ollie Johnston, which made the flour sack famous.
- Next: [Lesson 6: Camera Moves]({{ '/doc/course/lesson-06.html' | relative_url }}) puts a camera to work.

{% include series-nav.html series=site.data.course %}
