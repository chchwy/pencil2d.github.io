---
layout: page
title: Glossary
tagline: Animation and Pencil2D terms in plain words
comments: false
---

Short definitions of the animation terms and Pencil2D-specific words used in this manual. Where Pencil2D has a matching feature, the definition links to the chapter that explains it.

Jump to: [A](#letter-a) · [B](#letter-b) · [C](#letter-c) · [E](#letter-e) · [F](#letter-f) · [H](#letter-h) · [I](#letter-i) · [K](#letter-k) · [L](#letter-l) · [M](#letter-m) · [O](#letter-o) · [P](#letter-p) · [Q](#letter-q) · [S](#letter-s) · [T](#letter-t) · [V](#letter-v)

## A {#letter-a}

### Action safe area {#action-safe}

A frame drawn inside the camera field. Keep important action inside it so it isn't cut off on screens that crop the picture edges. Pencil2D shows it with the **Safe Areas** overlay. It is set to 5% by default, which leaves a 2.5% margin on each side. See [Overlays]({{ '/doc/manual/canvas.html#overlays' | relative_url }}). Compare [title safe area](#title-safe).

### Animatic {#animatic}

A rough version of a film made from storyboard drawings timed to the soundtrack. It is used to check pacing before full animation starts. In Pencil2D, you can make one with one keyframe per storyboard panel, held for as long as the shot lasts, plus a [sound layer](#sound-layer).

### Anti-aliasing {#anti-aliasing}

Smoothing the jagged, stair-stepped edges of lines by blending edge pixels with the background. In Pencil2D, some tools have an **Anti-Aliasing** option, and **Preferences** has a separate **Antialiasing** setting for how the canvas is displayed. Turn it off on a tool when you need hard-edged pixels, for example for clean bucket fills or pixel art. See [Tools]({{ '/doc/manual/tools.html#common-options' | relative_url }}).

### Anticipation {#anticipation}

A small movement in the opposite direction before a main action, such as crouching before a jump or pulling back an arm before a throw. It prepares the viewer for the action and makes the motion read clearly.

### Autosave {#autosave}

A Pencil2D option that saves your project automatically after a set number of changes. It is off by default. See [Autosave]({{ '/doc/manual/projects.html#autosave' | relative_url }}).

## B {#letter-b}

### Bitmap layer {#bitmap-layer}

A Pencil2D layer that stores each drawing as pixels, like a painting program. It supports every drawing tool and is the recommended layer type for most work. See [Bitmap or vector?]({{ '/doc/manual/getting-started.html#bitmap-vs-vector' | relative_url }}) and [Layers]({{ '/doc/manual/layers.html#layer-types' | relative_url }}).

### Breakdown {#breakdown}

The drawing between two key drawings that shows *how* the movement gets from one to the other, for example the path of an arc or which part leads. It is drawn before the remaining [in-betweens](#in-between).

## C {#letter-c}

### Camera field {#camera-field}

The rectangle on the canvas that represents what the camera sees and what gets exported. It is 800 × 600 pixels by default, and the canvas outside it is shaded. See [Camera size]({{ '/doc/manual/camera.html#camera-size' | relative_url }}) and [Key concepts]({{ '/doc/manual/getting-started.html#canvas-and-camera' | relative_url }}).

### Camera layer {#camera-layer}

A Pencil2D layer whose keyframes store the camera's position, rotation and zoom. Pencil2D moves the camera smoothly between those keyframes. Every project has at least one. See [The camera layer]({{ '/doc/manual/camera.html#camera-layer' | relative_url }}).

### Canvas {#canvas}

The drawing area in the middle of the Pencil2D window. It has no edges, so you can draw beyond the [camera field](#camera-field). See [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}).

### Cleanup {#cleanup}

Redrawing rough animation with final, clean lines, usually on a new layer above the rough drawings, which are then hidden or deleted.

### Crash recovery {#crash-recovery}

The Pencil2D feature that offers to restore a project when the program didn't close correctly. See [Crash recovery]({{ '/doc/manual/projects.html#recovery' | relative_url }}).

### Cycle {#cycle}

A sequence of drawings whose last drawing leads back into the first, so it can repeat without a visible jump. Walks, runs, flags waving and idle breathing are common cycles. Turn on **Loop** during playback to check a cycle. See [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }}).

## E {#letter-e}

### Easing {#easing}

Gradual acceleration and deceleration. "Ease in" or "slow in" means slowing down into a pose, and "ease out" or "slow out" means speeding up out of one. In hand-drawn animation you ease by placing drawings closer together near the key poses. For camera moves, Pencil2D can apply easing automatically between camera keyframes. See [Camera easing]({{ '/doc/manual/camera.html#easing' | relative_url }}).

### Exposure {#exposure}

How many frames a drawing stays on screen. In Pencil2D, a keyframe is exposed until the next keyframe on its layer. **Add Exposure** and **Subtract Exposure** lengthen or shorten it. See [Exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}). Related: [hold](#hold), [on ones, twos and threes](#on-twos).

## F {#letter-f}

### Feather {#feather}

A soft, gradually fading edge on a brush stroke. In Pencil2D, the **Brush**, **Eraser** and **Smudge** tools have a **Feather** option, and the Eraser also has a **Use Feather** check box. See [Tools]({{ '/doc/manual/tools.html#common-options' | relative_url }}).

### Flipping {#flipping}

Quickly switching between drawings to check motion, the digital version of flipping paper sheets. Pencil2D has **Flip In-Between** and **Flip Rolling** in the **Animation** menu. See [Timeline and Animation]({{ '/doc/manual/timeline.html#playback' | relative_url }}).

### Frame {#frame}

One still image in the sequence, and one numbered cell in the Timeline. The [frame rate](#frame-rate) sets how many frames make up one second. A frame doesn't need its own drawing, because it shows the last [keyframe](#keyframe) before it.

### Frame rate {#frame-rate}

How many frames are shown per second (fps). Pencil2D projects default to 12 fps. Film is traditionally 24 fps, and video is often 25 or 30 fps. Set it with the **fps** box in the Timeline. See [Frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}).

## H {#letter-h}

### Hold {#hold}

Keeping one drawing on screen for several frames. A short hold makes a pose read. A long hold with no motion at all can look dead, so animators often add a subtle "moving hold". In Pencil2D, a keyframe is held automatically until the next keyframe. See [Frames and keyframes]({{ '/doc/manual/getting-started.html#frames-and-keyframes' | relative_url }}).

## I {#letter-i}

### In-between {#in-between}

A drawing that fills the gap between two key drawings or breakdowns, completing the motion. Also called an "inbetween" or "tween". Pencil2D doesn't generate in-betweens for drawings; you draw them, usually with [onion skin](#onion-skin) turned on. The camera is the exception: camera moves are interpolated automatically.

### Invisible lines {#invisible-lines}

On vector layers, strokes drawn with the **Invisible** option. They don't appear in the final image but still act as boundaries for bucket fills, for example to close a color area without an outline. **View → Show Invisible Lines** shows them while you work. See [Tools]({{ '/doc/manual/tools.html#common-options' | relative_url }}) and [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}).

## K {#letter-k}

### Key drawing {#key-drawing}

A main drawing that defines an important pose or the extreme of a movement, for example the highest point of a jump. Animators usually draw keys first, then [breakdowns](#breakdown), then [in-betweens](#in-between). Also called a "key pose" or an "extreme". Don't confuse it with a Pencil2D [keyframe](#keyframe), which can hold any drawing.

### Keyframe {#keyframe}

In Pencil2D, a frame on a layer that holds content: a drawing on a bitmap or vector layer, a camera position on a camera layer, or the start of a clip on a sound layer. Keyframes appear as filled cells in the Timeline. See [Frames and keyframes]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}).

## L {#letter-l}

### Layer {#layer}

One level in the stack of content that makes up a scene, like a sheet of transparent paper. Each layer has its own row of keyframes in the Timeline, and higher layers appear in front of lower ones. Pencil2D has bitmap, vector, camera and sound layers. See [Layers]({{ '/doc/manual/layers.html' | relative_url }}).

### Layer visibility {#layer-visibility}

The Pencil2D setting that controls how layers other than the current one are shown while you draw: **Current layer only**, **Relative** (other layers faded) or **All layers**. See [Layer visibility]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}).

