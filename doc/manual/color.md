---
layout: page
title: Color and Palettes
tagline: Choosing colors, managing palettes, and how colors behave on bitmap and vector layers
comments: false
---

This chapter covers the three color panels (**Color Box**, **Color Inspector** and **Color Palette**), palette files, and the one important difference between bitmap and vector layers: on vector layers, drawings stay linked to palette colors. Read it when you start working with color, or when a vector drawing changes color and you don't know why.

Shortcuts are written in Windows/Linux form. On macOS, use <kbd>Cmd</kbd> in place of <kbd>Ctrl</kbd> and <kbd>Option</kbd> in place of <kbd>Alt</kbd>.

{% include toc.html %}

## The current color {#current-color}

Pencil2D has a single **current color**. Every drawing tool paints with it, and the three color panels all show it and can change it:

| Panel | What you use it for | Show/hide |
|---|---|---|
| **Color Box** | Picking a color by eye on a color wheel | <kbd>Ctrl</kbd>+<kbd>3</kbd> |
| **Color Palette** | Keeping a set of named colors (swatches) for the project | <kbd>Ctrl</kbd>+<kbd>4</kbd> |
| **Color Inspector** | Entering exact RGB or HSV numbers, and setting transparency (alpha) | <kbd>Ctrl</kbd>+<kbd>7</kbd> |

You can also show or hide these panels from the **Windows** menu. When you change the color in one panel, the others update to match. For docking, floating and resetting panels, see [The Interface]({{ '/doc/manual/interface.html#color-panels' | relative_url }}).

