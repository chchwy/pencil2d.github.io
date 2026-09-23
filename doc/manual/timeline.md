---
layout: page
title: Timeline and Animation
tagline: Keyframes, exposure, playback, frame rate, and editing frames on the timeline
comments: false
---

The Timeline panel is where drawings become animation. This chapter covers every part of the panel, how keyframes work, how to select, move, copy and re-time them, how to play your animation back, and every item in the **Animation** menu. Read it once from top to bottom when you start animating, then come back to it as a reference.

Shortcuts are written in Windows/Linux form. On macOS, use <kbd>Cmd</kbd> where this page says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> where it says <kbd>Alt</kbd>. You can change any shortcut in **Edit → Preferences → Shortcuts** (see [Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }})).

{% include toc.html %}

## Anatomy of the timeline {#anatomy}

The Timeline panel is docked along the bottom of the main window. To show or hide it, use **Windows → Timeline** (<kbd>Ctrl</kbd>+<kbd>6</kbd>). Like the other panels it can be moved, floated or docked elsewhere; see [The Interface]({{ '/doc/manual/interface.html#arranging-windows' | relative_url }}).

![The Timeline panel with three layers]({{ "/images/manual/timeline.png" | relative_url }})

The panel has two halves, separated by a splitter you can drag:

- **Left: the layer list.** One row per layer, each showing a visibility dot, an icon for the layer type, and the layer name. Above it, the **Layers:** buttons: **Add Layer** (opens a menu with **New Bitmap Layer**, **New Vector Layer**, **New Sound Layer** and **New Camera Layer**), **Delete Layer** and **Duplicate Layer**. Everything about layers is covered in [Layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}).
- **Right: the tracks.** One row per layer, divided into frame cells, with the frame-number row across the top. Above it are the key buttons, the zoom slider, and the playback controls.

### Tracks and frame cells {#tracks}

