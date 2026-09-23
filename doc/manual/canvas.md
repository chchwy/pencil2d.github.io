---
layout: page
title: Canvas and View
tagline: Zoom, pan, rotate and flip the view, and use grids, guides and perspective overlays
comments: false
---

This chapter covers how you look at your drawing: zooming, panning, rotating and mirroring the
view, the composition and perspective overlays you can lay over the canvas, and the display modes
that control which layers and lines you see. None of these change your artwork or your exported
animation; they only change what you see while you work.

> **Note:** Shortcuts are written for Windows and Linux. On macOS, press <kbd>Cmd</kbd> wherever
> this page says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.
> Preferences are under **Edit → Preferences** on Windows and Linux, and under the **Pencil2D**
> application menu on macOS. All shortcuts can be changed; see
> [Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }}).

{% include toc.html %}

## The View and Overlay toolbars {#view-toolbars}

Pencil2D 0.7 replaced the old Display Options window with two toolbars. They sit above the canvas
by default. To show or hide them, use **Windows → Toolbars → View Toolbar** and
**Windows → Toolbars → Overlay Toolbar**.

| Toolbar | Buttons, left to right |
|---|---|
| **View Toolbar** | **Zoom In**, **Zoom Out**, **Reset** (view), **Horizontal Flip**, **Vertical Flip**, **Show Invisible Lines**, **Show Outlines Only** |
| **Overlay Toolbar** | **Grid**, **Center**, **Thirds**, **Golden Ratio**, **Safe Areas**, **One Point Perspective**, **Two Point Perspective**, **Three Point Perspective**, **Perspective Lines Angle** (drop-down) |

![The Overlay toolbar]({{ "/images/pencil2d-0.7.0-perspective-grid-types.png" | relative_url }})

Every button is also in the **View** menu, so you can hide the toolbars and still reach
everything. The toggle buttons stay pressed while their option is on.

![The View Toolbar]({{ "/images/manual/view-toolbar.png" | relative_url }})

## Zoom {#zoom}

Pencil2D zooms from 1% to 10000%. The current zoom level is shown at the right end of the status
bar.

**With the mouse or trackpad:** scroll the mouse wheel over the canvas to zoom in and out around the
pointer. On a trackpad, scrolling up and down does the same. You do not need to hold any key. The
scroll wheel never pans the canvas. To reverse the direction, turn on **Invert Scroll Direction**
in **Preferences → General → Scroll Wheel Zoom**.