### Lip sync {#lip-sync}

Animating a character's mouth to match recorded dialogue. You import the dialogue on a [sound layer](#sound-layer), find where each sound starts by scrubbing, and draw the matching mouth shapes on those frames. See [Sound]({{ '/doc/manual/sound.html' | relative_url }}).

### Loop {#loop}

Playback that starts again from the beginning when it reaches the end. Use it to judge timing and to check [cycles](#cycle). In Pencil2D, toggle it with **Loop** in the Timeline or **Animation → Loop**. See [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }}).

## M {#letter-m}

### Memory Cache Budget {#memory-cache-budget}

A Pencil2D preference that limits how much memory is used to keep keyframe images loaded. See [File size, length and memory]({{ '/doc/manual/projects.html#performance' | relative_url }}).

## O {#letter-o}

### On ones, twos and threes {#on-twos}

How many frames each drawing is held for. "On ones" means a new drawing every frame, "on twos" a new drawing every second frame, and so on. Most hand-drawn animation at 24 fps is on twos. Pencil2D's default of 12 fps with one keyframe per frame gives the same rate of drawings per second as twos at 24 fps.

### Onion skin {#onion-skin}

Faded copies of neighboring drawings shown behind the current drawing, named after the thin onion-skin paper animators drew on over a light table. Onion skin helps you draw [in-betweens](#in-between) and keep movement consistent. See [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).

## P {#letter-p}

### .pcl {#pcl}

The legacy Pencil2D project format: an XML file plus a separate `.data` folder that holds the drawings. See [The legacy .pcl format]({{ '/doc/manual/projects.html#pcl' | relative_url }}).

### .pclx {#pclx}

The standard Pencil2D project format: a single ZIP-based file containing the whole project. See [File formats]({{ '/doc/manual/projects.html#file-formats' | relative_url }}).

### Peg bar {#peg-bar}

In traditional animation, a strip with pegs that holds punched paper in exactly the same position, so drawings line up. Pencil2D's **Peg bar Alignment** (in the **Edit** menu) lines up drawings on several layers using a registration mark. See [Peg bar alignment]({{ '/doc/manual/selection.html#peg-bar-alignment' | relative_url }}).

### Perspective grid {#perspective-grid}

Guide lines that converge on one, two or three vanishing points, used to draw backgrounds and objects in correct perspective. Pencil2D shows them as overlays. See [Perspective overlays]({{ '/doc/manual/canvas.html#perspective' | relative_url }}).

### Playback range {#playback-range}

A limited stretch of frames that playback is restricted to, so you can study one part of a long animation. In Pencil2D, turn on **Range** in the Timeline and set its start and end frames. Turn on [loop](#loop) as well to repeat it. See [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }}).

### Pose to pose {#pose-to-pose}

A way of working in which you draw the key poses first, then fill in between them. It gives good control of timing and staging. Compare [straight ahead](#straight-ahead).

### Preset {#preset}

In Pencil2D, a saved project that new projects start from, with your own layers, camera size, frame rate or palette. See [Presets]({{ '/doc/manual/projects.html#presets' | relative_url }}).

### Pressure {#pressure}

On a graphics tablet, how hard the pen presses. With the **Pressure** option on, Pencil2D varies the stroke with pen pressure. See [Tools]({{ '/doc/manual/tools.html#common-options' | relative_url }}).

## Q {#letter-q}

### Quick sizing {#quick-sizing}

Changing a tool's width or feather by dragging on the canvas while holding a modifier key, instead of using the **Options** panel. See [Quick sizing]({{ '/doc/manual/tools.html#quick-sizing' | relative_url }}).

## S {#letter-s}

### Scrubbing {#scrubbing}

Dragging the current-frame position back and forth along the Timeline to view the animation at your own speed. With sound scrub turned on, Pencil2D also plays a short snippet of audio at each frame, which helps with [lip sync](#lip-sync). See [Timeline and Animation]({{ '/doc/manual/timeline.html#anatomy' | relative_url }}) and [Sound]({{ '/doc/manual/sound.html' | relative_url }}).

### Sound layer {#sound-layer}

A Pencil2D layer that holds audio clips, placed at the frames where they start. See [Adding sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}).

### Spacing {#spacing}

How far an object moves from one drawing to the next. Wide spacing reads as fast, close spacing as slow, and changing spacing reads as acceleration or [easing](#easing). Spacing and [timing](#timing) work together.

### Squash and stretch {#squash-and-stretch}

Deforming a shape to show weight and flexibility: flattening it on impact (squash) and lengthening it during fast motion (stretch), while keeping its volume roughly the same. The bouncing ball is the classic exercise.

### Stabilizer {#stabilizer}

A Pencil2D tool option that smooths your strokes as you draw, reducing hand wobble. It has the levels **None**, **Simple** and **Strong**. See [Stabilizer]({{ '/doc/manual/tools.html#stabilizer' | relative_url }}).

### Straight ahead {#straight-ahead}

A way of working in which you draw each frame in order from the first to the last. It suits fluid, unpredictable motion such as fire, water or smoke. Compare [pose to pose](#pose-to-pose).

## T {#letter-t}

### Timecode {#timecode}

A way of labeling a position in time. Pencil2D's Timeline can show the current position as a plain frame number, SMPTE timecode (minutes, seconds, frames), or seconds and frames. See [Timeline and Animation]({{ '/doc/manual/timeline.html#anatomy' | relative_url }}).

### Timeline {#timeline}

The Pencil2D panel that shows layers as rows and frames as columns, and holds the playback controls. See [Timeline and Animation]({{ '/doc/manual/timeline.html' | relative_url }}) and [The Interface]({{ '/doc/manual/interface.html#timeline-panel' | relative_url }}).

### Timing {#timing}

How many frames an action takes, and therefore how fast it feels. Timing is set by the number of drawings and how long each is held ([exposure](#exposure)). It also depends on the [frame rate](#frame-rate).

### Title safe area {#title-safe}

A frame inside the [action safe area](#action-safe), further from the edges. Keep text and titles inside it so they stay readable on every screen. Pencil2D shows it with the **Safe Areas** overlay. It is set to 10% by default, which leaves a 5% margin on each side. See [Overlays]({{ '/doc/manual/canvas.html#overlays' | relative_url }}).

## V {#letter-v}

### Vector layer {#vector-layer}

A Pencil2D layer that stores strokes as editable curves instead of pixels. Strokes stay sharp at any zoom, and their colors are linked to the palette. The vector engine is still a work in progress, so bitmap layers are recommended for serious projects. See [Bitmap or vector?]({{ '/doc/manual/getting-started.html#bitmap-vs-vector' | relative_url }}) and [Colors on vector layers]({{ '/doc/manual/color.html#vector-colors' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
