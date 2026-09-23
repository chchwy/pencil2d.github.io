---
layout: page
title: Selecting and Transforming
tagline: Select, move, scale, rotate and flip artwork, use the clipboard, and align scanned drawings
comments: false
---

This chapter explains how to select part of a drawing and change it: move it, scale it, rotate
it, flip it, delete it, or copy it to another frame. It also covers the clipboard and the Peg Bar
Alignment dialog for lining up scanned drawings. For a short summary of the Select and Move tools
alongside the other tools, see [Tools]({{ '/doc/manual/tools.html#select' | relative_url }}).

> **Note:** Shortcuts are written for Windows and Linux. On macOS, press <kbd>Cmd</kbd> wherever
> this page says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.
> Preferences are under **Edit → Preferences** on Windows and Linux, and under the **Pencil2D**
> application menu on macOS.

{% include toc.html %}

## Select tool and Move tool {#select-and-move}

Two tools work together:

- The **Select** tool (<kbd>V</kbd>) draws and adjusts the *selection*, a rectangle that marks the
  part of the drawing you want to work on. It never changes the drawing itself.
- The **Move** tool (<kbd>M</kbd>) changes what is inside the selection: it moves, scales and
  rotates it.

Both tools work on bitmap and vector layers. A selection belongs to the current frame of the current
layer. On a camera layer, the Move tool moves the camera instead; see
[Camera]({{ '/doc/manual/camera.html#camera-tool' | relative_url }}).

Both tools have one option in the **Tool Options** panel, **Show Size and Diff.** When it is on,
text next to the selection shows its size and how far its center has moved, for example
`Size: 200x100. Diff: 12, -4.` The size is the selection's original size in canvas pixels; it
does not change while you scale. The Diff is measured in screen pixels, so the same move shows
larger numbers when you are zoomed in. A positive second number means the selection moved up.
Each tool has its own checkbox, but both save to the same setting, so whichever you changed last
applies to both the next time Pencil2D starts.

## Making a selection {#making-a-selection}

To select part of a drawing:

1. Choose the **Select** tool (<kbd>V</kbd>).
2. Drag a rectangle around the part you want.

A dashed rectangle (bitmap layers) or a gray shaded rectangle (vector layers) shows the selection,
with a square handle at each corner. On bitmap layers the rectangle snaps to whole pixels.

With the Select tool you can then adjust the selection:

| Action | What it does |
|---|---|
| Drag a corner handle | Resizes the selection rectangle; the drawing is not changed |
| Drag inside the selection | Moves the selection rectangle; the drawing stays where it is |
| Drag outside the selection | Starts a new selection that replaces the old one |
| Click outside the selection without dragging | Removes the selection |
| Hold <kbd>Alt</kbd> | Switches to the Move tool while the key is held, so you can move or scale the contents |
| <kbd>Backspace</kbd> | Deletes the contents of the selection |

<!-- SCREENSHOT: A bitmap drawing with a dashed selection rectangle and its four corner handles, with "Show Size and Diff." turned on -->

### Select All and Deselect All {#select-all}

- **Edit → Select All** (<kbd>Ctrl</kbd>+<kbd>A</kbd>) selects everything on the current frame. On
  a bitmap layer the selection fits snugly around the drawing, however large it is; on a vector
  layer, every stroke and fill is selected.
- **Edit → Deselect All** (<kbd>Ctrl</kbd>+<kbd>D</kbd>) removes the selection. It also clears any
  frames selected in the timeline.

### Selecting on vector layers {#vector-selection}

On a vector layer the selection picks whole strokes and filled areas, not pixels:

- A stroke is selected if any part of it touches the rectangle you drag.
- A filled area is selected only if it lies completely inside the rectangle.
- When you release the mouse, the selection rectangle changes to fit tightly around the selected
  strokes. If nothing was selected, the selection disappears.

Selected strokes are highlighted in blue, and selected fills are shown with a dotted pattern.

With the **Move** tool, while a selection exists, you can click a stroke or a filled area outside
the selection to select it instead, or <kbd>Shift</kbd>+click to add it to the selection. With
nothing selected, clicking a stroke with the Move tool does nothing.

To edit the individual points (vertices) of a vector stroke, use the Smudge tool; see
[Tools]({{ '/doc/manual/tools.html#smudge' | relative_url }}).

## Transforming {#transforming}

To move, scale or rotate part of a drawing, select it first, then choose the **Move** tool
(<kbd>M</kbd>). The Move tool only works on a selection; with nothing selected, dragging on the
canvas does nothing (except moving [perspective]({{ '/doc/manual/canvas.html#perspective' | relative_url }}) vanishing
points).

| Action with the Move tool | What it does |
|---|---|
| Drag inside the selection | Moves the contents |
| <kbd>Shift</kbd>+drag inside the selection | Moves the contents straight horizontally or vertically, whichever way you drag further |
| Drag a corner handle | Scales the contents; the opposite corner stays in place |
| <kbd>Shift</kbd>+drag a corner handle | Scales while keeping the width-to-height ratio |
| <kbd>Ctrl</kbd>+drag inside the selection | Rotates the contents around the center of the selection |
| <kbd>Ctrl</kbd>+drag, then also hold <kbd>Shift</kbd> | Rotates in fixed steps (15 degrees by default) |
| Arrow keys | Move the contents by one pixel in that direction |

