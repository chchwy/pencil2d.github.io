---
layout: page
title: "Lesson 6: Camera Moves"
tagline: Pan across a wide scene and push in for a close-up, with the camera layer
comments: false
---

Students draw a background that is much wider than the screen and let the camera travel across it.
The shot ends with a zoom in on a character. It is the first lesson where students direct a shot
instead of animating drawings, so it comes with a short introduction to film grammar: why a film
opens wide and then moves in close.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | One session, 60–90 minutes (a detailed background can take a second session) |
| **Level** | Beginner, after Lessons 1–5 |
| **Animation principle** | Staging and slow in / slow out, applied to the camera; film grammar |
| **Pencil2D skills** | The camera layer, **Camera Properties** (camera size), camera keyframes, panning / zooming / rotating with the Move tool on the camera layer, easing, **Show path**, exporting a movie |
| **What students make** | A 6-second shot: an establishing shot, a pan across a wide background, and a zoom in to a close-up of a character, exported as MP4 |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Explain the difference between the canvas (where you draw) and the camera (what the audience sees).
2. Set the camera size, and make camera keyframes that pan and zoom.
3. Use easing so that camera moves start and stop smoothly.
4. Name three shot types (establishing shot, medium shot, close-up) and say what each one is for.

## Before Class {#before-class}

- **Try it yourself** with the steps below. The camera takes a few minutes to get used to.
- **Pick a film clip** (30–60 seconds) that opens on a wide view of a place and then moves closer to
  a character. Many animated feature films open this way.
- **Decide the camera size.** This lesson uses **1280 × 720** (widescreen HD). Whatever you choose,
  keep both numbers even, because MP4 export requires it.
- **Optional starter file** (`camera-start.pclx`): camera size set to 1280 × 720, a **Background**
  layer with a simple landscape about three camera-widths wide (ground line, hills, a tree, a house),
  and a **Character** layer with a figure standing near the right end. With the starter file, students
  can go straight to Part C, which is useful when time is short.

## Key Ideas {#key-ideas}

**Canvas and camera.** Pencil2D's canvas has no edges; you can draw anywhere. The **camera frame**
is the rectangle that decides what ends up in the movie. The area outside it is shaded gray: that is
"off stage". Because you can draw off stage, you can draw a scene much bigger than the screen and
move the camera around inside it.

**Camera moves** (all made with the **Move** tool on the camera layer):

| Move | What you do in Pencil2D | What it's good for |
|---|---|---|
| **Pan** | Drag inside the camera frame | Following action, revealing a place bit by bit |
| **Zoom in** (push in) | Drag a corner handle inward | Drawing attention, showing emotion |
| **Zoom out** (pull back) | Drag a corner handle outward | Revealing the surroundings, a surprise |
| **Rotate** (Dutch angle) | Drag the round handle above the frame | Unease, dizziness, a comic effect; use sparingly |

**Film grammar.** Films are built from shot types, and the camera moves between them:

| Shot | Shows | Why |
|---|---|---|
| Establishing shot (wide) | The whole place | Tells the audience *where* we are |
| Medium shot | A character from the waist up | Action and body language |
| Close-up | A face | Tells the audience *how the character feels* |

A classic opening goes from an establishing shot to a close-up, often with a pan or zoom in between.
Every camera move should have a reason, and a short **hold** before and after a move gives the
audience time to take in each view.

**Easing.** A real camera operator starts and stops a move gently. This is slow in / slow out
from [Lesson 3]({{ '/doc/course/lesson-03.html' | relative_url }}), applied to the camera. Pencil2D moves the camera at a
constant speed unless you choose an easing. In Pencil2D's easing menu, **In** means the move starts
slowly and speeds up (what Lesson 3 calls *slow out*), **Out** means it slows down as it arrives
(*slow in*), and **In-Out** does both. The words are easy to mix up, so watch the dots on the camera path: close-together dots mean slow,
spread-out dots mean fast.

**Resolution.** The camera size is the size of your movie in pixels. When you zoom the camera in
past 100%, the frame outline on the canvas turns red. Your drawing is being enlarged, and bitmap
lines start to look soft. To avoid that, draw the close-up subject large enough that the close-up
needs no more than 100%, and zoom the camera *out* for the wide shots.

## Demo {#demo}

About 10 minutes.

1. **Play the film clip.** Ask: *"Where does the camera start? Where does it end up? Why?"*
2. **Show the camera frame.** In Pencil2D, zoom the view out with the mouse wheel. Say: *"Everything
   in the gray area is off stage. Only what's inside the frame goes into the movie."*
3. **Handles.** Click the camera layer, choose the **Move** tool (<kbd>M</kbd>), and drag the frame,
   a corner and the round rotate handle. Point out the second rectangle labeled **100%** and how
   the frame turns red when you zoom in past it.
4. **Two keyframes.** Add a camera keyframe later on the timeline, move the camera, and play. Say:
   *"Notice how it starts and stops like a robot."* Right-click the first keyframe and choose
   **Easing → In-Out → Slow**, then play again.