**With the Hand tool:** hold <kbd>Ctrl</kbd> and drag up or down. By default, dragging down zooms
in. To make dragging up zoom in instead, turn on **Invert Zoom Direction** in
**Preferences → Tools → Hand Tool**. See [Pan](#pan) for more about the Hand tool.

**With the menu and keyboard:**

| Command | Where | Default shortcut |
|---|---|---|
| **Zoom In** | **View → Zoom In**, View Toolbar | <kbd>Ctrl</kbd>+<kbd>Up</kbd> |
| **Zoom Out** | **View → Zoom Out**, View Toolbar | <kbd>Ctrl</kbd>+<kbd>Down</kbd> |
| 400% | **View → Zoom → 400%** | <kbd>4</kbd> |
| 300% | **View → Zoom → 300%** | <kbd>3</kbd> |
| 200% | **View → Zoom → 200%** | <kbd>2</kbd> |
| 100% | **View → Zoom → 100%** | <kbd>1</kbd> |
| 50% | **View → Zoom → 50%** | <kbd>Shift</kbd>+<kbd>2</kbd> |
| 33% | **View → Zoom → 33%** | <kbd>Shift</kbd>+<kbd>3</kbd> |
| 25% | **View → Zoom → 25%** | <kbd>Shift</kbd>+<kbd>4</kbd> |

**Zoom In** and **Zoom Out** step through fixed levels (1, 2, 4, 6, 8, 12, 16, 25, 33, 50, 75,
100, 150, 200, 300, 400, 500, 600, 800, 1600, 3200, 4800, 6400 and 9600%). Menu and keyboard
zooming keeps the middle of the canvas area in place.

### The status bar zoom control {#zoom-control}

The right end of the status bar has two zoom controls:

- **Zoom box:** a drop-down with preset levels (10000, 6400, 1600, 800, 400, 200, 100, 75, 50,
  33, 25, 12 and 1%). You can also click into it, type any value, and press <kbd>Enter</kbd>.
- **Zoom slider:** drag it for a quick zoom. It covers the whole range from 1% to 10000%, with
  100% in the middle.

![The status bar]({{ "/images/manual/statusbar.png" | relative_url }})

*The status bar. The tool help is on the left; the zoom controls are on the right.*

If you can't see the status bar, turn on **Windows → Status Bar**. See also
[The Interface]({{ '/doc/manual/interface.html#status-bar' | relative_url }}).

## Pan {#pan}

Panning slides the canvas around inside the window. There are several ways to do it:

- **Hand tool** (<kbd>H</kbd>): select it in the toolbox and drag the canvas.
- **Space bar:** hold <kbd>Space</kbd> and drag with the left mouse button or your pen. Pencil2D
  switches to the Hand tool while you hold the key and goes back to your tool when you release it.
- **Middle or right mouse button:** drag with either button pressed. This also switches to the Hand
  tool only for as long as you hold the button.

The Hand tool does more than pan:

| Action with the Hand tool | What it does |
|---|---|
| Drag | Pans the view |
| <kbd>Ctrl</kbd>+drag | Zooms around the point where you started dragging |
| <kbd>Alt</kbd>+drag | Rotates the view around the middle of the canvas area |
| Double-click with the right mouse button | Resets the view (same as **View → Reset**) |

**View → Center** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>H</kbd>) pans back to the middle of the
canvas, which is where the camera frame sits in a new project. It keeps the current zoom and
rotation.