Each track is tinted by layer type: blue for bitmap, green for vector, orange for sound and yellow for camera. The row of the current layer is highlighted, and hidden layers are drawn faded, with their keyframes hidden. A keyframe is drawn as a small box inside its cell; cells without a box are empty or hold the previous drawing (see [Frames and keyframes](#keyframes)). Sound clips are drawn as one long box that spans the length of the clip.

Other marks you will see on the tracks:

- **Selected keyframes** are drawn in dark gray.
- **The keyframe under the playhead** gets a white outline when the playhead is exactly on it.
- **The cell under the mouse pointer** on the current layer gets a faint outline, so you can see which frame you are about to click.
- **Onion skin markers:** gray blocks in the frame-number row show which frames the [onion skin]({{ '/doc/manual/onion-skin.html' | relative_url }}) is currently displaying. They are hidden during playback.
- **The playback range**, when **Range** is on, is shown as a colored strip along the top edge of the frame-number row.

### The frame-number row {#frame-numbers}

The strip along the top of the tracks counts frames. Frame 1 and every multiple of the frame rate are numbered (at 12 fps: 1, 12, 24, 36, …), with a large tick at each second and half-second and a small tick at every other frame. This row is also where you scrub: see [The playhead](#playhead).

### The playhead {#playhead}

The playhead (also called the scrubber) is the highlighted column that marks the current frame; its frame number is printed on it at the top. Whatever frame the playhead is on is the frame you see and draw on in the canvas.

To move the playhead:

- **Click or drag in the frame-number row.** Dragging there scrubs through the animation.
- **Drag the top of the playhead itself.**
- **Double-click a frame cell** in any track. The playhead jumps to that frame.
- Use the keyboard: <kbd>.</kbd> and <kbd>,</kbd> step one frame forward or back, and <kbd>Alt</kbd>+<kbd>.</kbd> and <kbd>Alt</kbd>+<kbd>,</kbd> jump to the next or previous keyframe (see [Navigating frames](#navigating)).

> **Note:** A single click on a frame cell *selects* that frame; it does not move the playhead. To go to a frame, click its number in the frame-number row, or double-click the cell.

**Hollow scrubber.** By default the playhead runs down through every track. When you hover the mouse over the playhead's column, it turns into an outline, so you can see and click the keyframe underneath it.

<video src="{{ '/images/pencil2d-0.7.0-timeline-hollow-scrubber-showcase.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

**Short scrub.** If you prefer, the playhead can cover only the frame-number row instead of the full height of the tracks. Turn this on with **Short scrub** in **Edit → Preferences → Timeline**, or toggle it by double-clicking the frame-number row.

### Buttons above the tracks {#timeline-buttons}

From left to right:

| Control | What it does |
|---|---|
| **Add Frame** | Adds a new blank keyframe at the playhead. See [Adding keyframes](#adding-keyframes). |
| **Remove Frame** | Removes the keyframe at the playhead. |
| **Duplicate Frame** | Copies the keyframe at the playhead to the next free frame. |
| **Zoom** slider | Sets the width of each frame cell ("Adjust frame width"). See [Timeline zoom and length](#zoom-and-length). |
| **Jump to the Start** | Moves the playhead to the first keyframe in the project, or to the start of the playback range when **Range** is on. |
| **Play** / **Stop** | Starts or stops playback. |
| **Jump to the End** | Moves the playhead to the last keyframe in the project, or to the end of the playback range when **Range** is on. |
| **Loop** | When on, playback starts again from the beginning after it reaches the end. |
| **fps** box | The frame rate of the project, in frames per second. See [Frame rate](#frame-rate). |
| **Range** checkbox | Limits playback to the frames set in the two boxes after it. |
| Range start / end boxes | The first ("Start of playback loop") and last ("End of playback loop") frame of the playback range. Only editable while **Range** is checked. |
| **Sound on/off** | Mutes or unmutes sound layers during playback. On by default. |
| **Sound scrub on/off** | When on, you hear a short snippet of sound as you scrub or step through frames. |
| **…** (more options) | Chooses what the frame counter next to it displays; see below. |

The frame counter at the far right shows where the playhead is. Choose its format from the **…** button's **Display timecode** menu:

| Option | Shows |
|---|---|
| **No text** | Nothing; the counter is hidden. |
| **Frames** | The current frame number, e.g. `0027`. This is the default. |
| **SMPTE Timecode** | Minutes, seconds and frames, `MM:SS:FF`. |
| **SFF Timecode** | Seconds and frames, `S:FF`. |

### Mouse and scroll wheel {#mouse}

- **Scroll wheel** over the timeline scrolls the layers up and down.
- <kbd>Shift</kbd>+**scroll wheel** scrolls the frames left and right.
- **Middle-button drag** on the tracks pans the timeline left and right.
- **Right-click a camera keyframe** to open the camera menu for easing and resetting the camera; see [Camera]({{ '/doc/manual/camera.html#easing' | relative_url }}). Other layer types have no right-click menu on the timeline in 0.7.2.
- **Double-click a layer name** to rename it (or, for a camera layer, to open its properties). See [Layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}).
- Clicking the dot at the top of the layer list changes the canvas layer visibility mode; see [Canvas and View]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}).

## Frames and keyframes {#keyframes}

A **frame** is one step of time on the timeline, one cell in a track. A **keyframe** is a frame that holds a drawing (or, on a camera layer, a camera position; on a sound layer, the start of a sound clip).

A keyframe **holds until the next keyframe**. If a layer has keyframes on frames 1 and 5, the drawing from frame 1 is shown on frames 1, 2, 3 and 4, and the drawing from frame 5 takes over on frame 5. The number of frames a drawing stays on screen is called its **exposure**. Holding a drawing for two frames is called animating "on twos", a common way to save drawing effort.

The drawing on a layer's last keyframe stays on screen for every frame after it, but playback stops at the last keyframe in the project, so the final drawing only flashes by for one frame. To hold the final pose, put another keyframe at the frame where the animation should end (for example with **Duplicate Frame**).

Each layer has its own keyframes, so a character's body and a background can be timed independently.

### Adding keyframes {#adding-keyframes}

To add a blank keyframe, move the playhead to a frame and click **Add Frame** in the timeline, choose **Animation → Add Frame**, or press <kbd>F7</kbd>. The playhead moves to the new keyframe.

- On an empty or held frame, the new keyframe is created right there.
- On a frame that already has a keyframe, the new keyframe is inserted on the next frame. If there are keyframes directly after it, that run of keyframes is pushed one frame to the right to make room; nothing is overwritten.
- On a sound layer, **Add Frame** opens a file dialog so you can import a sound clip; see [Sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}).
- You cannot add a keyframe to a hidden layer; Pencil2D shows a warning instead.

> **Note:** Pencil2D 0.7.0 also created a keyframe when you double-clicked an empty cell. Because this often created keyframes by accident, it was removed after 0.7.0. In 0.7.2, double-clicking a cell only moves the playhead.

### Drawing on an empty frame {#drawing-on-empty-frames}

You don't have to add a keyframe before you draw. When you start drawing on a frame that has no keyframe of its own, Pencil2D does one of three things, chosen under **Edit → Preferences → Timeline**, in **When drawing on an empty frame:**

| Option | What happens |
|---|---|
| **Create a new (blank) key-frame** | A blank keyframe is created at the playhead and your stroke goes on it. |
| **Duplicate the previous key-frame** | The drawing being held is copied into a new keyframe at the playhead, and your stroke goes on the copy. |
| **Keep drawing on the previous key-frame** | No keyframe is created; your stroke is added to the keyframe being held. This is the default. |

This applies to the drawing tools on bitmap and vector layers. The Eraser always works on the drawing you see and never creates a keyframe. See [Preferences]({{ '/doc/manual/preferences.html#timeline' | relative_url }}) for the rest of the Timeline preferences.

> **Tip:** With the default setting, drawing on frame 3 of a drawing held from frame 1 changes frame 1 too, because they are the same drawing. If you want every new frame to start fresh, switch to **Create a new (blank) key-frame**, or press <kbd>F7</kbd> before you draw.

### Duplicating keyframes {#duplicating-keyframes}

To copy the keyframe at the playhead, click **Duplicate Frame**, choose **Animation → Duplicate Frame**, or press <kbd>F6</kbd>. The copy goes on the first frame after the playhead that doesn't already have a keyframe, and the playhead moves to it. The playhead must be exactly on a keyframe. Any timeline selection is cleared.

Duplicating is the quickest way to make a small change from one drawing to the next: duplicate, then adjust the copy.

### Removing keyframes {#removing-keyframes}

To remove the keyframe at the playhead, click **Remove Frame**, choose **Animation → Remove Frame**, or press <kbd>Shift</kbd>+<kbd>F5</kbd>. The frames after it do not move; the previous drawing now holds over the gap. You can undo this with **Edit → Undo**.

- If the playhead is not on a keyframe, **Remove Frame** just steps the playhead back one frame.
- A bitmap, vector or camera layer always keeps at least one keyframe, so the last remaining keyframe cannot be removed.

To remove several keyframes at once, see [Remove Frames](#remove-frames).

## Selecting keyframes {#selecting-frames}

Most timeline editing works on a selection of keyframes. Selected keyframes are drawn in dark gray. You can only select keyframes on one layer at a time: selecting on another layer clears the previous selection.

| To… | Do this |
|---|---|
| Select one keyframe | Click it. Any other selection is cleared. |
| Add or remove a keyframe from the selection | <kbd>Ctrl</kbd>+click it. |
| Select a range | Click the first keyframe, then <kbd>Shift</kbd>+click the last. Every keyframe in between is selected. |
| Select a range by dragging | Press on an unselected cell and drag left or right along the track. |
| Select a keyframe and everything after it | <kbd>Alt</kbd>+click it. All keyframes from there to the end of the layer are selected. |
| Deselect | Click an empty cell, click a selected keyframe again, or use **Edit → Deselect All** (<kbd>Ctrl</kbd>+<kbd>D</kbd>). |

Clicking selects without moving the playhead. See [The playhead](#playhead).

## Moving keyframes {#moving-keyframes}

To move keyframes in time, select them, then drag any selected keyframe left or right. While you drag, the selection is lifted slightly above the track and does not disturb other keyframes; it is placed when you release the mouse.

<video src="{{ '/images/pencil2d-0.7.0-timeline-dragging-keyframes-showcase.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

- Keyframes stay on their own layer; you cannot drag them to another layer.
- Existing keyframes are never overwritten. If the drop position would land on keyframes that aren't part of the selection, Pencil2D moves the selection to the nearest position where it fits: further right when you drag right, or closer to where it started when you drag left. If there is no room at all, nothing moves.
- Keyframes can't be moved before frame 1.

> **Tip:** To make room in the middle of an animation, <kbd>Alt</kbd>+click the first keyframe that needs to move, which selects it and everything after it, then drag them all to the right.

### Move Frame Forward and Backward {#move-frame}

**Animation → Move Frame Forward** (<kbd>Ctrl</kbd>+<kbd>.</kbd>) and **Move Frame Backward** (<kbd>Ctrl</kbd>+<kbd>,</kbd>) move the keyframe at the playhead one frame later or earlier, and the playhead follows it. If the neighboring frame has a keyframe, the two swap places. The playhead must be exactly on a keyframe.

## Changing exposure {#exposure}

Exposure is how long a drawing stays on screen. Instead of dragging keyframes around one at a time, you can lengthen or shorten keyframes directly; the keyframes after them move to make room or close the gap.

- **Add Exposure** (<kbd>Ctrl</kbd>+<kbd>+</kbd>) makes each selected keyframe last one frame longer.
- **Subtract Exposure** (<kbd>Ctrl</kbd>+<kbd>-</kbd>) makes each selected keyframe last one frame shorter. A keyframe can't be shortened below one frame.

Both are in **Animation → Timeline Selection**. If nothing is selected, they change the keyframe currently shown at the playhead, even if the playhead is on one of its held frames. With several keyframes selected, each of them gains or loses one frame, and everything after moves to fit.


<video src="{{ '/images/pencil2d-0.7.0-timeline-keyframe-exposure-showcase.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

> **Tip:** Exposure is the fastest way to fix timing. Play the animation, find a pose that goes by too fast, put the playhead on it and press <kbd>Ctrl</kbd>+<kbd>+</kbd> until it feels right.

<!-- VERIFY: whether Ctrl++ can be typed as Ctrl+= on keyboards where + needs Shift, or only with the numeric keypad + key. -->

## Reversing, removing and repositioning selected frames {#timeline-selection}

The rest of the **Animation → Timeline Selection** submenu works on the selected keyframes of the current layer.

### Reverse Frames Order {#reverse}

**Reverse Frames Order** flips the order of the selected keyframes: the first selected drawing swaps with the last, the second with the second-to-last, and so on. The frame positions stay the same; only the drawings change places. It has no default shortcut.

> **Tip:** To make an action go there and back (a swing, a blink), [copy the keyframes](#copy-paste), paste them after the originals, then choose **Reverse Frames Order** while the pasted copies are still selected.

### Remove Frames {#remove-frames}

**Remove Frames** deletes all selected keyframes. Pencil2D asks you to confirm first.

> **Warning:** Remove Frames cannot be undone in 0.7.2. Save your project before using it.

### Reposition Selected Frames {#reposition}

**Animation → Reposition Selected Frames** moves the *content* of several keyframes by the same amount, for example to shift a character across the frame in every drawing at once. It works on bitmap layers.

![The Reposition Frames dialog next to the canvas]({{ "/images/pencil2d-0.7.0-reposition-selected-frames-interface.png" | relative_url }})

1. On a bitmap layer, select at least two keyframes. (With fewer, Pencil2D asks you to select at least 2 frames.)
2. Choose **Animation → Reposition Selected Frames**. The **Reposition Frames** dialog opens, the Move tool becomes active, and the drawing on the current (or first selected) keyframe gets a selection around it.
3. Drag the selection on the canvas to the new position. The dialog shows how far you moved it as **Repositioned: ( x, y )**.
4. To move the same amount on other layers too, check **Reposition on other layers?**, choose **Same keyframes as selected** (only keyframes at the same frame numbers) or **All keyframes on layer** (the default), and pick one or more bitmap layers in the list.
5. Click **Reposition**, or **Cancel** to close without changes.

The top of the dialog lists the layer (**Selected on Layer:**) and the frame numbers that will be moved.

<video src="{{ '/images/pencil2d-0.7.0-reposition-selected-frames-showcase.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

> **Note:** Undo for repositioning is limited in 0.7.2 and may not restore every frame. Save before you use it.

## Copying and pasting keyframes {#copy-paste}

You can copy whole keyframes on the timeline and paste them somewhere else.

1. Select the keyframes you want to copy.
2. Choose **Edit → Copy** (<kbd>Ctrl</kbd>+<kbd>C</kbd>), or **Edit → Cut** (<kbd>Ctrl</kbd>+<kbd>X</kbd>) to remove them at the same time.
3. Move the playhead to where the copies should start, on the same layer or another layer of the same type.
4. Choose **Edit → Paste** (<kbd>Ctrl</kbd>+<kbd>V</kbd>).

The first copied keyframe lands on the playhead, and the others keep their spacing. Existing keyframes in the way are pushed to the right, not overwritten. The pasted keyframes are selected afterwards, so you can drag them straight away.

<video src="{{ '/images/pencil2d-0.7.0-timeline-copy-paste-frames.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

- Copy and Cut work on keyframes only when keyframes are selected on the timeline **and** nothing is selected on the canvas. If there is a canvas selection, they copy the selected drawing instead; see [Selecting and Transforming]({{ '/doc/manual/selection.html#clipboard' | relative_url }}).
- Frames can only be pasted onto a layer of the same type (bitmap onto bitmap, sound onto sound, and so on).
- Pasting keyframes cannot be undone in 0.7.2. <!-- VERIFY: whether Edit → Cut of timeline keyframes can be undone; Editor::copyAndCut removes them without its own undo step. -->

**Edit → Paste from Previous Keyframe** (<kbd>Ctrl</kbd>+<kbd>Left</kbd>) is related but different: it pastes the *drawing* of the previous keyframe onto the current keyframe. It is covered in [Selecting and Transforming]({{ '/doc/manual/selection.html#clipboard' | relative_url }}).

## Navigating frames {#navigating}

| Command | Shortcut | What it does |
|---|---|---|
| **Next Frame** | <kbd>.</kbd> | Moves the playhead one frame forward. |
| **Previous Frame** | <kbd>,</kbd> | Moves the playhead one frame back (not before frame 1). |
| **Next Keyframe** | <kbd>Alt</kbd>+<kbd>.</kbd> | Jumps to the next keyframe on the current layer. After the last keyframe, it steps one frame forward. |
| **Previous KeyFrame** | <kbd>Alt</kbd>+<kbd>,</kbd> | Jumps to the previous keyframe on the current layer. |

All four are in the **Animation** menu. **Jump to the Start** and **Jump to the End** are buttons on the timeline (see [Buttons above the tracks](#timeline-buttons)). With **Sound scrub** on, stepping with <kbd>.</kbd> and <kbd>,</kbd> plays a short snippet of sound at each frame.

## Playback {#playback}

To play your animation, click **Play** on the timeline, choose **Animation → Play**, or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd>. The button turns into **Stop**; click it or press the shortcut again to stop. Clicking in the frame-number row also stops playback.

- Playback starts from the playhead. If the playhead is at or after the end, it starts over from frame 1 (or from the start of the range).
- Playback ends at the last keyframe in the project, or at the end of the last sound clip if that is later.
- Onion skins are hidden during playback, unless you turn on **Show During Playback** in the [Onion Skin panel]({{ '/doc/manual/onion-skin.html#onion-skin-panel' | relative_url }}).

### Loop {#loop}

Turn on **Loop** (the timeline button, **Animation → Loop**, or <kbd>Ctrl</kbd>+<kbd>L</kbd>) to have playback jump back to the start and keep going until you stop it. Looping is the best way to judge a cycle such as a walk or a bouncing ball.

### Playback range {#range}

To play only part of the animation, check **Range** on the timeline (or **Animation → Range**) and set the start and end frames in the two boxes next to it. The range is marked by a colored strip above the frame numbers. **Play**, **Loop**, **Jump to the Start** and **Jump to the End** then all use the range instead of the whole animation. The end frame is always after the start frame.

The frame rate, loop and range settings are saved in your project file.

### Sound during playback {#playback-sound}

**Sound on/off** mutes and unmutes sound layers during playback. **Sound scrub on/off** plays a short snippet of sound as you scrub or step frame by frame, which helps with lip sync. The length of the snippet is set by **Sound scrub** in **Edit → Preferences → Timeline** (100 ms by default). See [Sound]({{ '/doc/manual/sound.html' | relative_url }}).

### Flip In-Between and Flip Rolling {#flipping}

These imitate how traditional animators flip paper drawings to check motion. Both are in the **Animation** menu.

- **Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>) is for checking an in-between drawing. Put the playhead on a frame *between* two keyframes, then run it: Pencil2D flips previous keyframe, current frame, next keyframe, current frame, then returns to where you were. It needs a keyframe before and after the current frame, so it does nothing on the first or last keyframe of the layer.
- **Flip Rolling** (<kbd>Alt</kbd>+<kbd>X</kbd>) flips through the last few keyframes before the playhead and ends on the current frame.

How many drawings Flip Rolling shows (default 5) and how long each drawing stays on screen (default 100 ms, set separately for the roll and the in-between flip) are set in **Edit → Preferences → Timeline**, under **Flip and Roll**.

## Frame rate {#frame-rate}

The frame rate, in frames per second (fps), sets how fast the animation plays. Change it in the **fps** box on the timeline; it accepts 1 to 90. New projects start at 12 fps.

| fps | Typical use |
|---|---|
| 12 | Simple hand-drawn animation; each drawing is on screen for 1/12 of a second. |
| 24 | Film. Often animated "on twos" (each drawing held for 2 frames), which looks like 12 drawings per second. |
| 25 | PAL video (Europe and elsewhere). |
| 30 | NTSC video and most web video. |

Changing the frame rate does not move any keyframes, so the whole animation simply plays faster or slower. Sound clips keep their real length, so their length in frames is recalculated. The frame rate is stored in the project and is also used when you export a movie; see [Importing and Exporting]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

> **Tip:** Decide on a frame rate before you start timing. If you change it later, the timing of every drawing changes with it.

## Timeline zoom and length {#zoom-and-length}

**Zoom** on the timeline sets the width of each frame cell, from very narrow (to see many frames at once) to wide (to click individual frames easily). Pencil2D remembers the setting.

The timeline shows 240 frames by default. When your animation gets close to the end of the visible length, the timeline extends itself automatically, up to 9999 frames. To set a different length, change **Timeline length:** in **Edit → Preferences → Timeline**.

## Timeline preferences {#timeline-preferences}

The Timeline page of the Preferences dialog (**Edit → Preferences → Timeline**; on macOS, **Pencil2D → Preferences**) holds the settings mentioned on this page: **Timeline length:**, **Short scrub**, the **When drawing on an empty frame:** choice, **Flip and Roll** timing, **Sound scrub** duration and the layer visibility options. Every option and its default is listed in [Preferences]({{ '/doc/manual/preferences.html#timeline' | relative_url }}).

## The Animation menu {#animation-menu}

| Item | Shortcut | Described in |
|---|---|---|
| **Play** / **Stop** | <kbd>Ctrl</kbd>+<kbd>Enter</kbd> | [Playback](#playback) |
| **Loop** | <kbd>Ctrl</kbd>+<kbd>L</kbd> | [Loop](#loop) |
| **Range** | — | [Playback range](#range) |
| **Next Frame** | <kbd>.</kbd> | [Navigating frames](#navigating) |
| **Previous Frame** | <kbd>,</kbd> | [Navigating frames](#navigating) |
| **Next Keyframe** | <kbd>Alt</kbd>+<kbd>.</kbd> | [Navigating frames](#navigating) |
| **Previous KeyFrame** | <kbd>Alt</kbd>+<kbd>,</kbd> | [Navigating frames](#navigating) |
| **Add Frame** | <kbd>F7</kbd> | [Adding keyframes](#adding-keyframes) |
| **Duplicate Frame** | <kbd>F6</kbd> | [Duplicating keyframes](#duplicating-keyframes) |
| **Remove Frame** | <kbd>Shift</kbd>+<kbd>F5</kbd> | [Removing keyframes](#removing-keyframes) |
| **Move Frame Forward** | <kbd>Ctrl</kbd>+<kbd>.</kbd> | [Move Frame Forward and Backward](#move-frame) |
| **Move Frame Backward** | <kbd>Ctrl</kbd>+<kbd>,</kbd> | [Move Frame Forward and Backward](#move-frame) |
| **Flip In-Between** | <kbd>Alt</kbd>+<kbd>Z</kbd> | [Flip In-Between and Flip Rolling](#flipping) |
| **Flip Rolling** | <kbd>Alt</kbd>+<kbd>X</kbd> | [Flip In-Between and Flip Rolling](#flipping) |
| **Reposition Selected Frames** | — | [Reposition Selected Frames](#reposition) |
| **Timeline Selection → Add Exposure** | <kbd>Ctrl</kbd>+<kbd>+</kbd> | [Changing exposure](#exposure) |
| **Timeline Selection → Subtract Exposure** | <kbd>Ctrl</kbd>+<kbd>-</kbd> | [Changing exposure](#exposure) |
| **Timeline Selection → Reverse Frames Order** | — | [Reverse Frames Order](#reverse) |
| **Timeline Selection → Remove Frames** | — | [Remove Frames](#remove-frames) |

The onion skin toggles live in the **View** menu and are covered in [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