> **Note:** Pencil2D 0.7.2 has no pop-up palette at the cursor. The tooltip on the Color Box still mentions a <kbd>C</kbd> key, but that feature no longer exists. Keep the color panels docked where you can reach them, or use the [Eyedropper](#eyedropper).

## Color Wheel {#color-wheel}

The **Color Box** panel holds the color wheel. It has two parts:

- **The hue ring** (the outer rainbow circle) sets the hue, which is the basic color: red, yellow, green, blue and so on. A small circle on the ring shows the current hue.
- **The saturation/value square** (inside the ring) shows every shade of that hue. Moving left to right increases saturation, from white/grey on the left to full color on the right. Moving top to bottom lowers the value (brightness), down to black at the bottom. A small circle marks the current color.

To pick a color:

1. Click or drag on the ring to choose a hue. The square updates to show that hue.
2. Click or drag inside the square to choose how light, dark or saturated the color is. While you drag, the picker stays inside the square even if your pointer leaves it.

The wheel does not change transparency. If the current color is partly transparent, it stays that way while you use the wheel. To change alpha, use the [Color Inspector](#color-inspector).

If you pick a grey, white or black (a color with no hue), the ring keeps the hue you had before, so you can drag back into color without starting over.

![The Color Box panel]({{ "/images/manual/colorbox.png" | relative_url }})

## Color Inspector {#color-inspector}

The **Color Inspector** lets you type or slide exact values. It has two tabs:

| Tab | Channels | Ranges |
|---|---|---|
| **HSV** | **H** (hue), **S** (saturation), **V** (value), **A** (alpha) | H 0–359°, S/V/A 0–100% |
| **RGB** | **R** (red), **G** (green), **B** (blue), **A** (alpha) | 0–255 each |

Each channel has a colored slider and a number box. Click or drag on a slider to set the value, or type a number in the box. Each slider's gradient shows what the color would look like at every value of that channel, given the other channels.

The **A** (alpha) channel sets transparency: 100% (HSV tab) or 255 (RGB tab) is fully opaque, 0 is invisible. Strokes drawn with a partly transparent color are partly see-through.

The large bar below the sliders previews the current color over a checkerboard, so you can see its transparency.

Pencil2D remembers which tab you used last. The first time you open it, the **HSV** tab is shown.

> **Note:** The Color Inspector has no field for hex color codes (such as `#FF8000`). To use a color from a hex code, convert it to RGB numbers and enter them on the **RGB** tab.

![The Color Inspector panel, HSV tab]({{ "/images/manual/inspector.png" | relative_url }})

## Color Palette {#palette}

The **Color Palette** panel holds the project's palette: a list of colors, each with a name. The palette is saved inside your project file, so each project has its own. A new project starts with the [default palette](#default-palette).

Along the top of the panel are these buttons, from left to right:

| Button | Tooltip | What it does |
|---|---|---|
| Plus | **Add Color** | Adds the current color to the end of the palette and selects it |
| Minus | **Remove Color** | Removes the selected swatch or swatches |
| Color dialog | *(none)* | Opens a color picker dialog; the color you choose is added as a new swatch and selected |
| More options | *(none)* | Opens the view menu: **List Mode**, **Grid Mode** and the swatch sizes |

![The Color Palette panel in list mode]({{ "/images/manual/palette.png" | relative_url }})

### Picking a swatch {#picking-a-swatch}

Click a swatch to make it the current color. The Color Box and Color Inspector update to match. What happens next depends on the layer type; see [Colors on bitmap and vector layers](#vector-colors).

To select several swatches at once, for example to remove them together, hold <kbd>Ctrl</kbd> or <kbd>Shift</kbd> while clicking. Clicking with <kbd>Ctrl</kbd> or <kbd>Shift</kbd> held selects swatches but does not change the current color.

### Adding colors {#adding-colors}

There are three ways to add a color:

- Choose a color in the Color Box or Color Inspector, then click **Add Color** (the plus button). The new swatch is added at the end of the palette and becomes the selected swatch.
- Right-click anywhere in the palette and choose **Add**. The current color is added at the end of the palette and its name opens for editing so you can type a name straight away. The new swatch is not selected.
- Click the color dialog button, choose a color (including alpha) in the dialog, and confirm. The color is added at the end and selected.

New colors get an automatic descriptive name based on the color. You can [rename](#renaming-colors) them afterwards.

### Replacing a color {#replacing-colors}

To change a swatch to a different color:

1. Click the swatch you want to change.
2. Adjust the color in the Color Box or Color Inspector. This changes the current color only; the swatch keeps its old color for now.
3. Right-click the swatch and choose **Replace**.

The swatch takes the current color and keeps its name. On vector layers, every stroke and fill that uses this swatch changes to the new color, on every frame and every vector layer. See [Colors on bitmap and vector layers](#vector-colors).

### Removing colors {#removing-colors}

To remove colors, select one or more swatches and click **Remove Color** (the minus button), or right-click and choose **Remove**.

- If a color is used by any vector stroke or fill, Pencil2D warns: *"The color(s) you are about to delete are currently being used by one or multiple strokes."* Choose **Delete** to go ahead or **Cancel** to keep it. When you remove several selected swatches, this warning is shown once for all of them.
- Vector strokes and fills that used a removed color take the color of the swatch just before it in the palette (or of the new first swatch, if you removed the first one).
- The palette must keep at least one swatch. If you try to remove the last one, Pencil2D shows **Palette Restriction**: *"The palette requires at least one swatch to remain functional"*.

Removing a color never changes bitmap drawings.

### Renaming colors {#renaming-colors}

To rename a color, double-click its swatch.

- In **List Mode**, the name becomes editable in place. Type the new name and press <kbd>Enter</kbd>.
- In **Grid Mode**, a **Color name** dialog opens. Type the new name and click **OK**.

In Grid Mode, hover over a swatch to see its name as a tooltip.

### Reordering swatches {#reordering-swatches}

In **List Mode**, drag a swatch up or down to move it. Vector drawings keep their colors when you reorder: Pencil2D updates the strokes to follow the swatch to its new position.

Swatches cannot be dragged in **Grid Mode**. Switch to List Mode to reorder them.

### List and grid view, swatch size {#palette-view}

Click the more options button to change how the palette looks. Pencil2D remembers these choices.

| Option | What it does |
|---|---|
| **List Mode** | One swatch per row, with its name beside it. This is the default. |
| **Grid Mode** | Swatches only, packed in a grid. Names appear as tooltips. |
| **Small swatch** | Small swatches (19 px). The tooltip says 16×16 px, but 19 px is the actual size. |
| **Medium Swatch** | 26 × 26 px swatches |
| **Large Swatch** | 36 × 36 px swatches |
| **Fit Swatch** | Resizes swatches (19–36 px) so the whole palette fits in the panel, and keeps doing so when you resize the panel or add and remove colors |

## Palette files {#palette-files}

### The default palette {#default-palette}

Every new project starts with the same 24-color palette: black, white, four greys, red, orange, yellow, green, cyan and blue (each with a dark version), and six pale orange-yellow tones useful for skin. Pencil2D also uses this palette when it opens a project that has no palette data.

There is no command to reset an existing project to the default palette. To reuse a palette in other projects, [export it](#import-export-palettes) and then import it into each project.

### Importing and exporting palettes {#import-export-palettes}

| Menu item | What it does |
|---|---|
| **File → Import → Replace Palette...** | Discards the current palette and loads the colors from a palette file |
| **File → Import → Append to Palette...** | Adds the colors from a palette file to the end of the current palette |
| **File → Export → Palette** | Saves the current palette to a file |

After you replace or append a palette, the first swatch becomes the current color.

> **Warning:** If any vector strokes use the current palette, **Replace Palette...** first warns: *"Opening a palette will replace the old palette. Color(s) in strokes will be altered by this action!"* Vector strokes and fills take the color at the same position in the new palette. Click **Open Palette** to continue or **Cancel** to stop. Use **Append to Palette...** if you want to keep your existing colors.

### Supported palette formats {#palette-formats}

| Format | Extension | Notes |
|---|---|---|
| Pencil2D Palette | `.xml` | Keeps color names and alpha. This is the default when exporting. |
| GIMP Palette | `.gpl` | Also used by GIMP, Krita, Inkscape and other programs. Stores names and RGB only: alpha is lost on export, and imported colors are fully opaque. |

When exporting, Pencil2D picks the format from the file extension you type: `.gpl` saves a GIMP palette, anything else saves a Pencil2D palette.

When importing a GIMP palette, colors named "Untitled" or with no name get an automatic name.

## Picking colors from the drawing {#eyedropper}

The [Eyedropper]({{ '/doc/manual/tools.html#eyedropper' | relative_url }}) tool (<kbd>I</kbd>) picks a color from the canvas:

- On a **bitmap layer**, it picks the exact pixel color you click on (including its transparency) and makes it the current color. Clicking a fully transparent pixel does nothing. The palette does not change.
- On a **vector layer**, it finds the palette swatch used by the stroke or fill you click on and selects that swatch.

With most drawing tools, you can hold <kbd>Alt</kbd> to switch to the Eyedropper temporarily. Release <kbd>Alt</kbd> to return to your tool.

## Colors on bitmap and vector layers {#vector-colors}

Colors work differently on the two drawable layer types (see [Layer types]({{ '/doc/manual/layers.html#layer-types' | relative_url }})).

**On bitmap layers, color is copied.** Each stroke is painted with the current color, whatever panel you set it with. Once painted, the pixels keep that color. Changing, replacing or removing a palette swatch has no effect on existing bitmap drawings.

**On vector layers, color is linked.** Each vector stroke and fill stores *which palette swatch* it uses, not a copy of the color. This has three consequences:

- **You always draw with a palette swatch.** On a vector layer, tools use the selected swatch in the Color Palette. Changing the color in the Color Box or Color Inspector alone does not change what you draw. To draw with a new color, add it to the palette with **Add Color** (it is selected automatically), or [replace](#replacing-colors) an existing swatch.
- **Replacing a swatch recolors the drawing.** When you use **Replace** on a swatch, every vector stroke and fill that uses it changes color, on every frame of every vector layer. This makes recoloring a character across a whole animation a single step.
- **Removing or replacing the whole palette affects vector drawings.** See [Removing colors](#removing-colors) and [Importing and exporting palettes](#import-export-palettes).

When you switch to a vector layer, the current color changes to the selected palette swatch.

> **Tip:** Plan a vector palette before you animate: one swatch per part of your character (skin, hair, shirt, outline). You can then adjust any part's color later with **Replace**, without redrawing.

When you [import layers from another project]({{ '/doc/manual/layers.html#import-layers' | relative_url }}), the colors used by imported vector layers are added to the end of your palette, so they keep their original look.

## Change line color on bitmap layers {#change-line-color}

**Layer → Change line color** recolors an existing bitmap drawing with the current color. It is only available when the current layer is a bitmap layer.

| Menu item | What it does |
|---|---|
| **Current keyframe** | Recolors the keyframe at the current frame. Does nothing if there is no keyframe exactly at the current frame. |
| **All keyframes on layer** | Recolors every keyframe on the current layer |

Every pixel that is not fully transparent gets the current color, lines and fills alike. Each pixel keeps its own transparency, so soft edges and anti-aliasing are preserved. The alpha of the current color is ignored.

This is useful for turning rough sketches into a light color before drawing clean lines over them, or for recoloring line art that sits on its own layer.

> **Warning:** Because it recolors everything on the keyframe, use it on a layer that contains only line art. Otherwise your colored fills change too. It may not be possible to undo this action, so save first. <!-- VERIFY: changeKeyframeLineColor/changeallKeyframeLineColor in actioncommands.cpp make no mEditor->backup() call, so Undo likely does not revert it; confirm in the app -->

{% include series-nav.html series=site.data.manual %}