5. **Show path.** Tick **Show path** in the **Options** panel and point out how the dots bunch up at
   both ends of the eased move.

<video src="{{ '/images/pencil2d-0.7.0-camera.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## Step by Step {#steps}

Shortcuts are given for Windows and Linux. On macOS, use <kbd>Cmd</kbd> instead of <kbd>Ctrl</kbd>
and <kbd>Option</kbd> instead of <kbd>Alt</kbd>. All frame numbers assume **12 fps**.

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the
> frame you want. The playhead shows the number of the frame it is on. A single click on a cell in a
> layer's track selects that keyframe; it does not move the playhead.

**Part A: Camera size (5 minutes)**

1. Start a new project (**File → New**) and save it as `camera-yourname.pclx`.
2. In the timeline, find **Camera Layer** at the bottom of the layer list. Double-click its name.
   The **Camera Properties** dialog opens.
3. Set **Camera size:** to **1280** and **720** and click **OK**. The camera frame on the canvas gets
   wider. Pencil2D remembers the size you enter here and uses it for new camera layers on that
   computer. On a fresh installation the camera is 800 × 600.

**Part B: A scene bigger than the screen (20–25 minutes)**

{: start="4"}
4. Rename the drawing layer to **Background** (double-click its name). Add a layer for the character
   with **Layer → New Bitmap Layer** and call it **Character**. **Camera Layer** always stays at the bottom
   of the list.
5. Zoom the view out with the mouse wheel or <kbd>Ctrl</kbd>+<kbd>Down</kbd> until the camera frame
   is small on screen. To slide the view, hold <kbd>Space</kbd> and drag.
6. On the **Background** layer, frame 1: draw a landscape that starts a little to the left of the camera
   frame and continues to the right for about **three camera-widths**. Make it taller than the frame
   too. Add landmarks (a tree, a house, a sign) so the audience can feel the camera travel. Fill
   with the **Bucket**.
7. On the **Character** layer, frame 1: draw a character standing near the right end of the
   background. Draw the face big and clear, since you'll end on it.

<!-- SCREENSHOT: Zoomed-out canvas showing a landscape three camera-widths wide, the 1280x720 camera frame at the left end, gray shading outside the frame, and a character at the right end -->

**Part C: Camera keyframes (20 minutes)**

The shot is 72 frames (6 seconds) long:

| Frame | Camera | Shot |
|---|---|---|
| 1 | Left end of the scene, zoomed out a little | Establishing shot, holding |
| 12 | Same as frame 1 | The pan starts |
| 48 | At the character, same size | The pan ends |
| 54 | Same as frame 48 | A short hold |
| 66 | Zoomed in on the face | Close-up |
| 72 | Same as frame 66 | Hold, and the end of the shot |

{: start="8"}
8. Click **Camera Layer** in the timeline and choose the **Move** tool (<kbd>M</kbd>). On the camera
   layer, the Move tool moves the camera. Handles appear on the camera frame, and the status bar says
   *"Click and drag to move the camera."*
9. The camera layer already has a keyframe on frame 1. Drag inside the frame to put the camera at
   the left end of your scene. For a wider establishing shot, drag a corner handle outward a little.
10. Go to frame **12** and press <kbd>F7</kbd> (**Animation → Add Frame**). The new
    camera keyframe starts where the camera already is, so frames 1–12 are a hold.
11. Go to frame **48**, press <kbd>F7</kbd>, and drag the camera to the right until the character is in
    the frame.
12. To keep the pan perfectly level, right-click the keyframe on frame **12** in the camera track and
    choose **Transform → Align horizontally to frame 48**.
13. Go to frame **54** and press <kbd>F7</kbd> (a hold). Go to frame **66**, press <kbd>F7</kbd>, then drag a corner
    handle *inward* to zoom and drag inside the frame to center the face.
14. Go to frame **72** and press <kbd>F7</kbd>. This keyframe holds the close-up. It also marks the end of
    the shot: playback and export stop at the last keyframe.
15. Play (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). The moves work, but they start and stop abruptly.

<!-- SCREENSHOT: Camera layer selected with the Move tool: camera frame with four square corner handles, the round rotation handle above the top edge, and the thinner rectangle labeled 100% -->

**Part D: Easing and the camera path (15 minutes)**

{: start="16"}
16. Right-click the keyframe on frame **12** in the camera track. Choose
    **Easing: frame 12 to 48 → In-Out → Slow**. Play: the pan now eases in and out.
17. Right-click the keyframe on frame **54** and choose **Easing: frame 54 to 66 → Out → Moderate**.
    The zoom now slows down as it arrives on the face. (For a cartoon "boing", try
    **Out → Overshoot**.)
18. With the camera layer and the Move tool still selected, find **Camera path** in the **Options**
    panel. Tick **Show path** and pick a dot color that stands out against your background. Each dot
    is where the center of the camera is on one frame.
19. Optional: curve the path. Go to frame **30**, a frame *between* two keyframes.
    A square handle appears on the path; drag it to make the camera swoop up or down during the pan.
    **Reset path** straightens it again.
