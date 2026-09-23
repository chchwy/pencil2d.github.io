---
layout: page
title: The Interface
tagline: A tour of the main window, its panels and toolbars, and how to arrange them
comments: false
---

This chapter describes each part of the Pencil2D main window: the canvas, the panels, the toolbars and the status bar. It also explains how to move, float, hide, lock and reset panels. Use it to find your way around. Each section links to the chapter that explains that part in depth.

Shortcuts are written in their Windows/Linux form. On macOS, use <kbd>Cmd</kbd> for <kbd>Ctrl</kbd> and <kbd>Option</kbd> for <kbd>Alt</kbd>. On macOS, **Preferences** is in the **Pencil2D** application menu, not the **Edit** menu.

{% include toc.html %}

## The main window {#main-window}

With the default layout, the main window looks like this:

| Area | What's there |
|---|---|
| Top | The menu bar, then the **Main**, **View** and **Overlay** toolbars |
| Left | The **Tools**, **Options** and **Onion Skins** panels, stacked |
| Center | The canvas |
| Right | The **Color Box**, **Color Inspector** and **Color Palette** panels, stacked |
| Bottom | The **Timeline** panel, then the status bar |

On macOS, the menu bar is at the top of the screen, not in the window.

The window title shows the full path of the open project file, or "Pencil2D v0.7.2" for a project that hasn't been saved yet. When the project has unsaved changes, the title shows a modified marker: an asterisk (\*) on Windows and Linux, and a dot in the window's close button on macOS.

![The Pencil2D 0.7.2 main window with its areas numbered]({{ "/images/manual/main-window-annotated.png" | relative_url }})

