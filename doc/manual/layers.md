---
layout: page
title: Layers
tagline: Layer types, managing layers, visibility and opacity
comments: false
---

Layers let you keep different parts of an animation apart, such as the background, a character, and the camera, so you can draw, time and change each one without touching the others. This chapter explains the four layer types and how to add, rename, reorder, duplicate, hide and delete layers, and how to fade layers and keyframes in and out.

Shortcuts are written in Windows/Linux form. On macOS, use <kbd>Cmd</kbd> in place of <kbd>Ctrl</kbd> and <kbd>Option</kbd> in place of <kbd>Alt</kbd>.

{% include toc.html %}

## Layer types {#layer-types}

Pencil2D has four kinds of layer. Each one holds a different kind of keyframe.

| Type | What it holds | Use it for |
|---|---|---|
| **Bitmap** | Pixel drawings | Most hand-drawn animation: sketching, painting, shading, imported images |
| **Vector** | Strokes and fills stored as editable curves, linked to palette colors | Clean line art that you want to reshape, rescale or recolor later |
| **Camera** | Camera position, rotation and zoom at each keyframe | Framing the shot, pans and zooms, and choosing what gets exported |
| **Sound** | Sound clips | Dialogue, music and sound effects |

- **Bitmap layers** work like paper: what you draw becomes pixels. Colors are copied from the current color when you draw. Zooming in far shows the pixels.
- **Vector layers** store each stroke as a curve, so lines stay sharp at any zoom. Strokes and fills use palette swatches, so changing a swatch recolors the drawing everywhere. See [Colors on bitmap and vector layers]({{ '/doc/manual/color.html#vector-colors' | relative_url }}). Some tools behave differently on vector layers; see [Tools]({{ '/doc/manual/tools.html' | relative_url }}).
- **Camera layers** define the frame that is exported. Every project needs at least one. See [Camera]({{ '/doc/manual/camera.html#camera-layer' | relative_url }}).
- **Sound layers** hold audio clips that play along with the animation. See [Sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}).

You can only draw on bitmap and vector layers. A new project starts with a camera layer and a bitmap layer; you can change this with a [project preset]({{ '/doc/manual/projects.html#presets' | relative_url }}).

## The layer list {#layer-list}

The layers are listed on the left side of the [Timeline]({{ '/doc/manual/timeline.html#anatomy' | relative_url }}), one row per layer, next to that layer's frames. Each row shows, from left to right:

