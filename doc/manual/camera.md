---
layout: page
title: Camera
tagline: Camera size, camera moves, easing and camera paths
comments: false
---

Pencil2D's canvas has no edges: you can draw as far in any direction as you like. The camera
decides which part of that canvas ends up in your exported images and videos, and at what size.
This chapter explains the camera layer, how to set the output resolution, and how to animate the
camera with pans, zooms, rotations, easing and curved paths.

> **Note:** On macOS, press <kbd>Cmd</kbd> wherever this page says <kbd>Ctrl</kbd>, and
> <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.

{% include toc.html %}

<video src="{{ '/images/pencil2d-0.7.0-camera.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## The camera layer {#camera-layer}

Every project has at least one camera layer, named **Camera Layer** by default. It holds no
drawings. Each keyframe on it stores where the camera is on the canvas, how large it is and how it is
rotated. Frames between two camera keyframes are calculated automatically, so the camera moves
smoothly from one keyframe to the next.

On the canvas, the camera field (the area that will be exported) is shown as a clear rectangle;
everything outside it is shaded. You can keep drawing in the shaded area, and it just won't appear
in the export unless the camera moves over it. Hiding the camera layer (its eye icon in the timeline)
removes the shading, but the camera still controls the export.

<!-- SCREENSHOT: Canvas with a drawing larger than the camera; the camera field clear, the area outside shaded, camera layer visible in the timeline -->

- **Adding a camera layer:** **Layer → New Camera Layer** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>C</kbd>),
  or the add-layer button in the timeline. You are asked for a name first. A new camera layer starts
  with one keyframe on frame 1.
- **Deleting:** you can delete camera layers as long as one remains. Trying to delete the last one
  shows "Please keep at least one camera layer in project".
- **At least one keyframe:** a camera layer always keeps at least one keyframe; **Remove Frame**
  does nothing on the only remaining camera keyframe.
- **Before the first and after the last keyframe**, the camera holds still at that keyframe's
  position.

See [Layers]({{ '/doc/manual/layers.html#layer-types' | relative_url }}) for how camera layers fit with the other layer
types.

### Multiple camera layers {#multiple-cameras}

