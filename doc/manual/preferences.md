---
layout: page
title: Preferences
tagline: Every page and every setting in the Preferences dialog, with its default value
comments: false
---

The Preferences dialog holds the settings that belong to Pencil2D itself rather than to a
project: the interface language, how the canvas looks, what happens at startup, autosave, timeline
behavior, tool behavior and keyboard shortcuts. This chapter lists every setting on every page, in
the order the dialog shows them, with its default value. Read it when you want to change how
Pencil2D behaves, or to find out what a setting does before you touch it.

{% include toc.html %}

## Opening Preferences {#opening}

To open the dialog, choose **Edit → Preferences**. On macOS, **Preferences** is in the
**Pencil2D** application menu instead. The command has no default keyboard shortcut, but you can
give it one on the [Shortcuts](#shortcuts) page.

The list on the left switches between the five pages: **General**, **Files**, **Timeline**,
**Tools** and **Shortcuts**. There is no OK or Apply button: every change takes effect as soon as
you make it and is remembered the next time you start Pencil2D. Click **Close** when you are done.
The only exceptions are the interface language, which needs a restart, and keyboard shortcuts,
which take effect when you close the dialog.

Preferences are stored per user on your computer, not in the project file, so they stay the same
whichever project you open.



## General {#general}

The **General** page is a long, scrolling page. Its settings are grouped into boxes.

![The General page of the Preferences dialog]({{ "/images/manual/preferences-general.png" | relative_url }})

### Language {#language}

| Option | What it does | Default |
|---|---|---|
| Language list | Sets the language of Pencil2D's menus, dialogs and messages. | **[System-Language]** |

**[System-Language]** follows your operating system's language. The list also offers Arabic,
Bulgarian, Catalan, Czech, Danish, German, Greek, English, Spanish, Estonian, Persian, French,
Hebrew, Hungarian, Indonesian, Italian, Japanese, Kabyle, Korean, Norwegian Bokmål, Dutch
(Netherlands), Polish, Portuguese (Portugal), Portuguese (Brazil), Russian, Slovene, Swedish,
Turkish, Vietnamese, Cantonese, Chinese (China) and Chinese (Taiwan). Each entry shows the
language's name in the current interface language, followed by its own name in brackets.

> **Note:** A language change needs a restart. When you pick a language, Pencil2D shows a
> **Restart Required** message: "The language change will take effect after a restart of
> Pencil2D". Save your work, quit and start Pencil2D again.

### Window Opacity {#window-opacity}

| Option | What it does | Default |
|---|---|---|
| **Opacity** | Makes the whole main window see-through, from 30% (most transparent) to 100% (solid). Useful for tracing something shown behind Pencil2D on your screen. | 100% (solid) |

### Appearance {#appearance}

| Option | What it does | Default |
|---|---|---|
| **Shadows** | Draws a soft shadow along the edges of the drawing area. | Off |
| **Tool Cursors** | Shows each tool's own icon as the mouse pointer. When off, most tools use a plain crosshair. | On |
| **Canvas Cursor** | Shows an outline of the brush size (and feather, for tools that have one) at the pointer while you use a drawing tool. | On |

### Background {#background}

Five buttons, shown as small picture swatches, set the pattern that fills the drawing area behind
your artwork: **checkerboard**, **white**, **grey**, **dots** and **weave** (in that order). The
default is **white**.

The background is only a display aid behind your drawing; it is not part of your artwork and is
not exported.

### Canvas {#canvas}

| Option | What it does | Default |
|---|---|---|
| **Antialiasing** | Smooths the edges of strokes and of the canvas display. Turn it off for hard, pixel-exact edges. | On |

### Editing {#editing}

| Option | What it does | Default |
|---|---|---|
| **Vector curve smoothing** | How much Pencil2D simplifies strokes drawn with the Pencil, Pen and Brush on a **vector** layer. Further right gives smoother curves with fewer points; further left keeps more of your hand's wobble. Range 1–100. Has no effect on bitmap layers. | 20 |
| **Tablet high-resolution position** | Stored and shown, but not used by Pencil2D 0.7.2: changing it has no visible effect. | On |

### Grid {#grid}

| Option | What it does | Default |
|---|---|---|
| **Enable Grid** | Shows the grid overlay on the canvas. This is the same switch as **View → Overlays → Grid** (<kbd>G</kbd>). | Off |
| **Grid Width** | Horizontal spacing of the grid lines, in canvas pixels (1–9999). | 100 |
| **Grid Height** | Vertical spacing of the grid lines, in canvas pixels (1–9999). | 100 |

The grid and other overlays are explained in
[Canvas and View]({{ '/doc/manual/canvas.html#overlays' | relative_url }}).

### Overlays {#overlays}

These settings control the **Safe Areas** overlay, which you switch on and off with
**View → Overlays → Safe Areas**. Safe areas are frames inset from the edge of the camera view;
keep important action inside the action-safe frame and text inside the title-safe frame so it
isn't cut off on screens that crop the picture.

| Option | What it does | Default |
|---|---|---|
| **Enable Action Safe area (%)** | Includes the action-safe frame in the Safe Areas overlay. The number is how far it is inset from the camera edge, as a percentage (1–25). | On, 5% |
| **Enable Title Safe area (%)** | Includes the title-safe frame in the Safe Areas overlay, inset by the given percentage (1–25). | On, 10% |
| **Show Safe area labels** | Writes a small label on each safe-area frame. Greyed out when both safe areas are turned off. | On |

> **Note:** If you turn off both safe areas, **View → Overlays → Safe Areas** is greyed out the
> next time you start Pencil2D.

### Scroll Wheel Zoom {#scroll-wheel-zoom}

| Option | What it does | Default |
|---|---|---|
| **Invert Scroll Direction** | Reverses which way the mouse wheel (or trackpad scroll) zooms the canvas. | Off |

See [Zoom]({{ '/doc/manual/canvas.html#zoom' | relative_url }}) for the other ways to zoom.

### Advanced {#advanced}

| Option | What it does | Default |
|---|---|---|
| **Memory Cache Budget** | How much memory, in MB, Pencil2D may use to keep frames loaded for faster drawing and playback (100–16000 MB). Raise it on a computer with plenty of RAM if long projects feel slow; lower it if Pencil2D uses too much memory. | 1024 MB |

## Files {#files}

The **Files** page controls what Pencil2D does when it starts or when you create a new project,
and whether it saves your work automatically.

![The Files page of the Preferences dialog]({{ "/images/manual/preferences-files.png" | relative_url }})

### Startup Settings {#startup-settings}

The top of this box is the list of **presets**. A preset is a saved project used as the starting
point for new projects, so you can begin every animation with your usual layers, camera size and
frame rate already set up. **Blank** is always in the list: it is Pencil2D's built-in new
project, with one camera layer and one bitmap layer. The default preset is shown in bold.

| Control | What it does |
|---|---|
| **+** | Saves the project that is currently open as a new preset, named "Preset *n*", and lets you type a new name for it straight away. |
| **-** | Deletes the selected preset. If it was the default, **Blank** becomes the default again. |
| **Make Default** | Makes the selected preset the default. |

To rename a preset, double-click its name in the list. **Blank** cannot be renamed.

Below the list, three options choose what happens when Pencil2D starts. The same choice also
applies when you choose **File → New**, except for **Load last active file**, which only affects
startup.

| Option | What it does | Default |
|---|---|---|
| **Ask on startup** | Shows the **Choose a Preset for your Project** dialog, where you pick a preset. Tick **Always use this preset** in that dialog to make your choice the default and stop being asked. | |
| **Load default preset** | Starts a new project from the default preset without asking. | Selected |
| **Load last active file** | Reopens the project you last opened or saved. If that file no longer exists, Pencil2D starts from the default preset instead. | |

Presets are covered in more detail in [Projects and Files]({{ '/doc/manual/projects.html#presets' | relative_url }}).

### Autosave Documents {#autosave-documents}

| Option | What it does | Default |
|---|---|---|
| **Enable autosave** | Saves your project automatically after a set number of changes. | Off |
| **Number of modifications before autosaving:** | How many changes (strokes, moves, clears and other undoable actions) trigger an automatic save (4–8192). | 15 |


If the project has never been saved, autosave can't know where to put it, so Pencil2D asks
instead: the **AutoSave Reminder** offers **Yes** (save now), **No**, or **Never ask again**
(stop asking for this project). How autosave fits with crash recovery is explained in
[Projects and Files]({{ '/doc/manual/projects.html#autosave' | relative_url }}).

## Timeline {#timeline}

The **Timeline** page sets how the timeline looks, what happens when you draw between keyframes,
the speed of the flip commands, sound scrubbing and the default layer visibility.

![The Timeline page of the Preferences dialog]({{ "/images/manual/preferences-timeline.png" | relative_url }})

### Timeline Options {#timeline-options}

| Option | What it does | Default |
|---|---|---|
| **Timeline length:** | How many frames the timeline shows before you have to extend it (1–9999). The timeline also grows by itself when you add keyframes near its end. | 240 |
| **Short scrub** | Draws the current-frame marker only in the frame-number strip at the top of the timeline, instead of down through all the layers. You can also toggle it by double-clicking the frame-number strip. | Off |

### Drawing {#drawing}

**When drawing on an empty frame:** decides what happens when you start drawing on a frame that
has no keyframe of its own (a frame that is just holding the previous drawing).

| Option | What it does | Default |
|---|---|---|
| **Create a new (blank) key-frame** | Adds a new, empty keyframe at the current frame and draws on it. | |
| **Duplicate the previous key-frame** | Copies the previous keyframe to the current frame and draws on the copy. | |
| **Keep drawing on the previous key-frame** | Adds your stroke to the previous keyframe, so the change shows on every frame it is held for. | Selected |

The dialog notes that this applies to the Pencil, Eraser, Pen, Polyline, Bucket and Brush tools.
In practice the **Eraser** never creates a keyframe, so it always works on the previous keyframe.
If the layer has no keyframe before the current frame, all three options create a new blank
keyframe. See [Keyframes]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}) for more.