20. Optional: rotate. On frame 66, drag the round handle above the camera frame to rotate the close-up
    slightly. Hold <kbd>Shift</kbd> to snap to 15° steps. To undo the rotation, right-click the keyframe
    and choose **Transform → Reset rotation**.

<video src="{{ '/images/pencil2d-0.7.0-camera-path.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

**Part E: Export (5 minutes)**

{: start="21"}
21. Save. Choose **File → Export → Movie...**. In the **Export Movie** dialog, click **Browse...**,
    name the file `camera-yourname.mp4` and save it as MP4.
22. Check that **Camera** shows your camera layer, that **Width** and **Height** are 1280 and 720, and
    that the **Range** is **Start Frame** 1 to **End Frame** 72. Click **OK**.
23. When Pencil2D asks *"Finished. Open movie now?"*, click **Yes** and watch your shot.

More detail: [Camera layer]({{ '/doc/manual/camera.html#camera-layer' | relative_url }}),
[Camera size]({{ '/doc/manual/camera.html#camera-size' | relative_url }}), [Camera tool]({{ '/doc/manual/camera.html#camera-tool' | relative_url }}),
[Easing]({{ '/doc/manual/camera.html#easing' | relative_url }}), [Camera path]({{ '/doc/manual/camera.html#camera-path' | relative_url }}) and
[Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

## Practice Challenge {#challenge}

**Basic:** Finish the 6-second shot with an eased pan, a hold, and an eased zoom to a close-up, and
export it as MP4.

**Stretch:** Choose one:

- **Reveal:** start on a close-up and pull back to show something surprising that was off screen.
- **Whip pan:** a very fast pan between two places (about 3 frames long, eased with **In-Out →
  Fastest**), used as a cut between scenes.
- **Camera shake:** after something lands with a thump, add 4–6 camera keyframes on consecutive
  frames, each nudged a few pixels in a different direction, then return to the original position.
- **Combine lessons:** put your flour sack from Lesson 5 into the scene, and let the camera follow
  it.

## Wrap-up {#wrap-up}

Watch the exported movies together. Before each one, ask the class to call out the shot types as they
appear.

Discussion questions:

- What did the establishing shot tell you before any character appeared?
- Which moves felt natural, and which felt robotic? What was the difference?
- When would you *not* move the camera at all?
- How would the same shot feel if it ended with a tilted close-up?

## Assessment Checklist {#assessment}

| Look for | Evidence |
|---|---|
| Camera setup | Camera size set in **Camera Properties**; the scene extends beyond the frame |
| Keyframes | At least five camera keyframes with holds before and after moves |
| Easing | Pan and zoom start and stop smoothly, with no robotic stops |
| Staging | The shot begins wide and ends on a readable close-up; the edge of the drawing never shows |
| Film grammar | Student can name the shot types in their shot and say why they chose them |
| Export | An MP4 at the camera size that includes the final hold |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| No handles on the camera, or dragging does nothing | Not on the camera layer, or the playhead isn't on a camera keyframe (the handles look gray) | Click the camera layer and go to a camera keyframe, or press <kbd>F7</kbd> to make one |
| Dragging moved the drawing, not the camera | The Move tool was used on a drawing layer | Click **Camera Layer** first |
| The camera frame isn't visible while drawing | **Camera Layer** is hidden | Click the dot at the left of **Camera Layer** so it's filled in again |
| Zoomed in with the mouse wheel, but the movie didn't zoom | The mouse wheel only zooms *your view* | Zoom the camera with its corner handles on a camera keyframe |
| The frame outline is red | The camera is zoomed in past 100% | Zoom out a little, or draw the subject larger |
| The edge of the drawing shows during the pan | The background isn't wide or tall enough | Extend the background, or zoom the camera in slightly |
| No right-click menu, or **Easing** is grayed out | You didn't right-click directly on a camera keyframe, or it's the last keyframe | Right-click the *first* keyframe of the move |
| The pan drifts up or down | The two keyframes are at different heights | **Transform → Align horizontally to frame ...** |
| The final hold is missing from the movie | Export ends at the last keyframe | Add a camera keyframe at the last frame, or type the **End Frame** |
| MP4 export won't start, with a warning about odd width or height | MP4 needs even numbers | Use even numbers, such as 1280 × 720 |
| The movie shows the wrong view | There are two camera layers | Choose the right one under **Camera** in the export dialog, or delete the extra layer |

If movie export fails altogether, see the
[video export troubleshooting guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

## Going Further {#going-further}

- Read the whole [Camera]({{ '/doc/manual/camera.html' | relative_url }}) chapter, including camera onion skin and the full
  list of easing curves.
- Try the other easing groups: **Out-In** is fast at both ends and slow in the middle.
- Watch an animated film with the sound off and count how often the camera moves. Most shots don't
  move at all.
- Next: [Lesson 7: The Walk Cycle]({{ '/doc/course/lesson-07.html' | relative_url }}).

{% include series-nav.html series=site.data.course %}