1. [Menu bar](#menu-bar)
2. [Toolbars](#toolbars): Main Toolbar, View Toolbar and Overlay Toolbar
3. [Tools](#toolbox) panel
4. [Options](#tool-options) panel, showing the settings of the current tool
5. [Onion Skins](#onion-skin-panel) panel
6. [Canvas](#canvas), with the camera field in the middle
7. **Color Box** (the color wheel), see [color panels](#color-panels)
8. **Color Inspector**
9. **Color Palette**
10. [Timeline](#timeline-panel)
11. [Status bar](#status-bar)

Every panel can be moved, floated, hidden or closed. Pencil2D remembers the layout when you quit. See [Arranging windows](#arranging-windows).

### The menu bar {#menu-bar}

The menu bar has eight menus: **File**, **Edit**, **View**, **Animation**, **Tools**, **Layer**, **Windows** and **Help**. The [Menu Reference]({{ '/doc/manual/menus.html' | relative_url }}) lists every item. This chapter covers the **Windows** menu in [The Windows menu](#windows-menu).

### The canvas {#canvas}

The canvas is the large drawing area in the center. It extends without limit in every direction. The shaded area marks what lies outside the camera field, which isn't exported. For zooming, panning, rotating and flipping the view, overlays such as grids and perspective guides, and layer visibility modes, see [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}). For what the camera field is, see [Key concepts]({{ '/doc/manual/getting-started.html#key-concepts' | relative_url }}).

## Panels {#panels}

Pencil2D has seven panels. The **Windows** menu shows and hides each one. Its menu item uses the panel's title:

| Panel title | Default position | Show/hide shortcut | In depth |
|---|---|---|---|
| **Tools** | Left | <kbd>Ctrl</kbd>+<kbd>1</kbd> | [Tools]({{ '/doc/manual/tools.html' | relative_url }}) |
| **Options** | Left | <kbd>Ctrl</kbd>+<kbd>2</kbd> | [Tools]({{ '/doc/manual/tools.html#common-options' | relative_url }}) |
| **Color Box** | Right | <kbd>Ctrl</kbd>+<kbd>3</kbd> | [Color wheel]({{ '/doc/manual/color.html#color-wheel' | relative_url }}) |
| **Color Palette** | Right | <kbd>Ctrl</kbd>+<kbd>4</kbd> | [Palette]({{ '/doc/manual/color.html#palette' | relative_url }}) |
| **Timeline** | Bottom | <kbd>Ctrl</kbd>+<kbd>6</kbd> | [Timeline and Animation]({{ '/doc/manual/timeline.html' | relative_url }}) |
| **Color Inspector** | Right | <kbd>Ctrl</kbd>+<kbd>7</kbd> | [Color inspector]({{ '/doc/manual/color.html#color-inspector' | relative_url }}) |
| **Onion Skins** | Left | <kbd>Ctrl</kbd>+<kbd>8</kbd> | [Onion Skin]({{ '/doc/manual/onion-skin.html#onion-skin-panel' | relative_url }}) |

### Tools {#toolbox}

The **Tools** panel holds a button for each drawing and editing tool. In order: **Pencil**, **Eraser**, **Select**, **Move**, **Pen**, **Hand**, **Polyline**, **Bucket**, **Eyedropper**, **Brush** and **Smudge**. Hold the pointer over a button to see the tool's name, what it does and its shortcut key, for example "Pencil Tool (N): Sketch with pencil".

The panel rearranges its buttons to fit its size. It uses several rows and columns when it is wide, and shrinks to a single column when it is narrow. When the camera layer is selected, the **Move** button activates the **Camera** tool. You can also choose tools from the **Tools** menu or with their single-key shortcuts. **Tools → Reset to default** returns every tool's settings to their defaults.

The [Tools]({{ '/doc/manual/tools.html' | relative_url }}) chapter describes each tool.

### Options {#tool-options}

The **Options** panel shows the settings of the active tool, and its contents change when you switch tools. Typical settings are **Width**, **Feather**, **Pressure**, **Anti-Aliasing** and **Stabilizer**. The **Bucket** and **Camera** tools show their own sets of options here. Options that don't apply to the current layer type are hidden.

For what every option does, see [Tools → Common options]({{ '/doc/manual/tools.html#common-options' | relative_url }}) and the section for each tool.

### Color panels {#color-panels}

Three panels deal with color. All three show and change the same current color.

- **Color Box** holds the color wheel. Click or drag in the ring to pick a hue, and in the inner square to pick saturation and brightness. See [Color wheel]({{ '/doc/manual/color.html#color-wheel' | relative_url }}).
- **Color Inspector** sets the color by number, with **HSV** and **RGB** tabs and an alpha (**A**) value for transparency. See [Color inspector]({{ '/doc/manual/color.html#color-inspector' | relative_url }}).
- **Color Palette** holds the project's named color swatches. It has buttons to add and remove colors, and a menu to switch between **List Mode** and **Grid Mode** and to set the swatch size. See [Palette]({{ '/doc/manual/color.html#palette' | relative_url }}).

### Onion Skins {#onion-skin-panel}

The **Onion Skins** panel controls onion skinning, which shows faded copies of neighboring drawings so you can see motion while you draw. It has **Previous Frames** and **Next Frames** sections that you can switch on and off, each with a count and a color tint button. It also has a **Distributed Opacity** section (**Min** and **Max**), **Show Keyframes Only** and **Show During Playback**. See [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).

### Timeline {#timeline-panel}

The **Timeline** panel is where you manage layers and frames and play back your animation. It has two sides:

- **Left side:** the layer list, with a **Layers:** toolbar above it. The toolbar has buttons to **Add Layer** (which opens a menu of layer types), **Delete Layer** and **Duplicate Layer**.
- **Right side:** the frame tracks. The **Keys:** toolbar above them has buttons to **Add Frame**, **Remove Frame** and **Duplicate Frame**, followed by a **Zoom:** slider that sets the frame width.
- **Playback controls**, on the same toolbar row: **Jump to the Start**, **Play**, **Jump to the End**, **Loop**, the **fps** (frames per second) box, the **Range** check box with its start and end frame boxes, **Sound on/off**, **Sound scrub on/off**, and a menu that chooses what the timecode display next to it shows.

On a narrow window, some controls move into an overflow menu at the right end of the toolbar (**»**).

See [Timeline and Animation]({{ '/doc/manual/timeline.html#anatomy' | relative_url }}) for how to use each part, and [Layers]({{ '/doc/manual/layers.html' | relative_url }}) for the layer list.

![The Timeline panel]({{ "/images/manual/timeline.png" | relative_url }})

*The Timeline panel. The left side lists the layers; the right side shows their keyframes.*

## Toolbars {#toolbars}

Three toolbars sit below the menu bar. Each button does the same as the menu item of the same name.

| Toolbar | Buttons |
|---|---|
| **Main Toolbar** | **New**, **Open**, **Save** · **Undo**, **Redo** · **Cut**, **Copy**, **Paste**, **Clear Frame** |
| **View Toolbar** | **Zoom In**, **Zoom Out**, **Reset** (view) · **Horizontal Flip**, **Vertical Flip** · **Show Invisible Lines**, **Show Outlines Only** |
| **Overlay Toolbar** | **Grid**, **Center**, **Thirds**, **Golden Ratio**, **Safe Areas**, **One Point Perspective**, **Two Point Perspective**, **Three Point Perspective**, and a **Perspective Lines Angle** menu |

Notes on the View and Overlay toolbars:

- **Show Invisible Lines** and **Show Outlines Only** only work on vector layers and are grayed out on other layers.
- **Safe Areas** is grayed out if both the action-safe and title-safe areas are turned off in [Preferences]({{ '/doc/manual/preferences.html#general' | relative_url }}). This is checked when Pencil2D starts, so the change shows after a restart.
- **Horizontal Flip** and **Vertical Flip** mirror your view of the canvas, not the drawing itself.

To show or hide a toolbar, use **Windows → Toolbars** and click its name. To move a toolbar, drag its handle, the grip at its left or top end. You can drop it on another edge of the window, or drop it anywhere else to make it float.

What the view and overlay buttons do is covered in [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}) (see [Overlays]({{ '/doc/manual/canvas.html#overlays' | relative_url }}) and [Flip]({{ '/doc/manual/canvas.html#flip' | relative_url }})). The edit buttons are covered in [Selecting and Transforming]({{ '/doc/manual/selection.html#clipboard' | relative_url }}).

## The status bar {#status-bar}

The status bar runs along the bottom of the window. From left to right, it has:

- **Tool help:** the icon of the active tool and a hint on how to use it, for example "Click to draw. Hold Ctrl and Shift to erase or Alt to select a color from the canvas." For the Polyline tool, the hint changes while you are drawing a line.
- **Unsaved-changes indicator:** a save icon that is highlighted when the project has unsaved changes and grayed out when it doesn't. Hold the pointer over it to see which state it is in.
- **Zoom box:** shows the current zoom level. Choose a preset from the list (from 1% to 10000%), or type a value and press <kbd>Enter</kbd>.
- **Zoom slider:** drag it to zoom out (left) or in (right).

To hide or show the status bar, use **Windows → Status Bar**. It has no default shortcut, but you can assign one in [Preferences → Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }}).

## Arranging windows {#arranging-windows}

You can rearrange the panels to suit your screen. Pencil2D saves the layout when you quit and restores it the next time you start.

### Moving and docking panels {#docking}

Each panel has a title bar with its name and two small buttons: one floats the panel and one closes it.

- **To move a panel**, drag its title bar. As you drag over an edge of the main window, a highlighted gap shows where the panel will dock. Release to dock it there.
- **To place panels side by side or in a stack**, drop a panel beside or above another docked panel.
- **To stack panels as tabs**, drop one panel directly onto another. Click a tab to switch between them. This saves space, for example for the three color panels.
- **To resize docked panels**, drag the divider between them or between a panel and the canvas.

### Floating panels {#floating}

A floating panel is a separate window that you can place anywhere, including on a second monitor.

- **To float a panel**, click the float button in its title bar, double-click its title bar, or drag it away from the window edges.
- **To dock it again**, double-click its title bar, or drag it back to an edge of the main window.

### Hiding and showing panels {#hiding-panels}

To hide a panel, click the close button in its title bar, or clear its check mark in the **Windows** menu. To bring it back, choose it in the **Windows** menu or press its shortcut from the [panel table](#panels). Hiding a panel only hides it. It doesn't reset its settings.

### The Windows menu {#windows-menu}

The **Windows** menu contains:

| Item | What it does |
|---|---|
| **Reset Windows** | Shows every panel and docks it back in its default position. It doesn't change toolbars or the status bar. |
| **Lock Windows** | When checked, panels can't be moved, floated or closed, and their title bars are hidden |
| **Tools**, **Options**, **Color Box**, **Color Palette**, **Timeline**, **Color Inspector**, **Onion Skins** | Show or hide each panel |
| **Toolbars** | Submenu to show or hide the **Main Toolbar**, **View Toolbar** and **Overlay Toolbar** |
| **Status Bar** | Shows or hides the status bar |

**Reset Windows** has no default shortcut, but you can assign one in [Preferences → Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }}).

### Locking the layout {#locking}

Once the layout suits you, choose **Windows → Lock Windows** to stop panels being moved or closed by accident. This matters especially with a tablet pen, which can easily drag a title bar. While the layout is locked, the panel title bars are hidden, so panels can't be dragged, floated or closed. You can still resize them with the dividers.

To unlock, choose **Windows → Lock Windows** again. The setting is remembered between sessions. Locking doesn't affect toolbars.

### Resetting the layout {#resetting-layout}

If a panel is lost, for example it is floating off-screen or on a monitor that is no longer connected, choose **Windows → Reset Windows**. Every panel is shown again and docked in its default position: **Tools**, **Options** and **Onion Skins** on the left, the color panels on the right, and **Timeline** at the bottom.

If a toolbar is missing, turn it back on in **Windows → Toolbars**.

### Full screen and more drawing space {#full-screen}

Pencil2D v0.7.2 has no full-screen command. To get more room for the canvas:

- Maximize the window with your operating system's window controls. On macOS, the green button in the window's title bar also enters macOS full-screen mode.
- Hide panels you don't need with their shortcuts, for example <kbd>Ctrl</kbd>+<kbd>3</kbd>, <kbd>Ctrl</kbd>+<kbd>4</kbd> and <kbd>Ctrl</kbd>+<kbd>7</kbd> for the color panels. Press the same shortcut again to bring a panel back.
- Hide toolbars in **Windows → Toolbars** and the status bar with **Windows → Status Bar**.
- Stack panels as tabs, or float them onto a second monitor.

### Window opacity {#window-opacity}

To make the whole Pencil2D window partly transparent, go to **Edit → Preferences → General** and use the **Window opacity** setting. You can then trace over something that is behind the window on your screen. See [Preferences]({{ '/doc/manual/preferences.html#general' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