### Flip and Roll {#flip-and-roll}

These settings control **Animation → Flip In-Between** and **Animation → Flip Rolling**, which
quickly flash through nearby drawings the way an animator flips paper, so you can check motion
without playing the whole animation.

| Option | What it does | Default |
|---|---|---|
| **Maximum numbers of drawings in roll** | How many previous keyframes **Flip Rolling** shows before returning to the current frame (3–10). | 5 |
| **Msecs per drawing in flip roll** | How long each drawing stays on screen during **Flip Rolling**, in milliseconds (100–400). | 100 |
| **Msecs per drawing in flip inbetween** | How long each drawing stays on screen during **Flip In-Between**, in milliseconds (100–400). | 100 |

### Sound Scrub {#sound-scrub}

| Option | What it does | Default |
|---|---|---|
| Slider and **ms** box | How long a snippet of sound plays each time you step to a frame while sound scrubbing is on. The shortest allowed value is one frame's duration at the project's frame rate (at most 100 ms); the longest is 200 ms. | 100 ms |

Sound scrubbing itself is turned on and off with the **Sound scrub on/off** button on the
timeline, not here. See [Sound]({{ '/doc/manual/sound.html' | relative_url }}).

### Layer Visibility {#layer-visibility}

| Option | What it does | Default |
|---|---|---|
| **Startup option** | Which layer visibility mode is used: **Current layer only**, **Relative** or **All Layers**. This is the same setting as **View → Layer Visibility**, so changing either one changes both, and the last choice is used when Pencil2D starts. | **All Layers** |
| **When layer visibility is relative (gray dot)** | In **Relative** mode, the opacity of the layers directly above and below the current one (0–100%). Layers further away fade more with each step. Only available when the mode is **Relative**. | 50% |

