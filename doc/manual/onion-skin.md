---
layout: page
title: Onion Skin
tagline: Seeing previous and next drawings while you animate
comments: false
---

Onion skinning shows faded copies of the drawings before and after the current frame, so you can see where a movement is coming from and where it is going while you draw. This chapter explains every control in the Onion Skins panel, the two onion skin modes, and settings that work well when you are starting out, and ends with a short worked example.

Shortcuts are written in Windows/Linux form; on macOS, use <kbd>Option</kbd> where this page says <kbd>Alt</kbd>, and <kbd>Cmd</kbd> where it says <kbd>Ctrl</kbd>.

{% include toc.html %}

## What onion skinning is {#what-is-onion-skinning}

Traditional animators draw on thin paper over a light table, so they can see the previous drawing through the sheet they are working on. The name comes from the thin, see-through skin of an onion. In Pencil2D, onion skins are "ghosts" of the neighboring keyframes, drawn faintly behind the current frame.

Animators use onion skins to:

- keep shapes and proportions consistent from drawing to drawing;
- judge **spacing**: how far something moves between drawings, which decides whether it looks fast or slow;
- draw **in-betweens**: a drawing that sits halfway between two others, which you place by looking at both at once.

Onion skins only appear on the canvas while you work. They are never included when you export an image or a movie.

## Turning onion skin on and off {#toggling}

Previous and next onion skins are switched on separately. Both are off by default. You can toggle them in three places, which always stay in sync:

| Where | Previous | Next |
|---|---|---|
| **View → Onion Skin** menu | **Previous** (<kbd>O</kbd>) | **Next** (<kbd>Alt</kbd>+<kbd>O</kbd>) |
| Onion Skins panel | **Previous Frames** checkbox | **Next Frames** checkbox |
| Keyboard | <kbd>O</kbd> | <kbd>Alt</kbd>+<kbd>O</kbd> |

> **Tip:** Tap <kbd>O</kbd> to look at your drawing without ghosts, then tap it again to bring them back.

When onion skin is on, the timeline marks the frames being shown as ghosts with gray blocks in the frame-number row (see [Timeline and Animation]({{ '/doc/manual/timeline.html#anatomy' | relative_url }})).

## The Onion Skins panel {#onion-skin-panel}

To open the panel, choose **Windows → Onion Skins** (<kbd>Ctrl</kbd>+<kbd>8</kbd>). By default it is docked on the left side of the main window.

![The Onion Skins panel with Previous Frames and Next Frames on and colored onion skins]({{ "/images/manual/onion-skins-panel.png" | relative_url }})

*Previous Frames and Next Frames turned on, with the red and blue color buttons pressed.*

