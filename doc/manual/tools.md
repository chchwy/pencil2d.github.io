---
layout: page
title: Tools
tagline: Every drawing and editing tool, and all of its options
comments: false
---

This chapter is the reference for every tool in the **Tools** panel: what each one does on bitmap and vector layers, every setting in the **Options** panel, and the modifier keys you can hold while using it. Read the tool sections as you need them, and read [Common Options](#common-options) once, because most drawing tools share the same settings.

Shortcuts are written in Windows/Linux form. On macOS, use <kbd>Cmd</kbd> in place of <kbd>Ctrl</kbd> and <kbd>Option</kbd> in place of <kbd>Alt</kbd>.

{% include toc.html %}

## The toolbox at a glance {#overview}

You pick a tool by clicking it in the **Tools** panel (see [The Interface]({{ '/doc/manual/interface.html#toolbox' | relative_url }})), from the **Tools** menu, or with its single-key shortcut. The settings of the current tool appear in the **Options** panel ([Tool Options]({{ '/doc/manual/interface.html#tool-options' | relative_url }})). Shortcuts can be changed in **Preferences → Shortcuts** (see [Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }})).

The tools, in the order they appear in the toolbox:

| Tool | Shortcut | Bitmap | Vector | What it is for |
|---|---|---|---|---|
| [Pencil](#pencil) | <kbd>N</kbd> | Yes | Yes | Sketching with a soft, pencil-like line |
| [Eraser](#eraser) | <kbd>E</kbd> | Yes | Yes | Erasing pixels, or points of vector strokes |
| [Select](#select) | <kbd>V</kbd> | Yes | Yes | Making a rectangular selection |
| [Move](#move) | <kbd>M</kbd> | Yes | Yes | Moving, scaling and rotating the selection |
| [Pen](#pen) | <kbd>P</kbd> | Yes | Yes | Clean, hard-edged ink lines |
| [Hand](#hand) | <kbd>H</kbd> | Yes | Yes | Panning, zooming and rotating the view |
| [Polyline](#polyline) | <kbd>Y</kbd> | Yes | Yes | Straight or curved lines built from clicked points |
| [Bucket](#bucket) | <kbd>K</kbd> | Yes | Yes (selected strokes only) | Filling areas with color |
| [Eyedropper](#eyedropper) | <kbd>I</kbd> | Yes | Yes | Picking a color from the drawing |
| [Brush](#brush) | <kbd>B</kbd> | Yes | Yes | Soft, painterly strokes |
| [Smudge](#smudge) | <kbd>A</kbd> | Yes | Yes | Smearing pixels, or reshaping vector strokes |

On a **camera layer**, the Move button becomes the **Camera** tool; see [Camera tool]({{ '/doc/manual/camera.html#camera-tool' | relative_url }}). The drawing tools do nothing on camera and sound layers. If you try to use any tool except Hand on a hidden layer, Pencil2D shows the warning "You are trying to modify a hidden layer!" and does nothing.

The status bar at the bottom of the window shows a one-line hint for the current tool (see [Status bar]({{ '/doc/manual/interface.html#status-bar' | relative_url }})). **Tools → Reset to default** resets the tools' settings. The values it sets are not the same as a fresh installation's: it sets the Pen to width 12, the Eraser to 24, the Brush to 24 with feather 48 and the Polyline to 8. The **Default** columns in this chapter show what a new installation starts with.
<!-- VERIFY: ToolManager::resetAllTools() calls each tool's resetToDefault() without emitting toolPropertyChanged, so the Options panel may keep showing the old values until you switch tools. Also Pencil/Pen reset does not reset every option (e.g. Pencil keeps its Pressure setting). Confirm in the app. -->

![The Tools panel]({{ "/images/manual/toolbox.png" | relative_url }})

*The Tools panel. Hover over a button to see the tool's name and shortcut.*

## Temporary tools and modifier keys {#temporary-tools}

Some keys switch to another tool only while you hold them, then return to your tool:

| Hold | While using | Switches to |
|---|---|---|
| <kbd>Alt</kbd> | Pencil, Eraser, Pen, Brush, Bucket | Eyedropper |
| <kbd>Alt</kbd> | Select | Move |
| <kbd>Ctrl</kbd>+<kbd>Shift</kbd> | Any tool | Eraser |
| <kbd>Space</kbd> | Any tool | Hand |
| Right or middle mouse button (drag) | Any tool | Hand |

On a graphics tablet, turning the pen over to use its eraser end switches to the Eraser tool, with the Eraser's own settings, until you turn the pen back.

> **Note:** Pencil2D 0.7.2 has no "hold <kbd>Shift</kbd> to draw a straight line" feature. In the drawing tools, <kbd>Shift</kbd>+drag changes the width instead (see [Quick Sizing](#quick-sizing)). For straight lines, use the [Polyline](#polyline) tool.

## Pencil {#pencil}

The Pencil draws a soft, slightly textured line in the current color, like a graphite pencil. Use it for rough sketches and construction lines. It is the tool selected when Pencil2D starts.

![Options panel for the Pencil tool]({{ "/images/manual/options-pencil.png" | relative_url }})

*The Options panel for the Pencil on a bitmap layer.*

- **On bitmap layers** the Pencil paints soft dabs of color. The edge softness is fixed; there is no Feather setting.
- **On vector layers** the Pencil draws **invisible lines**: thin guide strokes with no width. They are shown as dotted lines only while **View → Show Invisible Lines** is on, and they are not included when you export. Pencil2D turns **Show Invisible Lines** on for you when you start drawing with the Pencil on a vector layer. Invisible lines are useful as boundaries for fills: draw the outline of a shape with them, then fill it.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Bitmap | Line thickness, 1–200 | 4 |
| **Pressure** | Bitmap | Tablet pressure changes width and opacity | On |
| **Stabilizer** | Both | Smooths your stroke; see [Stabilizer](#stabilizer) | Strong |
| **Fill Contour** | Vector | Fills the shape enclosed by the new stroke with the current color | Off |

**Fill Contour** is not remembered between sessions; it is off each time Pencil2D starts.

**Modifier keys:** <kbd>Shift</kbd>+drag to change the width ([Quick Sizing](#quick-sizing)); <kbd>Alt</kbd> for the Eyedropper; <kbd>Ctrl</kbd>+<kbd>Shift</kbd> for the Eraser.

**Cursor:** a pencil icon, or a crosshair if **Tool Cursors** is off in Preferences; plus the round brush outline if **Canvas Cursor** is on (see [Tool preferences](#tool-preferences)).

> **Tip:** With a mouse, the Pencil draws each dab at half opacity while **Pressure** is on, so lines look light. Turn **Pressure** off for darker, more solid lines.

## Eraser {#eraser}

The Eraser removes what you drew on the current layer.

![Options panel for the Eraser tool]({{ "/images/manual/options-eraser.png" | relative_url }})

*The Options panel for the Eraser on a bitmap layer.*

- **On bitmap layers** it erases pixels along your stroke, with a soft or hard edge depending on **Use Feather**.
- **On vector layers** it deletes the **points** of vector strokes that lie within the eraser's radius (half the width) of your stroke. A stroke that loses points at its end gets shorter, and one that loses points in the middle is split in two; it is not trimmed smoothly at the eraser's edge. Fills attached to the removed points are removed too.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Both | Eraser size, 1–200 | 10 |
| **Feather** | Both | Softness of the edge, 1–99; used only while **Use Feather** is on | 48 |
| **Use Feather** | Both | Erases with a soft, fading edge. Turn off for a hard edge | On |
| **Anti-Aliasing** | Bitmap | Smooths the hard edge; shown only while **Use Feather** is off | — |
| **Pressure** | Both | Tablet pressure changes size and strength | On |
| **Stabilizer** | Both | See [Stabilizer](#stabilizer) | None |

On vector layers **Feather** and **Use Feather** are shown but have no effect.

The Eraser never creates a keyframe. On a frame with no keyframe of its own, it erases from the previous keyframe on the layer, whatever the "When drawing on an empty frame" setting in Preferences says.

**Modifier keys:** <kbd>Shift</kbd>+drag for width and <kbd>Ctrl</kbd>+drag for feather ([Quick Sizing](#quick-sizing)); <kbd>Alt</kbd> for the Eyedropper.

**Cursor:** a crosshair, plus the brush outline (outer circle = width, inner circle = feather) if **Canvas Cursor** is on.

## Pen {#pen}

The Pen draws a solid line with a hard edge. Use it for clean line art and inking over a sketch.

![Options panel for the Pen tool]({{ "/images/manual/options-pen.png" | relative_url }})

*The Options panel for the Pen on a bitmap layer.*

- **On bitmap layers** the stroke is fully opaque in the current color. **Pressure** varies only the width, never the opacity.
- **On vector layers** each stroke becomes a vector curve. With **Pressure** on, the curve keeps the varying width of your stroke; with it off, the curve has one constant width.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Both | Line thickness, 1–200 | 2 |
| **Pressure** | Both | Tablet pressure changes the width | On |
| **Anti-Aliasing** | Bitmap | Smooth edges instead of jagged pixel edges | On |
| **Stabilizer** | Both | See [Stabilizer](#stabilizer) | Strong |

**Modifier keys:** <kbd>Shift</kbd>+drag for width ([Quick Sizing](#quick-sizing)); <kbd>Alt</kbd> for the Eyedropper; <kbd>Ctrl</kbd>+<kbd>Shift</kbd> for the Eraser.

**Cursor:** a pen icon (crosshair if **Tool Cursors** is off), plus the brush outline if **Canvas Cursor** is on.

> **Tip:** For pixel art or flat colors that the Bucket should fill exactly, turn **Anti-Aliasing** off. The line then has no semi-transparent edge pixels.

## Brush {#brush}

The Brush paints soft strokes whose edge fades out. Use it for shading, color and painterly work.

![Options panel for the Brush tool]({{ "/images/manual/options-brush.png" | relative_url }})

*The Options panel for the Brush on a bitmap layer.*

- **On bitmap layers** the Brush always paints with a feathered edge. **Pressure** varies both width and opacity.
- **On vector layers** each stroke becomes a vector curve, as with the Pen. **Feather** is stored with the curve but has no visible effect.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Both | Brush size, 1–200 | 15 |
| **Feather** | Both | Edge softness, 1–99. Higher values give a softer, fainter edge | 15 |
| **Pressure** | Both | Tablet pressure changes width (and opacity on bitmap) | On |
| **Invisible** | Vector | Draws invisible lines (see [Pencil](#pencil)) instead of visible strokes | Off |
| **Stabilizer** | Both | See [Stabilizer](#stabilizer) | Strong |

**Modifier keys:** <kbd>Shift</kbd>+drag for width and <kbd>Ctrl</kbd>+drag for feather ([Quick Sizing](#quick-sizing)); <kbd>Alt</kbd> for the Eyedropper; <kbd>Ctrl</kbd>+<kbd>Shift</kbd> for the Eraser.

**Cursor:** a brush icon (crosshair if **Tool Cursors** is off), plus the brush outline with its feather circle if **Canvas Cursor** is on.

> **Tip:** Like the Pencil, the Brush paints each dab at half opacity while **Pressure** is on and you use a mouse. Turn **Pressure** off for fuller coverage, or lower **Feather**.

## Bucket {#bucket}

The Bucket (its tooltip calls it the Paint Bucket Tool) fills with the current color. It works very differently on the two layer types, and the **Options** panel shows different settings for each.

![Options panel for the Bucket tool]({{ "/images/manual/options-bucket.png" | relative_url }})

*The Options panel for the Bucket on a bitmap layer.*



### Filling on bitmap layers {#bucket-bitmap}

Click inside an area to flood-fill it: the fill spreads from the clicked pixel to all connected pixels of the same color, and stops at lines of a different color. The fill is always painted onto the current layer.

You can also **drag** to fill: after the first fill, keep the button held and move over other areas; each area whose color matches the one you first clicked is filled too. This is quick for filling many small gaps of the same background.

| Option | What it does | Default |
|---|---|---|
| **Reference** | Which layers define the fill boundaries: **Current layer**, or **All layers** (all visible bitmap layers combined) | Current layer |
| **Blend mode** | How the fill combines with pixels already there: **Overlay**, **Replace** or **Behind** (see below) | Overlay |
| **Color tolerance** (checkbox and slider) | How different a pixel's color may be from the clicked color and still be filled, 0–100. Unticked, only exactly matching pixels are filled | Ticked, 50 |
| **Expand fill** (checkbox and slider) | Grows the filled area outward by this many pixels, 0–25, so it tucks under soft line edges | Ticked, 2 |

The **Blend mode** matters mainly when the current color is semi-transparent (tooltip: "Defines how the fill will behave when the new color is not opaque"):

- **Overlay** paints the fill on top of the existing pixels.
- **Replace** replaces the pixels in the filled area with the fill color, including its transparency.
- **Behind** paints the fill behind the existing pixels, so it only shows where they are transparent or semi-transparent.

> **Note:** On a fresh installation, the panel shows **Color tolerance** ticked at 50, but the tool itself starts with tolerance off. If fills seem to ignore the tolerance setting, untick and tick **Color tolerance** again (and nudge the slider) so the tool uses the value shown.
<!-- VERIFY: BucketTool::loadSettings defaults toleranceEnabled=false and tolerance=32, while BucketOptionsWidget shows the checkbox from BucketToleranceEnabled (default true) and the slider from Tolerance (default 50), without pushing either to the Bucket tool. Confirm on a clean profile. -->

> **Tip:** Keep line art on one layer and colors on a layer below it. Select the color layer, set **Reference** to **All layers**, and fill: the lines above define the areas, but the paint goes onto the color layer.

> **Tip:** A fill cannot spread beyond the area covered by the existing drawing and the camera's view (the camera layer below the current layer). Clicking outside both does nothing.

### Filling on vector layers {#bucket-vector}

On a vector layer, the Bucket does not fill the area you click. It acts on the **strokes that are currently selected**:

1. Select the stroke or strokes to fill, for example by dragging a rectangle over them with the [Select](#select) tool.
2. Switch to the Bucket and click on the canvas.

Each selected stroke is filled with the current palette color (the fill follows the shape of the stroke), and the stroke itself takes the current color and the **Stroke thickness** width. Vector colors are linked to the palette; see [Colors on bitmap and vector layers]({{ '/doc/manual/color.html#vector-colors' | relative_url }}).

| Option | What it does | Default |
|---|---|---|
| **Stroke thickness** | Width given to the selected strokes, 1–200 | 4 |

**Modifier keys:** <kbd>Alt</kbd> for the Eyedropper; <kbd>Ctrl</kbd>+<kbd>Shift</kbd> for the Eraser. The Bucket has no Quick Sizing.

**Cursor:** a paint bucket icon, or a crosshair if **Tool Cursors** is off.

## Eyedropper {#eyedropper}

The Eyedropper sets the current color from the drawing. Click on the canvas; the color is picked when you release the button. It has no options.

![Options panel for the Eyedropper tool]({{ "/images/manual/options-eyedropper.png" | relative_url }})

*The Options panel for the Eyedropper on a bitmap layer.*

- **On bitmap layers** it picks the color of the pixel under the pointer on the current layer. Fully transparent pixels are ignored.
- **On vector layers** it picks the palette color of the nearest stroke, or of the fill under the pointer, and selects that color in the palette.

While you move over the canvas, the cursor shows a small swatch of the color it would pick. The Eyedropper only looks at the current layer, not at what you see from other layers.

To pick a color without leaving your drawing tool, hold <kbd>Alt</kbd>, click, and release <kbd>Alt</kbd>. See [Color and Palettes]({{ '/doc/manual/color.html' | relative_url }}) for how picked colors relate to the palette.

## Polyline {#polyline}

The Polyline draws a line through points you click, one segment at a time. Use it for straight lines, perspective lines and geometric shapes.

![Options panel for the Polyline tool]({{ "/images/manual/options-polyline.png" | relative_url }})

*The Options panel for the Polyline on a bitmap layer.*

To draw a polyline:

1. Click where the line starts.
2. Click again for each corner. A preview segment follows the pointer from the last point.
3. Finish the line by **double-clicking**, or by pressing <kbd>Enter</kbd> (the main Return key). Both add the current pointer position as the last point.

Press <kbd>Esc</kbd> to discard the line you are drawing. Switching to another tool also discards an unfinished line. To close a shape, place the last point on the starting point.

- **On bitmap layers** the line is painted in the current color.
- **On vector layers** the line becomes a vector curve of constant width. Its end points join nearby points of existing strokes when they land close to them.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Both | Line thickness, 1–200 | 1.5 |
| **Bézier** | Both | Connects the points with smooth curves instead of straight segments | Off |
| **Anti-Aliasing** | Bitmap | Smooth edges instead of jagged pixel edges | Off |

**Bézier** is not remembered between sessions; it is off each time Pencil2D starts.

**Modifier keys:** <kbd>Shift</kbd>+drag for width ([Quick Sizing](#quick-sizing)); <kbd>Ctrl</kbd>+<kbd>Shift</kbd> for the Eraser. <kbd>Alt</kbd> does not switch to the Eyedropper in this tool.

**Cursor:** a crosshair, plus the brush outline if **Canvas Cursor** is on.

## Smudge {#smudge}

The Smudge tool (tooltip: "Edit polyline/curves, Liquify bitmap pixels") does two unrelated jobs depending on the layer.

![Options panel for the Smudge tool]({{ "/images/manual/options-smudge.png" | relative_url }})

*The Options panel for the Smudge on a bitmap layer.*

**On bitmap layers** it pushes existing pixels around, like dragging a finger through wet paint. Drag across the drawing to smear it in the direction of your stroke. Hold <kbd>Alt</kbd> while dragging to switch to the alternative mode, which the tooltip calls "Smooth"; the cursor changes to show it. In 0.7.2 the alternative mode displaces pixels (a liquify effect) rather than blurring them.

**On vector layers** it reshapes strokes. Move the pointer near a stroke: the points within reach are highlighted. Press near a stroke and drag to move those points; when you release, the edited stroke is smoothed. Hold <kbd>Shift</kbd> when you press to add points to the ones already selected instead of starting over.

| Option | Layers | What it does | Default |
|---|---|---|---|
| **Width** | Bitmap | Size of the smudge area, 1–200 | 24 |
| **Feather** | Bitmap | Softness of the smudge edge, 1–99 | 48 |

On vector layers the Smudge tool has no options.

> **Warning:** Known issues in 0.7.x: on bitmap layers the default mode can leave a white background along the smudged stroke, and the <kbd>Alt</kbd> mode keeps smudging instead of blurring. Try it on a copy of your work first.

The Smudge tool never creates a keyframe. On a frame without its own keyframe, it changes the previous keyframe.

**Modifier keys:** <kbd>Shift</kbd>+drag for width and <kbd>Ctrl</kbd>+drag for feather on bitmap layers ([Quick Sizing](#quick-sizing)); <kbd>Alt</kbd> for the alternative mode (not the Eyedropper).

**Cursor:** a smudge icon, which changes while <kbd>Alt</kbd> is held, plus the brush outline if **Canvas Cursor** is on.

## Select {#select}

The Select tool makes a rectangular selection. Drag on the canvas to draw a rectangle; drag its corners to resize it. On a vector layer, strokes inside the rectangle are selected. Hold <kbd>Alt</kbd> to switch to the Move tool temporarily and move what is inside. <kbd>Backspace</kbd> clears the selected content.

![Options panel for the Select tool]({{ "/images/manual/options-select.png" | relative_url }})

*The Options panel for the Select on a bitmap layer.*

| Option | What it does | Default |
|---|---|---|
| **Show Size and Diff.** | Shows the selection's size, and how far its center has moved, next to the selection | Off |

The Move tool has the same option. For everything you can do with a selection, see [Selecting and Transforming]({{ '/doc/manual/selection.html#making-a-selection' | relative_url }}).

## Move {#move}

The Move tool moves, scales and rotates the current selection. Drag inside the selection to move it and drag a corner to scale it. Hold <kbd>Ctrl</kbd> when you press inside it to rotate. Hold <kbd>Shift</kbd> to keep proportions while scaling or to move along one axis; while rotating, <kbd>Shift</kbd> snaps the angle to the **Rotation snap increment** set in Preferences.

![Options panel for the Move tool]({{ "/images/manual/options-move.png" | relative_url }})

*The Options panel for the Move on a bitmap layer.*

When a perspective overlay is on and nothing is selected, the Move tool drags the vanishing points (see [Perspective]({{ '/doc/manual/canvas.html#perspective' | relative_url }})). On a camera layer, this toolbox button selects the [Camera tool]({{ '/doc/manual/camera.html#camera-tool' | relative_url }}).

The only option is **Show Size and Diff.**, as for [Select](#select). For details see [Transforming]({{ '/doc/manual/selection.html#transforming' | relative_url }}).

## Hand {#hand}

The Hand tool changes your view of the canvas; it never changes the drawing.

![Options panel for the Hand tool]({{ "/images/manual/options-hand.png" | relative_url }})

*The Options panel for the Hand on a bitmap layer.*

| Action | Result |
|---|---|
| Drag | Pan the view |
| <kbd>Ctrl</kbd>+drag | Zoom: drag down to zoom in, up to zoom out |
| <kbd>Alt</kbd>+drag | Rotate the view around the center of the canvas area |
| Double-click with the right mouse button | Reset the view |

The zoom direction can be reversed with **Invert Zoom Direction** in Preferences. You rarely need to select the Hand tool itself: hold <kbd>Space</kbd>, or drag with the right or middle mouse button, while using any tool. It has no options. The cursor is an open hand, which closes while you drag.

For other ways to move the view, see [Canvas and View]({{ '/doc/manual/canvas.html#pan' | relative_url }}).

## Common Options {#common-options}

These settings appear for several tools. Each tool remembers its own values: changing the width of the Pen does not change the width of the Brush. Most settings are kept between sessions.

Which option each tool shows:

| Option | Pencil | Eraser | Pen | Brush | Polyline | Smudge |
|---|---|---|---|---|---|---|
| **Width** | Bitmap | Both | Both | Both | Both | Bitmap |
| **Feather** | — | Both | — | Both | — | Bitmap |
| **Use Feather** | — | Both | — | — | — | — |
| **Pressure** | Bitmap | Both | Both | Both | — | — |
| **Anti-Aliasing** | — | Bitmap | Bitmap | — | Bitmap | — |
| **Stabilizer** | Both | Both | Both | Both | — | — |
| **Invisible** | — | — | — | Vector | — | — |
| **Fill Contour** | Vector | — | — | — | — | — |
| **Bézier** | — | — | — | — | Both | — |

**Width** sets the size of the tool in canvas pixels. You can drag the slider, type in the number box beside it, or use [Quick Sizing](#quick-sizing). The slider covers 1–200 and grows faster at the high end so small sizes are easy to set; the number box also accepts values down to 0.5. The Bucket's **Stroke thickness** on vector layers works the same way.

**Feather** sets how soft the edge of the stroke is. Low values give a firm edge; high values fade the stroke out towards its edge and make it fainter overall. The slider covers 1–99 (the number box accepts down to 0.1). The Eraser only feathers while **Use Feather** is ticked; with it off, you get a hard edge and **Anti-Aliasing** becomes available instead.

**Pressure** makes the stroke respond to how hard you press with a graphics tablet stylus. For Pencil, Eraser and Brush on bitmap layers, pressure changes both width and opacity; for the Pen, only width. With a mouse, pressure is treated as constant, so this setting mostly matters on a tablet.

**Anti-Aliasing** smooths the edges of hard-edged strokes by adding semi-transparent pixels along them. Turn it off for crisp pixel edges, for example for pixel art or for fills that must meet the line exactly. It only applies to bitmap layers. This is separate from the **Antialiasing** preference, which affects how the canvas is displayed.

**Invisible** (Brush, vector layers) draws strokes that are not rendered or exported, but still exist as lines that fills can follow. **View → Show Invisible Lines** shows them as dotted lines while you work.

**Fill Contour** (Pencil, vector layers) fills the area enclosed by each new stroke with the current color as soon as you finish it.

**Bézier** (Polyline) turns the straight segments between clicked points into smooth curves.

> **Note:** The Options panel also contains "Merge" and "Alpha" checkboxes, but no tool shows them in 0.7.2.

### Stabilizer {#stabilizer}

The **Stabilizer** smooths the path of your stroke to remove the jitter of a shaky hand or a mouse. It is available for the Pencil, Eraser, Pen and Brush.

| Level | What it does |
|---|---|
| **None** | The stroke follows the pointer exactly. |
| **Simple** | Each new point is placed halfway between the pointer and the previous point, and the segments are joined with smooth curves. Light smoothing with little delay. |
| **Strong** | The stroke follows the average of the last few pointer positions, so it trails slightly behind the pointer and catches up when you lift. Strongest smoothing. |

The defaults are **Strong** for Pencil, Pen and Brush, and **None** for the Eraser.

> **Tip:** If your lines look like they "cut corners" or lag behind fast movements, lower the Stabilizer to **Simple** or **None**. For slow, careful inking, **Strong** gives the smoothest lines.

## Quick Sizing {#quick-sizing}

Quick Sizing lets you change a tool's size directly on the canvas, so you can see the result against your drawing:

- Hold <kbd>Shift</kbd>, press on the canvas and drag to change **Width**. A circle shows the new size; its edge follows the pointer.
- Hold <kbd>Ctrl</kbd>, press on the canvas and drag to change **Feather**. The inner circle shows the feather; drag towards the center to increase it and outwards to reduce it.

Release the button to keep the new value; the Options panel updates as you drag. No stroke is drawn while you do this.

| Tool | <kbd>Shift</kbd>+drag: Width | <kbd>Ctrl</kbd>+drag: Feather |
|---|---|---|
| Pencil, Pen, Polyline | Yes | — |
| Eraser, Brush, Smudge | Yes | Yes |

The Bucket, Eyedropper, Select, Move and Hand tools do not use Quick Sizing. Quick Sizing is on by default; turn it off with **Use Quick Sizing** in Preferences if you want <kbd>Shift</kbd> and <kbd>Ctrl</kbd> to do nothing special while drawing.

## Tool preferences {#tool-preferences}

Several settings in **Edit → Preferences** (under the **Pencil2D** menu on macOS) change how tools behave. They are described in full in [Preferences]({{ '/doc/manual/preferences.html#tools' | relative_url }}):

| Setting | Where | Effect | Default |
|---|---|---|---|
| **Use Quick Sizing** | Tools → Brush Tools | Turns [Quick Sizing](#quick-sizing) on or off | On |
| **Rotation snap increment** | Tools → Move Tool | Angle step when rotating a selection with <kbd>Shift</kbd> | 15 degrees |
| **Invert Zoom Direction** | Tools → Hand Tool | Zoom in by dragging up instead of down | Off |
| **Tool Cursors** | General → Appearance | Shows tool icons as cursors instead of a crosshair | On |
| **Canvas Cursor** | General → Appearance | Shows the brush outline (width and feather) on the canvas | On |
| **Vector curve smoothing** | General → Editing | How much vector strokes are smoothed when you finish them, 1–100 | 20 |
| **When drawing on an empty frame** | Timeline → Drawing | Whether drawing on a frame without a keyframe creates a new keyframe, duplicates the previous one, or draws on the previous one | Keep drawing on the previous key-frame |

The empty-frame setting applies to the Pencil, Pen, Brush, Polyline and Bucket. The Eraser and Smudge tools always work on the previous keyframe, even though the Preferences label also lists the Eraser.

{% include series-nav.html series=site.data.manual %}