- **A visibility dot.** A filled dot means the layer is shown; an empty dot means it is hidden. When a [layer visibility mode]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}) hides or dims the other layers, their dots are drawn empty or gray as well. See [Showing and hiding layers](#hiding-layers).
- **An icon** for the layer type (bitmap, vector, sound or camera).
- **The layer name.**

Above the list are the **Layers:** buttons: **Add Layer**, **Delete Layer** and **Duplicate Layer**.

![The Timeline panel: the layer list on the left, with the Layers: buttons above it]({{ "/images/manual/timeline.png" | relative_url }})

### The current layer {#current-layer}

The **current layer** is the one you draw on and the one that layer commands act on. Its row in the layer list is highlighted.

To make a layer current, click its name in the layer list, or click any frame in its row of the timeline. When the canvas has keyboard focus and nothing is selected, you can also press <kbd>Up</kbd> to move to the layer above and <kbd>Down</kbd> to move to the layer below.

## Managing layers {#managing-layers}

### Adding layers {#adding-layers}

To add a layer, do one of the following:

- Click **Add Layer** (the plus button above the layer list) and choose **New Bitmap Layer**, **New Vector Layer**, **New Sound Layer** or **New Camera Layer**.
- Use the **Layer** menu, which has the same four commands.
- Press the shortcut:

| Command | Shortcut |
|---|---|
| **New Bitmap Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd> |
| **New Vector Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>V</kbd> |
| **New Sound Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>W</kbd> |
| **New Camera Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>C</kbd> |

A **Layer Properties** dialog asks for a **Layer name:**. It suggests a name such as "Bitmap Layer", adding a number ("Bitmap Layer 2") if that name is taken. Click **OK** to create the layer, or **Cancel** to stop.

The new layer is placed at the top of the list, above all other layers, and becomes the current layer.

Some imports, such as importing a sound, can also create a layer for you; see [Importing and Exporting]({{ '/doc/manual/import-export.html' | relative_url }}).

### Renaming layers {#renaming-layers}

To rename a layer, double-click its name in the layer list. In the **Layer Properties** dialog, type a new name and click **OK**. Double-click the name itself, not the visibility dot, which only toggles visibility.

Double-clicking a camera layer opens **Camera Properties** instead, where you can change both its name and the camera size. See [Layer properties](#layer-properties).

### Duplicating layers {#duplicating-layers}

To copy a layer with all of its keyframes, make it the current layer and click **Duplicate Layer** above the layer list. The copy is named after the original with " (copy)" added, for example "Bitmap Layer (copy)", and is placed at the top of the list.

This works for every layer type. Duplicating is useful for keeping a backup of a layer before a big change, or as a starting point for a variation.

### Deleting layers {#deleting-layers}

To delete the current layer, click **Delete Layer** above the layer list, or choose **Layer → Delete Current Layer**. Pencil2D asks you to confirm: *"Are you sure you want to delete layer: … ? This cannot be undone."* Click **OK** to delete it.

> **Warning:** Deleting a layer cannot be undone. If you might want the layer back, [duplicate](#duplicating-layers) it or [hide](#hiding-layers) it instead.

Some layers can't be deleted:

- The bottom layer of the list. **Delete Layer** is disabled while it is the current layer.
- The last remaining camera layer. Pencil2D shows *"Please keep at least one camera layer in project"*.

**Delete Current Layer** has no default shortcut. You can assign one in [Preferences]({{ '/doc/manual/preferences.html#shortcuts' | relative_url }}).

### Reordering layers {#reordering-layers}

To move a layer, drag its name up or down in the layer list. A line shows where it will go. Release to drop it there.

The bottom layer of a new project is the camera layer, and it stays at the bottom: you can't drag it up, and you can't drag another layer below it.

There are no menu commands or shortcuts for moving layers; use dragging.

### Layer order and drawing order {#layer-order}

Layers are drawn from the bottom of the list to the top. A layer higher in the list covers the layers below it, like sheets of transparent film stacked on a light table. Put your background near the bottom and characters and foreground elements above it.

The order of sound layers doesn't matter; all visible sound layers play together.

## Showing and hiding layers {#hiding-layers}

To hide or show a layer, click the dot at the left end of its row in the layer list. A hidden layer:

- is not shown on the canvas,
- is left out when you export images or movies,
- can't be drawn on. If you try, Pencil2D warns: *"You are trying to modify a hidden layer! Please select another layer (or make the current layer visible)."*

Hiding a sound layer mutes it during playback and leaves it out of exported movies.

Whether each layer is shown or hidden is saved with the project.

Separately from hiding individual layers, the **View → Layer Visibility** modes control how the *other* layers look while you work: all shown, dimmed, or hidden, leaving only the current layer. Clicking the dot in the header row above the layer list cycles through these modes. See [Layer visibility]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}).

> **Note:** Pencil2D 0.7.2 has no way to lock a layer against changes. To protect a layer while you work on others, hide it, or keep the current layer set to the one you mean to draw on.

## Layer and keyframe opacity {#opacity}

You can make a whole layer, or individual keyframes, partly transparent. This is useful for fading a drawing in or out, for ghosts and reflections, or for making a background less prominent.

To open the controls, choose **Layer → Layer / Keyframe opacity**. The **Layer / Keyframe Opacity** window stays open on top of the main window while you keep working, so you can change frames, layers and selections with it open. It works on bitmap and vector layers only; for other layer types its controls are disabled.

![The Layer / Keyframe Opacity dialog]({{ "/images/pencil2d-0.7.0-opacity.png" | relative_url }})

The top line shows which layer you are adjusting (**Layer:** followed by its name). Set the opacity with the slider or the number box (0–100%, in 0.2% steps). The change applies immediately to whatever you chose under **Set opacity for:**:

| Option | What it changes |
|---|---|
| **Active keyframe** | The keyframe shown at the current frame (the default) |
| **Selected keyframe(s)** | All keyframes selected in the timeline. Available when at least three keyframes are selected. |
| **Layer** | Every keyframe that currently exists on the layer |

Opacity is stored on each keyframe. **Layer** sets all existing keyframes at once; keyframes you add later start at 100%.

### Fading in and out {#fading}

The **Fade in / Fade out** buttons spread a gradual change in opacity over several keyframes:

1. In the timeline, select at least three keyframes on the current layer. The buttons are disabled until you do.
2. Click **Fade in** or **Fade out**.

The fade uses the first (leftmost) selected keyframe as its starting point:

- **Fade in** goes from that keyframe's opacity up to 100% at the last selected keyframe. If the first keyframe is already at 100%, the fade starts from 0%.
- **Fade out** goes from that keyframe's opacity down to 0% at the last selected keyframe. If the first keyframe is already at 0%, the fade starts from 100%.

Fading always applies to the selected keyframes, whichever **Set opacity for:** option is chosen.

Click **Close** when you are done.

> **Note:** As the window says, *"Be aware that opacity changes are made in the rendering, and will not change your artwork."* Opacity only affects how the keyframe is shown and exported. The drawing itself is untouched, so you can set it back to 100% at any time.

## Layer properties {#layer-properties}

Bitmap, vector and sound layers have only one property, the name; see [Renaming layers](#renaming-layers).

Camera layers have a **Camera Properties** dialog with **Camera name:** and **Camera size:**. Open it by double-clicking the camera layer's name. The camera size sets the resolution of the exported frame; see [Camera size]({{ '/doc/manual/camera.html#camera-size' | relative_url }}).

## Importing layers from another project {#import-layers}

To copy layers from another Pencil2D project into the current one, choose **File → Import → Layers from Project file...**:

1. Click **Select File** and choose the project file.
2. In the list, select one or more layers. Hold <kbd>Ctrl</kbd> or <kbd>Shift</kbd> to select several.
3. Click **Import layers**, then **Close**.

Imported layers are added at the top of the layer list, with all their keyframes. If a name is already taken, a number is added. Colors used by imported vector layers are added to the end of your palette so the drawings keep their original colors. For more on importing, see [Importing and Exporting]({{ '/doc/manual/import-export.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