Layer visibility modes are explained in
[Canvas and View]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}).

## Tools {#tools}

The **Tools** page holds the few tool settings that aren't in the **Options** panel.

![The Tools page of the Preferences dialog]({{ "/images/manual/preferences-tools.png" | relative_url }})

| Box | Option | What it does | Default |
|---|---|---|---|
| **Brush Tools** | **Use Quick Sizing** | Lets you change a tool's size by holding <kbd>Shift</kbd> and dragging on the canvas, and its feather (Eraser, Brush and Smudge) by holding <kbd>Ctrl</kbd> and dragging. See [Quick sizing]({{ '/doc/manual/tools.html#quick-sizing' | relative_url }}). | On |
| **Move Tool** | **Rotation snap increment** | The angle steps used when you hold <kbd>Shift</kbd> while rotating a selection with the Move tool, or the camera (the Move tool on a camera layer). The slider only stops at angles that divide evenly into 360°, from 1 to 360 degrees; the label beside it shows the current value. | 15 degrees |
| **Hand Tool** | **Invert Zoom Direction** | Reverses the direction of zooming by dragging with the Hand tool (<kbd>Ctrl</kbd>+drag). Normally dragging down zooms in; with this on, dragging up zooms in. | Off |

## Shortcuts {#shortcuts}

The **Shortcuts** page lists every command that can have a keyboard shortcut, in two columns:
**Action** and **Shortcut**. Select a row to change its shortcut in the box below the list, or
use the buttons to save, load or restore the whole set:

| Control | What it does |
|---|---|
| **Shortcuts:** box | Click it and press a new key combination for the selected action. |
| **Clear** | Removes the shortcut from the selected action. |
| **Save** | Saves all your shortcuts to a Pencil2D shortcut file (`.pcls`). |
| **Load** | Loads shortcuts from a `.pcls` file. |
| **Restore Default Shortcuts** | Puts every shortcut back to its default, immediately and without asking. |

Step-by-step instructions, conflict handling and the full list of defaults are in
[Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html#customizing' | relative_url }}).

![The Shortcuts page of the Preferences dialog]({{ "/images/manual/preferences-shortcuts.png" | relative_url }})

{% include series-nav.html series=site.data.manual %}