> **Warning:** On Windows, panning by dragging with the middle or right button of a tablet pen can
> make Pencil2D misbehave ([issue #1813](https://github.com/pencil2d/pencil/issues/1813)). Hold
> <kbd>Space</kbd> and drag with the pen tip instead. If it has already happened, click the canvas
> once with a mouse to get back to normal.

## Rotate the view {#rotate}

Rotating the view turns the canvas like you would turn a sheet of paper on your desk, so you can
draw curves at a comfortable angle. Your drawing and the camera are not rotated.

| Command | Where | Default shortcut |
|---|---|---|
| **Rotate Clockwise** | **View → Rotate Clockwise** | <kbd>R</kbd> |
| **Rotate Anticlockwise** | **View → Rotate Anticlockwise** | <kbd>Z</kbd> |
| **Reset Rotation** | **View → Reset Rotation** | <kbd>Alt</kbd>+<kbd>H</kbd> |

Each press of **Rotate Clockwise** or **Rotate Anticlockwise** turns the view by 15 degrees. For
free rotation, hold <kbd>Alt</kbd> and drag with the Hand tool. If the view is also flipped,
Pencil2D swaps the direction for you, so the canvas always turns the way the command says.

The status bar shows no rotation angle. Use **Reset Rotation** to get back to 0 degrees.

## Flip the view {#flip}

Flipping mirrors what you see without changing the drawing. Artists use it to find mistakes in
proportion and symmetry: a drawing seen in a mirror often shows problems that your eye has got
used to.

| Command | Where | Default shortcut |
|---|---|---|
| **Horizontal Flip** | **View → Horizontal Flip**, View Toolbar | <kbd>Shift</kbd>+<kbd>H</kbd> |
| **Vertical Flip** | **View → Vertical Flip**, View Toolbar | <kbd>Shift</kbd>+<kbd>V</kbd> |

Both are toggles: use the same command again to turn the flip off. You can keep drawing while the
view is flipped, and exported images and movies are not flipped.

To mirror the artwork itself, select it and use **Edit → Selection → Flip X** or **Flip Y**; see
[Selecting and Transforming]({{ '/doc/manual/selection.html#flip-selection' | relative_url }}).

## Reset the view {#reset-view}

**View → Reset** (<kbd>Ctrl</kbd>+<kbd>H</kbd>, also on the View Toolbar) sets the zoom to 100%,
the rotation to 0 degrees, and pans back to the middle of the canvas.

> **Note:** **Reset** does not turn off **Horizontal Flip** or **Vertical Flip**. Check the flip
> buttons if your drawing still looks mirrored after a reset.

## Overlays {#overlays}

Overlays are guide lines drawn over the canvas to help you compose shots and draw in perspective.
They are never part of your drawing and never appear in exports. They are hidden while the
animation plays.

Turn overlays on and off in **View → Overlays** or with the Overlay Toolbar. You can combine as
many as you like. Pencil2D remembers which overlays are on between sessions; this is a program
setting, not part of the project file.

| Overlay | What it shows | Default shortcut |
|---|---|---|
| **Grid** | A grid of light gray lines over the whole canvas | <kbd>G</kbd> |
| **Center** | A small dashed cross at the center of the camera frame | none |
| **Thirds** | Dashed lines that divide the camera frame into thirds (the rule of thirds) | none |
| **Golden Ratio** | Dashed lines at the golden ratio points of the camera frame (38.2% and 61.8%) | none |
| **Safe Areas** | The action safe and title safe rectangles inside the camera frame | none |
| **One Point Perspective** | Lines radiating from one vanishing point | none |
| **Two Point Perspective** | Lines radiating from two vanishing points on a horizon line | none |
| **Three Point Perspective** | Two-point lines plus lines from a third vanishing point | none |

**Center**, **Thirds**, **Golden Ratio** and **Safe Areas** are measured from the camera frame, so
they follow the camera as it moves, rotates and zooms. The **Grid** is fixed to the canvas instead.

Overlays are drawn relative to the nearest camera layer at or below the current layer in the layer
list. If the current layer is below every camera layer, no overlays are drawn at all, not even the
grid. With the usual setup, where the camera layer is at the bottom, this doesn't happen.

<!-- SCREENSHOT: Canvas with the Thirds, Center and Safe Areas overlays switched on together, showing the safe area labels -->

### Grid {#grid}

The grid starts at the canvas origin and covers the whole visible canvas. Set the size of the grid
cells in **Preferences → General → Grid**:

| Option | What it does | Default |
|---|---|---|
| **Grid Width** | Horizontal spacing of the grid lines, in canvas pixels (1–9999) | 100 |
| **Grid Height** | Vertical spacing of the grid lines, in canvas pixels (1–9999) | 100 |
| **Enable Grid** | Same as **View → Overlays → Grid** | off |

### Safe areas {#safe-areas}

TV and video work uses two safe areas: keep important action inside the **action safe** area and
all text inside the smaller **title safe** area, so that nothing is cut off at the edges of a
screen. Set them up in **Preferences → General → Overlays**:

| Option | What it does | Default |
|---|---|---|
| **Enable Action Safe area (%)** | Draws the action safe rectangle; the number (1–25) is how much of the frame lies outside it | on, 5 |
| **Enable Title Safe area (%)** | Draws the title safe rectangle; the number (1–25) is how much of the frame lies outside it | on, 10 |
| **Show Safe area labels** | Writes "Safe Action area" and "Safe Title area" with their percentages next to the rectangles | on |

For example, a 5% action safe area leaves a margin of 2.5% of the frame on each side.

> **Note:** If you turn off both safe areas in Preferences, the **Safe Areas** button is disabled.
> Pencil2D only checks this when it starts, so after turning a safe area back on, restart
> Pencil2D to use the button again.

### Perspective overlays {#perspective}

Perspective overlays draw fans of straight lines out of vanishing points, like the construction
lines you would rule by hand. Use them to lay out backgrounds, buildings and props.

| One point | Two point | Three point |
|---|---|---|
| ![One point perspective overlay]({{ "/images/pencil2d-0.7.0-one-point-perspective.png" | relative_url }}) | ![Two point perspective overlay]({{ "/images/pencil2d-0.7.0-two-point-perspective.png" | relative_url }}) | ![Three point perspective overlay]({{ "/images/pencil2d-0.7.0-three-point-perspective.png" | relative_url }}) |

- **One Point Perspective** draws lines in every direction from a single vanishing point, which
  starts at the center of the camera frame.
- **Two Point Perspective** draws lines from a left and a right vanishing point. They start on the
  horizontal center line of the camera frame, 300 pixels either side of the center, and always
  stay on the same horizon line.
- **Three Point Perspective** adds a third vanishing point, which starts 200 pixels below the
  center of the camera frame. Its lines point towards the horizon, so they flip direction when you
  drag the point above the horizon.

The lines extend across the whole visible canvas. The vanishing points are placed relative to the
camera, so they move and rotate with it.

**Moving vanishing points:** select the **Move** tool (<kbd>M</kbd>) on any layer except a camera
layer, and make sure nothing is selected. A round handle appears on each vanishing point. Drag a
handle to move the point. When you drag the left or right point of a two- or three-point overlay
up or down, the other one follows, so the horizon stays level.

<video src="{{ '/images/pencil2d-0.7.0-perspective-handle.mp4' | relative_url }}" controls muted loop playsinline style="max-width:100%"></video>

> **Note:** Vanishing point positions are not saved. They go back to their starting positions each
> time you start Pencil2D.

### Perspective Lines Angle {#perspective-angle}

**View → Overlays → Perspective Lines Angle** sets the angle between neighbouring perspective
lines: **2°**, **3°**, **5°**, **7.5°**, **10°**, **15°** (the default), **20°** or **30°**.
Smaller angles give more, denser lines. The same menu is the drop-down button at the right end of
the Overlay Toolbar. The setting applies to all three perspective overlays.

## Layer visibility {#layer-visibility}

Layer visibility modes control how much of the *other* layers you see while you work on the
current one. They don't change which layers are exported; they only change the display. (To
hide a single layer, use its visibility switch in the timeline; see
[Layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}).)