<video src="{{ '/images/pencil2d-0.7.0-selection-transform-new.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

The selection rectangle turns and stretches along with the contents, so you can always see
exactly what you are changing. You can combine moves, scales and rotations before you apply them.

To rotate, you must already be holding <kbd>Ctrl</kbd> when you press the mouse button. Add
<kbd>Shift</kbd> during the drag to snap. Change the step size with **Rotation snap increment** in
**Preferences → Tools → Move Tool**. The slider only offers values that divide evenly into 360
degrees.

The arrow keys, <kbd>Enter</kbd>, <kbd>Escape</kbd> and <kbd>Backspace</kbd> act on the selection
only while the pointer is over the canvas, because the canvas needs keyboard focus. Without a
selection, the arrow keys go to other frames and layers instead.

### Applying and cancelling {#apply-cancel}

A transformation is only a preview until it is applied. Until then the original drawing is
unchanged underneath.

- **Apply:** press <kbd>Enter</kbd>, or click outside the selection with the Move tool. Both apply
  the change and remove the selection.
- **Cancel:** press <kbd>Escape</kbd>. The contents jump back to where they were and the selection
  is removed.

Pencil2D also applies a pending transformation for you when you go to another frame, switch to
another layer, or switch from the Move tool to another tool. There is no dialog asking whether to
apply it; that dialog was removed in Pencil2D 0.7.0.

To keep working on the same selection after clicking elsewhere, hold <kbd>Shift</kbd> while you
click outside it with the Move tool; the selection stays active.

Every transformation can be undone with **Edit → Undo** (<kbd>Ctrl</kbd>+<kbd>Z</kbd>).

> **Warning:** Apply a transformation with <kbd>Enter</kbd> before using **Deselect All**, or
> before clicking on the canvas with the Select tool. Both remove the selection, and may throw
> away a change that hasn't been applied yet.
<!-- VERIFY: Editor::deselectAll() and SelectTool's click-to-deselect call resetSelectionProperties() without applying the pending transform (e.g. a Flip X made while the Select tool is active). Confirm whether the change is lost in the 0.7.2 build. -->

> **Tip:** Transform drawings while the playhead is on their keyframe. On a frame that only
> holds an earlier drawing, a bitmap transformation follows the **When drawing on an empty frame**
> setting in **Preferences → Timeline**, and a vector transformation changes the earlier keyframe.
<!-- VERIFY: exact results of applying a bitmap transform on a held (non-key) frame under each "When drawing on an empty frame" option. -->

### Flipping the selection {#flip-selection}

To mirror the selected artwork, use **Edit → Selection → Flip X** (left to right) or
**Edit → Selection → Flip Y** (upside down). The flip happens around the center of the original
selection. The **Selection** submenu is only available while something is selected.

The flip is part of the pending transformation: press <kbd>Enter</kbd> to apply it. These commands
have no default shortcuts, but you can assign them in **Preferences → Shortcuts** as
**Selection: Horizontal Flip** and **Selection: Vertical Flip**.

To mirror only your view of the canvas, see [Flip the view]({{ '/doc/manual/canvas.html#flip' | relative_url }}).

## Deleting and clearing {#deleting}

- **Delete the selected contents:** press <kbd>Backspace</kbd>. The <kbd>Delete</kbd> key does
  not do this by default.