You can have more than one camera layer, for example to export the same animation at two sizes or
with two different moves. Only one camera is used per export: the **Camera** list in the export
dialog picks it. That list starts on the camera layer you have selected; if you have a non-camera
layer selected, it starts on the lowest camera layer in the timeline. The export width and height
are filled in from the chosen camera's size. See
[Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

The canvas shading and the camera handles belong to the first camera layer found at or below the
selected layer in the timeline.

> **Tip:** Give each camera layer a different name. The export dialog lists cameras by name, so
> two cameras with the same name can't be told apart.

## Camera size and resolution {#camera-size}

The camera size is the resolution of your exported frames, in pixels. The default is 800 × 600.

To change it, double-click the camera layer's **name** in the timeline. The **Camera Properties**
dialog opens:

| Option | What it does | Default |
|---|---|---|
| **Camera name:** | Renames the camera layer | Camera Layer |
| **Camera size:** | Width and height of the camera field in pixels, 1 to 10000 each | 800 × 600 |

Click **OK** to apply. Keep these points in mind:

- The size belongs to **that camera layer only**. Each camera layer has its own size.
- Pencil2D also remembers the last size you entered and uses it for camera layers you create
  later, including the camera of new projects that use the built-in default setup. A project
  created from a custom [preset]({{ '/doc/manual/projects.html#presets' | relative_url }}) keeps the preset's camera size.
- Changing the size does not scale your drawings. The camera field grows or shrinks around its
  center, so you may need to reposition artwork or the camera afterwards.
- Double-clicking the name of any other layer type only renames it.

<!-- SCREENSHOT: Camera Properties dialog with Camera name and Camera size (width, height) fields -->

> **Tip:** For HD video, a common choice is 1920 × 1080; for 720p, 1280 × 720. Set the size before
> you start drawing so your layout fits the frame from the beginning.

## The Camera tool {#camera-tool}

There is no separate camera button in the toolbox. To move the camera:

1. Select the camera layer in the timeline.
2. Choose the **Move** tool (<kbd>M</kbd>). While a camera layer is selected, the Move tool acts as
   the camera tool, and the status bar reads "Click and drag to move the camera. While on in-between
   frames, drag handle to change interpolation."
3. Move the playhead to a camera keyframe.

If you switch to another layer while the camera tool is active, the Move tool goes back to moving
artwork. The camera layer must be visible; if it is hidden, Pencil2D warns you instead of moving it.

The camera field gets handles when you are on a keyframe. On frames between keyframes the handles
turn gray; you can't transform the camera there, but you can bend its path (see
[Camera path](#camera-path)).

<!-- SCREENSHOT: Camera tool on a camera keyframe: camera field with four square corner handles, the round rotation handle above the top edge, and the "100%" reference rectangle -->

| To | Do this |
|---|---|
| Move (translate) | Drag anywhere inside the camera field |
| Rotate | Drag the round handle above the top edge |
| Rotate in steps | Hold <kbd>Shift</kbd> while dragging the rotation handle |
| Scale (zoom) | Drag any square corner handle |

- **Rotation steps** follow **Rotation snap increment** in
  [Preferences → Tools]({{ '/doc/manual/preferences.html#tools' | relative_url }}) (15 degrees by default).
- **Scaling** keeps the camera's proportions and works from its center. Dragging a corner outward
  makes the camera field bigger, so objects look smaller in the export (zoom out). Dragging inward
  makes objects look bigger (zoom in).
- A thin rectangle labeled **100%** shows the camera field at its normal size, for reference.
- **Red outline:** when you scale the camera field smaller than 100%, its outline turns red. That
  frame is enlarged on export, so bitmap drawings may look blurry or pixelated.

| Translate | Rotate | Scale |
|---|---|---|
| <video src="{{ '/images/pencil2d-0.7.0-camera-translate.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video> | <video src="{{ '/images/pencil2d-0.7.0-camera-rotate.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video> | <video src="{{ '/images/pencil2d-0.7.0-camera-scale.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video> |

> **Tip:** Moving the camera doesn't move your view of the canvas. To pan or zoom your view,
> use the [Hand tool]({{ '/doc/manual/tools.html#hand' | relative_url }}) or the other methods in
> [Canvas and View]({{ '/doc/manual/canvas.html#pan' | relative_url }}).

## Camera options in Tool Options {#camera-options}

When the camera tool is active, the [Tool Options]({{ '/doc/manual/interface.html#tool-options' | relative_url }}) panel
shows two groups.

![Camera options in the Tool Options panel]({{ "/images/pencil2d-0.7.0-camera-options.png" | relative_url }})

**Transform** resets the keyframe at the current frame. If you are between keyframes, it resets the
previous keyframe.

| Option | What it does |
|---|---|
| **Reset all** | Resets position, rotation and scale |
| **Reset** – move icon (**Reset translation**) | Moves the camera back to the center of the canvas |
| **Reset** – rotate icon (**Reset rotation**) | Sets rotation back to 0 |
| **Reset** – scale icon (**Reset scaling**) | Sets scale back to 100% |

**Camera path** controls the path overlay of the selected camera layer. Both settings are saved with
that camera layer in the project.

| Option | What it does | Default |
|---|---|---|
| **Show path** | Shows the camera's path between keyframes on the canvas | Off |
| Path color list | Color of the path dots: **Red**, **Blue**, **Green**, **Black** or **White** | Red |
| **Reset path** | Straightens the path segment the current frame is in | – |

<video src="{{ '/images/pencil2d-0.7.0-camera-options.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## Camera keyframes and interpolation {#camera-keyframes}

A camera move needs at least two keyframes. To add one, select the camera layer, move to a frame and
use **Animation → Add Frame** (<kbd>F7</kbd>) or the add-frame button in the timeline. The new
keyframe starts at the position, size and rotation the camera already had on that frame, so adding a
keyframe in the middle of a move doesn't make the camera jump. Then change it with the camera tool.

You can move, duplicate, copy and delete camera keyframes like any other keyframes; see
[Timeline and Animation]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}).

Between two keyframes, Pencil2D blends:

- **position** along the camera path, which is straight unless you bend it,
- **rotation** and **scale** evenly from one keyframe's values to the next,

all timed by the easing set on the first keyframe of the pair. New keyframes use **Linear**, which
moves at a constant speed.

## Easing {#easing}

Easing changes the timing of a camera move. It can start slowly and speed up, slow down into the
next keyframe, overshoot, bounce, and so on. It applies to position, rotation and scale together.

To set the easing between two keyframes, **right-click the first keyframe** of the pair in the
timeline and open **Easing: frame *X* to *Y***. The first line, **Selected:**, shows the current
easing. The submenu is unavailable on the last keyframe, because nothing follows it.

<video src="{{ '/images/pencil2d-0.7.0-camera-easings.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

The menu has **Linear** plus four groups:

- **In**: starts slowly, then speeds up into the next keyframe.
- **Out**: starts fast, then slows down into the next keyframe.
- **In-Out**: slow at both ends, fastest in the middle.
- **Out-In**: fast at both ends, slowest in the middle.

Each group offers the same ten curves: **Slow**, **Moderate**, **Quick**, **Fast**, **Faster** and
**Fastest** differ in how strong the acceleration is. **Circle-based** follows a circular curve,
**Overshoot** goes a little past the target and comes back, **Elastic** springs back and forth, and
**Bounce** bounces against the end position.

The **Selected:** line and the camera path show a longer name for each choice:

| Menu choice | Name shown for **In** | **Out** | **In-Out** | **Out-In** |
|---|---|---|---|---|
| Slow | Slow Ease-in | Slow Ease-out | Slow Ease-in - Ease-out | Slow Ease-out - Ease-in |
| Moderate | Moderate Ease-in | Moderate Ease-out | Moderate Ease-in - Ease-out | Moderate Ease-out - Ease-in |
| Quick | Quick Ease-in | Quick Ease-out | Quick Ease-in - Ease-out | Quick Ease-out - Ease-in |
| Fast | Fast Ease-in | Fast Ease-out | Fast Ease-in - Ease-out | Fast Ease-out - Ease-in |
| Faster | Faster Ease-in | Faster Ease-out | Faster Ease-in - Ease-out | Faster Ease-out - Ease-in |
| Fastest | Fastest Ease-in | Fastest Ease-out | Fastest Ease-in - Ease-out | Fastest Ease-out - Ease-in |
| Circle-based | Circle-based Ease-in | Circle-based Ease-out | Circle-based Ease-in - Ease-out | Circle-based Ease-out - Ease-in |
| Overshoot | Overshoot Ease-in | Overshoot Ease-out | Overshoot Ease-in - Ease-out | Overshoot Ease-out - Ease-in |
| Elastic | Elastic Ease-in | Elastic Ease-out | Elastic Ease-in - Ease-out | Elastic Ease-out - Ease-in |
| Bounce | Bounce Ease-in | Bounce Ease-out | Bounce Ease-in - Ease-out | Bounce Ease-out - Ease-in |

**Linear** is shown as "Linear". That makes 41 easings in all.

> **Tip:** **In-Out → Slow** or **In-Out → Moderate** gives most pans a natural start and stop.
> Keep **Elastic** and **Bounce** for comic effects.

## The camera context menu {#context-menu}

Right-click a camera keyframe in the timeline to open this menu. It appears only when you click
directly on a camera keyframe. *X* is the keyframe you clicked and *Y* is the next keyframe.

| Item | What it does |
|---|---|
| **Easing: frame *X* to *Y*** | Sets the easing for the move from *X* to *Y*; see [Easing](#easing) |
| **Transform → Reset all** | Resets position, scale and rotation of keyframe *X* |
| **Transform → Reset position** | Moves keyframe *X* back to the center of the canvas |
| **Transform → Reset scale** | Sets the scale of keyframe *X* back to 100% |
| **Transform → Reset rotation** | Sets the rotation of keyframe *X* back to 0 |
| **Transform → Align horizontally to frame *Y*** | Gives keyframe *Y* the same vertical position as *X*, so the camera moves in a straight horizontal line |
| **Transform → Align vertically to frame *Y*** | Gives keyframe *Y* the same horizontal position as *X*, so the camera moves in a straight vertical line |
| **Transform → Hold to keyframe *Y*** | Copies the position, scale and rotation of *X* to *Y*, so the camera stays still between them |

The last three items are unavailable on the last keyframe. They also straighten the path between *X*
and *Y*.

## Camera path {#camera-path}

With **Show path** turned on in [Tool Options](#camera-options), the camera tool draws the route the
camera's center takes:

- a dot for every frame between two keyframes that have different positions (the dots of the
  segment you are in are drawn more strongly),
- a solid dot marking the camera's center on the current frame,
- a square handle on each segment with at least one in-between frame, labeled with that segment's
  easing,
- dashed guide lines from the handle to the two keyframe positions.

Spacing between the dots shows the speed: dots close together mean slow movement, and dots far apart
mean fast movement. That makes the path a handy way to check an easing.

**To curve the path:**

1. Turn on **Show path**.
2. Move the playhead to a frame *between* keyframes. On a keyframe, the path handles are gray and
   can't be moved.
3. Drag the square handle. The segment bends into a smooth curve.

The handle bends only the route. To change where the camera starts or ends, go to that keyframe and
move the camera itself. To straighten a segment again, go to a frame in it and click **Reset path**.
If you add a keyframe in the middle of a curved segment, Pencil2D splits the curve so the path keeps
its shape.

<video src="{{ '/images/pencil2d-0.7.0-camera-path.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

The handles and path appear only while the camera tool is active. During playback the handles
are hidden.

## Camera onion skin {#camera-onion-skin}

[Onion skin]({{ '/doc/manual/onion-skin.html' | relative_url }}) works on camera layers too. Instead of drawings, you see
dashed outlines of the camera field on the neighboring frames, drawn for every camera layer. It
follows the same settings as drawing onion skins:

- **Previous Frames** and **Next Frames** turn earlier and later outlines on or off, and set how many
  are shown.
- The red and blue color buttons draw previous outlines in red and next outlines in blue.
- **Show Keyframes Only** outlines only camera keyframes instead of every in-between frame.
- **Show During Playback** keeps the outlines visible while playing.

See [Onion Skin]({{ '/doc/manual/onion-skin.html#onion-skin-panel' | relative_url }}) for the panel itself.

<video src="{{ '/images/pencil2d-0.7.0-camera-onion-skins.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

## Worked example: pan and zoom {#example}

This example pans across a wide background and then zooms in on a detail.

1. **Draw the background.** On a bitmap layer, draw a landscape that extends well past the left and
   right edges of the camera field. Zoom your view out so you can see all of it.
2. **Select the camera.** Click the camera layer in the timeline and press <kbd>M</kbd> for the
   Move tool. Frame 1 already has a camera keyframe.
3. **Set the start.** On frame 1, drag inside the camera field to put it over the left end of the
   background.
4. **Set the end of the pan.** Go to frame 36 and press <kbd>F7</kbd> to add a camera keyframe.
   Drag the camera to the right end of the background.
5. **Zoom in.** Go to frame 48, press <kbd>F7</kbd>, and drag a corner handle inward until the
   detail you want fills the camera field. Rotate it slightly with the round handle if you like.
6. **Ease the moves.** Right-click the keyframe on frame 1 and choose
   **Easing: frame 1 to 36 → In-Out → Slow**. Right-click frame 36 and choose
   **Easing: frame 36 to 48 → Out → Moderate**, so the zoom slows down as it arrives.
7. **Check it.** Turn on **Show path** to see the dots, then press Play (see
   [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }})). The canvas view stays put while the camera
   field moves; the export shows only what is inside the camera field.
8. **Export.** Use **File → Export → Movie...** and make sure the right camera is selected in the
   **Camera** list.

> **Tip:** In step 5 the camera field outline turns red, because the zoomed-in shot is enlarged on
> export. To keep a bitmap close-up sharp, plan the other way around: keep the close-up at 100% and
> scale the camera field *up* (outward) for the wide shots. Draw the artwork large enough for that.

{% include series-nav.html series=site.data.manual %}
