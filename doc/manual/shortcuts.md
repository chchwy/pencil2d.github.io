---
layout: page
title: Keyboard Shortcuts
tagline: Every default shortcut, the keys and mouse moves that always work, and how to change them
comments: false
---

This chapter lists every keyboard shortcut Pencil2D 0.7.2 comes with, grouped by what the commands
do, followed by the keys and mouse actions that are built in and can't be changed. The last section
shows how to change shortcuts and how to save them to a file or load them from one. Print the
tables or keep this page open while you learn the program.

> **Note:** On macOS, press <kbd>Cmd</kbd> wherever this page says <kbd>Ctrl</kbd>, and
> <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>. <kbd>Enter</kbd> means the main
> Enter (Return) key, not the one on the number pad.

{% include toc.html %}

## Default Shortcuts {#defaults}

In the tables below, **Action** is the command's name in the menus, and **Shortcuts page name**
is how the same command is listed in **Edit → Preferences → Shortcuts**, where you can change it.
A dash (–) means the command has no shortcut by default; you can give it one yourself (see
[Customizing Shortcuts](#customizing)).

![The Shortcuts page of the Preferences dialog]({{ "/images/manual/preferences-shortcuts.png" | relative_url }})

### File {#file}

| Action | Default | Shortcuts page name |
|---|---|---|
| **File → New** | <kbd>Ctrl</kbd>+<kbd>N</kbd> | New File |
| **File → Open** | <kbd>Ctrl</kbd>+<kbd>O</kbd> | Open File |
| **File → Save** | <kbd>Ctrl</kbd>+<kbd>S</kbd> | Save File |
| **File → Save As...** | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd> | Save File As |
| **File → Import → Image...** | – | Import Image |
| **File → Import → Image Sequence...** | – | Import Image Sequence |
| **File → Import → Sound...** | – | Import Sound |
| **File → Export → Movie...** | – | Export Movie |
| **File → Export → Image Sequence...** | <kbd>Ctrl</kbd>+<kbd>R</kbd> | Export Image Sequence |
| **File → Export → Image...** | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd> | Export Image |
| **File → Export → Palette** | – | Export Palette |
| **File → Exit** | <kbd>Ctrl</kbd>+<kbd>Q</kbd> | Exit |

The Shortcuts page also lists **Export Sound**, set to <kbd>Ctrl</kbd>+<kbd>I</kbd>. Pencil2D 0.7.2
has no Export Sound command, so this shortcut does nothing.

### Edit {#edit}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Edit → Undo** | <kbd>Ctrl</kbd>+<kbd>Z</kbd> | Undo |
| **Edit → Redo** | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Z</kbd> | Redo |
| **Edit → Cut** | <kbd>Ctrl</kbd>+<kbd>X</kbd> | Cut |
| **Edit → Copy** | <kbd>Ctrl</kbd>+<kbd>C</kbd> | Copy |
| **Edit → Paste** | <kbd>Ctrl</kbd>+<kbd>V</kbd> | Paste |
| **Edit → Paste from Previous Keyframe** | <kbd>Ctrl</kbd>+<kbd>←</kbd> | Paste from Previous Keyframe |
| **Edit → Clear Frame** | – | Clear Frame |
| **Edit → Selection → Flip X** | – | Selection: Horizontal Flip |
| **Edit → Selection → Flip Y** | – | Selection: Vertical Flip |
| **Edit → Select All** | <kbd>Ctrl</kbd>+<kbd>A</kbd> | Select All |
| **Edit → Deselect All** | <kbd>Ctrl</kbd>+<kbd>D</kbd> | Deselect All |
| **Edit → Preferences** | – | Preferences |

### View {#view}

| Action | Default | Shortcuts page name |
|---|---|---|
| **View → Reset** | <kbd>Ctrl</kbd>+<kbd>H</kbd> | Reset View |
| **View → Center** | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>H</kbd> | Center View |
| **View → Zoom In** | <kbd>Ctrl</kbd>+<kbd>↑</kbd> | Zoom In |
| **View → Zoom Out** | <kbd>Ctrl</kbd>+<kbd>↓</kbd> | Zoom Out |
| **View → Zoom → 400%** | <kbd>4</kbd> | Set Zoom to 400% |
| **View → Zoom → 300%** | <kbd>3</kbd> | Set Zoom to 300% |
| **View → Zoom → 200%** | <kbd>2</kbd> | Set Zoom to 200% |
| **View → Zoom → 100%** | <kbd>1</kbd> | Set Zoom to 100% |
| **View → Zoom → 50%** | <kbd>Shift</kbd>+<kbd>2</kbd> | Set Zoom to 50% |
| **View → Zoom → 33%** | <kbd>Shift</kbd>+<kbd>3</kbd> | Set Zoom to 33% |
| **View → Zoom → 25%** | <kbd>Shift</kbd>+<kbd>4</kbd> | Set Zoom to 25% |
| **View → Rotate Clockwise** | <kbd>R</kbd> | Rotate Clockwise |
| **View → Rotate Anticlockwise** | <kbd>Z</kbd> | Rotate Anticlockwise |
| **View → Reset Rotation** | <kbd>Alt</kbd>+<kbd>H</kbd> | Reset Rotation |
| **View → Horizontal Flip** | <kbd>Shift</kbd>+<kbd>H</kbd> | View: Horizontal Flip |
| **View → Vertical Flip** | <kbd>Shift</kbd>+<kbd>V</kbd> | View: Vertical Flip |
| **View → Preview** | <kbd>Alt</kbd>+<kbd>P</kbd> | Preview |

**View → Preview** is always greyed out in 0.7.2, so <kbd>Alt</kbd>+<kbd>P</kbd> does nothing.

### Overlays, Onion Skin and Layer Visibility {#display}

| Action | Default | Shortcuts page name |
|---|---|---|
| **View → Overlays → Grid** | <kbd>G</kbd> | Toggle Grid |
| **View → Onion Skin → Previous** | <kbd>O</kbd> | Toggle Previous Onion Skin |
| **View → Onion Skin → Next** | <kbd>Alt</kbd>+<kbd>O</kbd> | Toggle Next Onion Skin |
| **View → Layer Visibility → Current layer only** | <kbd>Alt</kbd>+<kbd>1</kbd> | Show Current Layer Only |
| **View → Layer Visibility → Relative** | <kbd>Alt</kbd>+<kbd>2</kbd> | Show Layers Relative to Current Layer |
| **View → Layer Visibility → All layers** | <kbd>Alt</kbd>+<kbd>3</kbd> | Show All Layers |

The other overlays (center, thirds, golden ratio, safe areas and the perspective grids) have no
shortcut commands. See [Canvas and View]({{ '/doc/manual/canvas.html#overlays' | relative_url }}) and
[Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).

### Playback {#playback}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Animation → Play** / **Stop** | <kbd>Ctrl</kbd>+<kbd>Enter</kbd> | Play/Stop |
| **Animation → Loop** | <kbd>Ctrl</kbd>+<kbd>L</kbd> | Toggle Loop |
| **Animation → Flip In-Between** | <kbd>Alt</kbd>+<kbd>Z</kbd> | Flip In-Between |
| **Animation → Flip Rolling** | <kbd>Alt</kbd>+<kbd>X</kbd> | Flip Rolling |

**Animation → Range** can't be given a shortcut.

### Frames and Keyframes {#frames}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Animation → Next Frame** | <kbd>.</kbd> (period) | Next Frame |
| **Animation → Previous Frame** | <kbd>,</kbd> (comma) | Previous Frame |
| **Animation → Next Keyframe** | <kbd>Alt</kbd>+<kbd>.</kbd> | Next Keyframe |
| **Animation → Previous KeyFrame** | <kbd>Alt</kbd>+<kbd>,</kbd> | Previous Keyframe |
| **Animation → Add Frame** | <kbd>F7</kbd> | Add Frame |
| **Animation → Duplicate Frame** | <kbd>F6</kbd> | Duplicate Frame |
| **Animation → Remove Frame** | <kbd>Shift</kbd>+<kbd>F5</kbd> | Remove Frame |
| **Animation → Move Frame Forward** | <kbd>Ctrl</kbd>+<kbd>.</kbd> | Move Frame Forward |
| **Animation → Move Frame Backward** | <kbd>Ctrl</kbd>+<kbd>,</kbd> | Move Frame Backward |
| **Animation → Timeline Selection → Add Exposure** | <kbd>Ctrl</kbd>+<kbd>+</kbd> | Selection: Add Frame Exposure |
| **Animation → Timeline Selection → Subtract Exposure** | <kbd>Ctrl</kbd>+<kbd>-</kbd> | Selection: Subtract Frame Exposure |
| **Animation → Timeline Selection → Reverse Frames Order** | – | Selection: Reverse Keyframes |
| **Animation → Timeline Selection → Remove Frames** | – | Selection: Remove Keyframes |

The canvas also has built-in frame keys (<kbd>←</kbd> and <kbd>→</kbd>); see
[Keys on the canvas](#canvas-keys). Working with frames and keyframes is covered in
[Timeline and Animation]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}).

### Tools {#tools}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Tools → Pencil** | <kbd>N</kbd> | Pencil Tool |
| **Tools → Eraser** | <kbd>E</kbd> | Eraser Tool |
| **Tools → Select** | <kbd>V</kbd> | Select Tool |
| **Tools → Move** | <kbd>M</kbd> | Move Tool |
| **Tools → Pen** | <kbd>P</kbd> | Pen Tool |
| **Tools → Hand** | <kbd>H</kbd> | Hand Tool |
| **Tools → Polyline** | <kbd>Y</kbd> | Polyline Tool |
| **Tools → Bucket** | <kbd>K</kbd> | Bucket Tool |
| **Tools → Eyedropper** | <kbd>I</kbd> | Eyedropper Tool |
| **Tools → Brush** | <kbd>B</kbd> | Brush Tool |
| **Tools → Smudge** | <kbd>A</kbd> | Smudge Tool |

Tool shortcuts are ignored while you are in the middle of a stroke with the mouse. The tooltip of
each button in the **Tools** panel also shows its shortcut. Every tool is described in
[Tools]({{ '/doc/manual/tools.html' | relative_url }}).

### Layers {#layers}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Layer → New Bitmap Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd> | New Bitmap Layer |
| **Layer → New Vector Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>V</kbd> | New Vector Layer |
| **Layer → New Sound Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>W</kbd> | New Sound Layer |
| **Layer → New Camera Layer** | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>C</kbd> | New Camera Layer |
| **Layer → Delete Current Layer** | – | Delete Current Layer |

### Windows {#windows}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Windows → Reset Windows** | – | Reset Windows |
| **Windows → Tools** | <kbd>Ctrl</kbd>+<kbd>1</kbd> | Toggle Tools Window Visibility |
| **Windows → Options** | <kbd>Ctrl</kbd>+<kbd>2</kbd> | Toggle Options Window Visibility |
| **Windows → Color Box** | <kbd>Ctrl</kbd>+<kbd>3</kbd> | Toggle Color Box Window Visibility |
| **Windows → Color Palette** | <kbd>Ctrl</kbd>+<kbd>4</kbd> | Toggle Color Palette Window Visibility |
| **Windows → Timeline** | <kbd>Ctrl</kbd>+<kbd>6</kbd> | Toggle Timeline Window Visibility |
| **Windows → Color Inspector** | <kbd>Ctrl</kbd>+<kbd>7</kbd> | Toggle Color Inspector Window Visibility |
| **Windows → Onion Skins** | <kbd>Ctrl</kbd>+<kbd>8</kbd> | Toggle Onion Skins Window Visibility |
| **Windows → Status Bar** | – | Toggle Status Bar Visibility |

<kbd>Ctrl</kbd>+<kbd>5</kbd> is not used. The panels are described in
[The Interface]({{ '/doc/manual/interface.html' | relative_url }}).

### Help {#help}

| Action | Default | Shortcuts page name |
|---|---|---|
| **Help → Quick Reference Guide** | <kbd>F1</kbd> | (not listed) |

<kbd>F1</kbd> is fixed and does not appear on the Shortcuts page. In 0.7.2 it stops working after
you close the Preferences dialog, until you restart Pencil2D; the menu item still works.

A few menu commands can't be given a shortcut at all because they are not on the Shortcuts page:
**File → Import → Movie Video...**, **Movie Audio...**, **Image Predefined set...**,
**Animated Image...**, **Layers from Project file...**, **Replace Palette...** and
**Append to Palette...**, **File → Export → Animated GIF...**, **Edit → Peg bar Alignment**, the
other overlays, **Show Invisible Lines**, **Show Outlines Only**, **Reposition Selected Frames**,
**Tools → Reset to default**, **Layer → Change line color**, **Layer / Keyframe opacity**,
**Lock Windows**, the toolbar toggles and the rest of the **Help** menu.

## Keys and Mouse Actions You Can't Change {#fixed-keys}

These interactions are built into the canvas and the tools. They don't appear on the Shortcuts
page and always use the keys shown here.

### Modifier Keys While Drawing {#drawing-modifiers}

| Key | Works with | What it does |
|---|---|---|
| Hold <kbd>Alt</kbd> | Pencil, Eraser, Pen, Brush, Bucket | Switches to the Eyedropper while held, so you can pick a color from the canvas. |
| Hold <kbd>Ctrl</kbd>+<kbd>Shift</kbd> | Any tool | Switches to the Eraser while held. |
| <kbd>Shift</kbd>+drag | Pencil, Eraser, Pen, Brush, Polyline, Smudge | Changes the tool's width ([quick sizing]({{ '/doc/manual/tools.html#quick-sizing' | relative_url }})). |
| <kbd>Ctrl</kbd>+drag | Eraser, Brush, Smudge | Changes the tool's feather ([quick sizing]({{ '/doc/manual/tools.html#quick-sizing' | relative_url }})). |
| Hold <kbd>Alt</kbd> | Smudge | Switches to the Smudge tool's alternative (liquify) mode while held. |
| <kbd>Enter</kbd> | Polyline | Finishes the current line (so does double-clicking). |
| <kbd>Esc</kbd> | Polyline | Cancels the line you are drawing. |

Quick sizing only works while **Use Quick Sizing** is on in
[Preferences → Tools]({{ '/doc/manual/preferences.html#tools' | relative_url }}). Pencil2D has no modifier key for drawing
straight lines with the Pencil, Pen or Brush; use the
[Polyline tool]({{ '/doc/manual/tools.html#polyline' | relative_url }}) instead.

### Selecting, Moving and Rotating {#selection-keys}

| Key | Works with | What it does |
|---|---|---|
| Hold <kbd>Alt</kbd> | Select | Switches to the Move tool while held, so you can drag the selection. |
| <kbd>Shift</kbd>+drag | Move | Keeps the proportions when scaling, and keeps the selection on a straight horizontal or vertical line when moving. |
| <kbd>Ctrl</kbd>+drag | Move | Rotates the selection when you drag inside it. |
| <kbd>Shift</kbd> while rotating | Move (also the camera, on a camera layer) | Snaps the angle to the **Rotation snap increment** set in [Preferences → Tools]({{ '/doc/manual/preferences.html#tools' | relative_url }}) (15° by default). |
| <kbd>↑</kbd> <kbd>↓</kbd> <kbd>←</kbd> <kbd>→</kbd> | Any selection | Nudges the selection by one pixel. |
| <kbd>Enter</kbd> | Any selection | Applies the transformation and deselects. |
| <kbd>Esc</kbd> | Any selection | Cancels the transformation and deselects. |
| <kbd>Backspace</kbd> | Any selection | Deletes the selected content. |

Selections are covered in [Selecting and Transforming]({{ '/doc/manual/selection.html#transforming' | relative_url }}).

### Keys on the Canvas {#canvas-keys}

When nothing is selected and the canvas has keyboard focus:

| Key | What it does |
|---|---|
| <kbd>→</kbd> / <kbd>←</kbd> | Goes to the next / previous frame. |
| <kbd>↑</kbd> / <kbd>↓</kbd> | Makes the layer above / below the current one the current layer. |
| Hold <kbd>Space</kbd> | Switches to the Hand tool while held, so you can drag to pan. |

### Navigating with the Mouse {#mouse}

| Action | What it does |
|---|---|
| Mouse wheel over the canvas | Zooms in or out around the pointer. The direction can be reversed in [Preferences → General]({{ '/doc/manual/preferences.html#scroll-wheel-zoom' | relative_url }}). |
| Middle-button or right-button drag | Pans the view, whichever tool is selected. |
| Drag with the Hand tool | Pans the view. |
| <kbd>Alt</kbd>+drag with the Hand tool | Rotates the view around the center of the canvas. |
| <kbd>Ctrl</kbd>+drag with the Hand tool | Zooms: drag down to zoom in, up to zoom out (reversible in [Preferences → Tools]({{ '/doc/manual/preferences.html#tools' | relative_url }})). |
| Right-button double-click with the Hand tool | Resets the view (same as **View → Reset**). |
| Tablet pen's eraser end | Switches to the Eraser while you use it. |

More about moving around the canvas is in [Canvas and View]({{ '/doc/manual/canvas.html#pan' | relative_url }}).

### On the Timeline {#timeline-mouse}

| Action | What it does |
|---|---|
| Mouse wheel | Scrolls the layer list up and down. |
| <kbd>Shift</kbd>+mouse wheel | Scrolls the frames left and right. |
| <kbd>Ctrl</kbd>+click a frame | Adds the frame to the selection, or removes it. |
| <kbd>Shift</kbd>+click a frame | Selects every frame from the last selected one to this one. |
| <kbd>Alt</kbd>+click a frame | Selects this keyframe and every keyframe after it on the layer. |
| Double-click the frame-number strip | Turns **Short scrub** on or off. |

See [Selecting frames]({{ '/doc/manual/timeline.html#selecting-frames' | relative_url }}).

## Customizing Shortcuts {#customizing}

You can change the shortcut of any command on the Shortcuts page, remove shortcuts you keep
pressing by accident, and save your set to a file to use on another computer.

<!-- SCREENSHOT: The Shortcuts page of the Preferences dialog with "Pencil Tool" selected and the Shortcuts box showing N, with the Clear, Save, Load and Restore Default Shortcuts buttons visible -->

### Changing a Shortcut {#changing}

1. Choose **Edit → Preferences** (on macOS, **Pencil2D → Preferences**) and click **Shortcuts**.
2. Click the command in the list. Its name appears next to **Action:** below the list.
3. Click in the **Shortcuts:** box and press the new key combination. Pencil2D records it once
   you stop pressing keys, and the list updates.
4. Click **Close**. New shortcuts start working when the Preferences dialog closes.

To remove a command's shortcut, select the command and click **Clear**.

If the combination you press already belongs to another command, Pencil2D shows **Shortcut
Conflict!** with the message "*(key)* is already used, overwrite?". Click **Yes** to move the
shortcut to the new command (the other command is left with no shortcut), or **No** to keep
things as they were.

> **Tip:** Single letters are quick to press but easy to hit by accident. Tool shortcuts are single
> letters by default; if you type in text boxes a lot, check that the canvas has focus before
> pressing them.

### Restoring the Defaults {#restore-defaults}

Click **Restore Default Shortcuts** to put every shortcut back to the default listed on this page.
This happens immediately, without asking, and replaces all your changes.

### Saving and Loading Shortcut Files {#shortcut-files}

Shortcut sets can be saved to Pencil2D shortcut files, which use the `.pcls` extension.

- To **save** your current shortcuts, click **Save**, choose a folder and file name (the suggested
  name is `untitled.pcls`), and click **Save** in the file dialog.
- To **load** a shortcut file, click **Load** and pick the `.pcls` file. Every shortcut stored in
  the file replaces your current one; commands that aren't in the file keep their current
  shortcut. If the file can't be read or isn't a shortcut file, nothing changes.

After you have saved a shortcut file, the Save and Load dialogs start from that file's location.

{% include series-nav.html series=site.data.manual %}