| Mode | Menu | Default shortcut | What you see |
|---|---|---|---|
| **Current layer only** | **View → Layer Visibility → Current layer only** | <kbd>Alt</kbd>+<kbd>1</kbd> | Only the current layer |
| **Relative** | **View → Layer Visibility → Relative** | <kbd>Alt</kbd>+<kbd>2</kbd> | All layers, fading with distance from the current layer |
| **All layers** | **View → Layer Visibility → All layers** | <kbd>Alt</kbd>+<kbd>3</kbd> | All layers at full strength (the default) |

In **Relative** mode, each layer is drawn more transparent the further it is from the current
layer. The opacity multiplies with each step: with the default setting of 50%, the layers next to
the current layer are shown at 50%, the layers two steps away at 25%, and so on. Change the
percentage with the slider **When layer visibility is relative (gray dot)** in
**Preferences → Timeline → Layer Visibility**. The **Startup option** drop-down on the same page
sets the mode directly.

You can also switch modes from the timeline: the small circle at the top of the layers' visibility
column shows the current mode (hollow for **Current layer only**, gray for **Relative**, filled for
**All layers**). Click it to go to the next mode, or right-click it to go to the previous one.

When the current layer is a camera layer, all layers are shown at full strength in every mode.

<!-- SCREENSHOT: Timeline header with the layer visibility circle shown gray (Relative mode), and the canvas showing a faded background layer -->

## Vector display options {#vector-display}

These two options only affect vector layers, and are only available while a vector layer is the
current layer.

- **View → Show Invisible Lines** (also on the View Toolbar) shows strokes that were drawn with the
  **Invisible** option as thin dotted lines. Invisible strokes are normally hidden, which makes
  them hard to find and edit; this option lets you see them. See [Tools]({{ '/doc/manual/tools.html' | relative_url }})
  for the **Invisible** option.
- **View → Show Outlines Only** (also on the View Toolbar) hides all fills and draws every stroke as
  a thin line. Use it to see the structure of a vector drawing.

## Other View menu items {#other-view-items}

- **View → Onion Skin → Previous** (<kbd>O</kbd>) and **Next** (<kbd>Alt</kbd>+<kbd>O</kbd>)
  toggle onion skinning. See [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).
- **View → Preview** (<kbd>Alt</kbd>+<kbd>P</kbd>) is always grayed out in Pencil2D 0.7.2 and has
  no function.

{% include series-nav.html series=site.data.manual %}