| Control | What it does | Default |
|---|---|---|
| **Previous Frames** (checkbox in the group title) | Shows drawings before the current frame. Same as **View → Onion Skin → Previous**. | Off |
| Previous number box | How many previous drawings to show, 1 to 60. | 5 |
| Red button ("Onion skin color: red") | Tints the previous drawings solid red. | Off |
| **Next Frames** (checkbox in the group title) | Shows drawings after the current frame. Same as **View → Onion Skin → Next**. | Off |
| Next number box | How many next drawings to show, 1 to 60. | 5 |
| Blue button ("Onion skin color: blue") | Tints the next drawings solid blue. | Off |
| **Distributed Opacity: Max** | Opacity of the ghost nearest to the current frame, 0 to 100 %. | 50 % |
| **Distributed Opacity: Min** | Opacity the ghosts fade towards as they get further away, 0 to 100 %. | 20 % |
| **Show Keyframes Only** | Counts keyframes instead of frames. See [Onion skin modes](#modes). | Off |
| **Show During Playback** | Keeps onion skins visible while the animation plays. When off, they are hidden during playback. | Off |

These settings belong to Pencil2D, not to a project: they stay the same when you open another file or restart the program.

### Distributed opacity {#opacity}

The ghost nearest to the current frame is drawn at the **Max** opacity. Each ghost further away is a little fainter, stepping evenly down towards **Min**, so the furthest drawing is the faintest. Previous and next ghosts fade the same way. If ghosts get in the way of your line work, lower **Max**; if distant ghosts are hard to see, raise **Min**.

A keyframe's own opacity (set with **Layer → Layer / Keyframe opacity**; see [Layers]({{ '/doc/manual/layers.html#opacity' | relative_url }})) also makes its ghost fainter.

### Red and blue color onion {#colors}

With the color buttons off, ghosts keep their original colors and are simply faded. With them on, every previous drawing is tinted solid red and every next drawing solid blue. This makes it easy to tell past from future at a glance, and to tell both apart from the drawing you're working on, especially when your drawings are colored.

![A bouncing ball with red and blue onion skins]({{ "/images/manual/onion-skin-example.png" | relative_url }})

## Onion skin modes {#modes}

The **Show Keyframes Only** checkbox decides what the number boxes count.

**Show Keyframes Only off (the default)** counts *frames*. With Previous set to 2, Pencil2D looks at the two frames just before the playhead and shows a ghost for each one that has a keyframe. Frames that only hold an earlier drawing show nothing. This mode shows timing honestly: a drawing that is held for a long time drops out of the ghosts.

**Show Keyframes Only on** counts *keyframes*. With Previous set to 2, you always see the two previous drawings on the layer, however far back they are. The drawing currently on screen is never repeated as a ghost.

For example, a layer animated on twos has keyframes on frames 1, 3 and 5. With the playhead on frame 5 and Previous set to 2:

| Mode | Frames checked | Ghosts shown |
|---|---|---|
| Show Keyframes Only off | 4 and 3 | Frame 3 only |
| Show Keyframes Only on | Previous 2 keyframes | Frames 3 and 1 |

> **Tip:** If you hold drawings for two frames or more, turn on **Show Keyframes Only**. Otherwise you may see fewer ghosts than you expect, or none at all.

## Which layers show onion skins {#layers}

Onion skins are drawn for the **current layer only**, and only for bitmap and vector layers. Click another layer in the timeline to see its ghosts instead. Hidden layers show no onion skin.

Camera layers use the same settings in a different way: the camera frame at previous and next frames is drawn as a dashed outline, red and blue if the color buttons are on. This lets you see the path of a camera move. See [Camera]({{ '/doc/manual/camera.html' | relative_url }}).

<video src="{{ '/images/pencil2d-0.7.0-camera-onion-skins.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## Recommended settings for beginners {#recommended-settings}

- **Previous Frames** on, set to **1** or **2**. More ghosts than that make the canvas hard to read.
- **Next Frames** off while you draw new poses; turn it on (set to **1**) when you draw an in-between and need to see the drawing on both sides.
- **Red** and **blue** color on.
- **Show Keyframes Only** on, so held drawings still show up as ghosts.
- Leave **Distributed Opacity** at 20 % to 50 %.
- **Show During Playback** off, so playback shows your animation as the viewer will see it.

## Worked example: a bouncing ball {#example}

This example uses onion skin to space the drawings of a ball dropping to the ground. It assumes you know how to draw with the [Pencil]({{ '/doc/manual/tools.html#pencil' | relative_url }}) and add keyframes (see [Timeline and Animation]({{ '/doc/manual/timeline.html#keyframes' | relative_url }})).

1. Create a new project and click the bitmap layer in the timeline.
2. Open the Onion Skins panel with <kbd>Ctrl</kbd>+<kbd>8</kbd>. Check **Previous Frames** and set it to **2**. Turn on the red button. Check **Show Keyframes Only**.
3. On frame 1, draw a ball near the top of the camera frame.
4. Press <kbd>F7</kbd> to add a keyframe on frame 2. The canvas is empty except for a red ghost of the first ball.
5. Draw the ball a little lower. Press <kbd>F7</kbd> again and draw it lower still, leaving a bigger gap each time: a falling ball speeds up, so the red ghosts should get further apart as it drops.
6. On the frame where the ball hits the ground, draw it squashed flat.
7. Now check an in-between. Move the playhead to one of the middle drawings, check **Next Frames**, set it to **1** and turn on the blue button. The nearest red ghost shows the drawing before and the blue ghost the drawing after; the current drawing should sit between them.
8. Press <kbd>O</kbd> and <kbd>Alt</kbd>+<kbd>O</kbd> to hide the ghosts, then press <kbd>Ctrl</kbd>+<kbd>L</kbd> and <kbd>Ctrl</kbd>+<kbd>Enter</kbd> to play the drop in a loop. If one drawing jumps, turn the ghosts back on, go to that frame and redraw it.

To make the ball bounce back up, select and copy the falling drawings, move the playhead to the frame after the squash, paste, and reverse the order of the pasted keyframes; see [Timeline and Animation]({{ '/doc/manual/timeline.html#reverse' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