- **Cut** (<kbd>Ctrl</kbd>+<kbd>X</kbd>) deletes the selected contents after copying them; see
  [Clipboard](#clipboard).
- **Edit → Clear Frame** erases the whole drawing on the current frame of the current layer, with
  or without a selection. It is also a button on the Main Toolbar and has no default shortcut.

> **Note:** **Clear Frame** clears the drawing you see. If the current frame holds a drawing from
> an earlier keyframe, that keyframe is the one that gets cleared.

All of these can be undone.

## Clipboard {#clipboard}

| Command | Menu | Default shortcut |
|---|---|---|
| **Cut** | **Edit → Cut** | <kbd>Ctrl</kbd>+<kbd>X</kbd> |
| **Copy** | **Edit → Copy** | <kbd>Ctrl</kbd>+<kbd>C</kbd> |
| **Paste** | **Edit → Paste** | <kbd>Ctrl</kbd>+<kbd>V</kbd> |
| **Paste from Previous Keyframe** | **Edit → Paste from Previous Keyframe** | <kbd>Ctrl</kbd>+<kbd>Left</kbd> |

**Cut**, **Copy** and **Paste** are also on the Main Toolbar.

### Copy and cut {#copy}

- **Bitmap layers:** **Copy** copies the contents of the selection. With no selection, it copies
  the whole drawing on the current frame. The copied image is also placed on your system
  clipboard, so you can paste it into other programs.
- **Vector layers:** **Copy** always copies the whole drawing on the current frame, even if only
  part of it is selected. Vector artwork is not placed on the system clipboard.
- **Cut** copies in the same way, then deletes the selected contents and removes the selection.
  Without a selection, **Cut** copies but deletes nothing.

If frames are selected in the timeline and nothing is selected on the canvas, **Copy** and **Cut**
work on those keyframes instead; see [Timeline]({{ '/doc/manual/timeline.html#copy-paste' | relative_url }}).

### Paste {#paste}

To paste in place, go to the frame you want and press <kbd>Ctrl</kbd>+<kbd>V</kbd>. Pasted bitmap
artwork lands exactly where it was copied from, which makes it easy to carry part of a drawing
over to the next frame. If there is no keyframe on the current frame, Pencil2D first follows the
**When drawing on an empty frame** setting in **Preferences → Timeline**.

After pasting, the pasted area is selected, so you can switch to the Move tool and position it.

> **Warning:** On bitmap layers the pasted image is merged into the drawing straight away. The
> selection around it also contains anything that was already underneath, and moving it moves
> that too. Paste onto an empty area, or onto a new layer, if you want to move the pasted part on
> its own.

If a selection exists when you paste on a bitmap layer, the pasted image goes into it: an image
that fits is placed at the selection's top-left corner, and a larger image is stretched to fill
the selection exactly, without keeping its proportions.

**Pasting from other programs:** copy an image in another program, then paste it on a bitmap
layer. It is placed in the middle of the part of the canvas you are looking at. Images from other
programs can't be pasted on vector layers.

There is no command to paste into a new layer. Add a layer first, then paste.

### Paste from Previous Keyframe {#paste-previous}

**Edit → Paste from Previous Keyframe** (<kbd>Ctrl</kbd>+<kbd>Left</kbd>) copies the drawing from
the previous keyframe on the same layer onto the current keyframe, in the same position. It only
works when the current frame is a keyframe and there is an earlier keyframe on the layer. On
bitmap layers, if you have a selection, only the part of the previous drawing inside the
selection is pasted.

## Peg bar alignment {#peg-bar-alignment}

When you scan drawings made on paper, each sheet ends up in a slightly different position.
Animation paper has peg holes that keep the sheets aligned on the desk; **Edit → Peg bar Alignment**
uses a mark on each drawing, such as the peg holes, to line up all the scanned drawings on one or
more bitmap layers automatically.

<!-- SCREENSHOT: The Peg bar Alignment dialog with its Prerequisites list, the Layer selection list with one layer selected, "Reference key:" showing a frame number, and the Align button enabled -->

### How it finds the mark {#peg-mark}

Inside the selection rectangle, Pencil2D looks for fully opaque pixels darker than medium gray.
It takes the leftmost column and the topmost row that contain such a pixel, and uses that point as
the drawing's position. Then it moves each drawing so that its point matches the point in the
reference drawing.

For this to work, on every keyframe:

- A dark, solid mark (a peg hole that scanned dark, or a registration mark) is inside the
  selection rectangle.
- Nothing else dark is inside the rectangle.
- White paper doesn't count, but gray scanner noise or smudges near the mark might.

### Aligning drawings {#aligning}

1. Make the layer with the correctly placed drawing the current layer, and go to that drawing's
   keyframe. The playhead must be exactly on the keyframe. This drawing is the **reference key**.
2. Open **Edit → Peg bar Alignment**. Pencil2D switches to the Select tool and, if nothing is
   selected, creates a 200 × 100 pixel selection in the middle of the view.
3. Adjust the selection so that it surrounds the peg mark, with enough room to include the mark on
   every other drawing too. Use [onion skin]({{ '/doc/manual/onion-skin.html' | relative_url }}) to check the other
   drawings: going to another frame or layer removes the selection.
4. Under **Layer selection**, click each bitmap layer you want to align. You can select several;
   click a layer again to deselect it. The first layer in the list is selected when the dialog
   opens.
5. Click **Align**.

The dialog lists three **Prerequisites**: a selection exists, the selection is large enough to
contain the pegs of all frames, and at least one layer is selected. **Align** is enabled once a
selection exists, at least one layer is selected, and the current layer is a bitmap layer with a
keyframe, whose frame number is shown next to **Reference key:**. Pencil2D can't check whether the
selection is large enough; if it isn't, you'll get an error when you click **Align**.

Every keyframe on the selected layers is shifted, without resampling, so that its mark matches
the reference. When it finishes, the selection is removed and the dialog closes. The dialog stays
on top of the main window while it is open, so you can still use the canvas.

If Pencil2D can't find a mark, it stops and shows a message:

- **Peg hole not found! Check selection, and please try again.** No mark was found inside the
  selection on the reference key.
- **Peg bar not found at** *layer*, *frame*: no mark was found on that keyframe. Drawings that were
  processed before it have already been moved.

> **Warning:** Peg bar alignment can't be undone with **Edit → Undo**. Save your project before
> aligning, so you can go back if the result isn't what you expected.

> **Note:** Layers are matched by name. If two bitmap layers have the same name, rename one of them
> before aligning.

{% include series-nav.html series=site.data.manual %}
