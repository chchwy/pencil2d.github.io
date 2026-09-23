---
layout: page
title: Quick Reference
tagline: A one-page cheat sheet of Pencil2D shortcuts and quick fixes for students
comments: false
---

Print this page and keep it next to the computer. These are Pencil2D v0.7.2's default shortcuts. On macOS, press <kbd>Cmd</kbd> for <kbd>Ctrl</kbd> and <kbd>Option</kbd> for <kbd>Alt</kbd>. On many laptops, <kbd>F6</kbd>, <kbd>F7</kbd> and <kbd>F5</kbd> need <kbd>Fn</kbd> held down. The full list is in [Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html' | relative_url }}).

## Files and Editing {#files}

| Action | Keys | Action | Keys |
|---|---|---|---|
| New project | <kbd>Ctrl</kbd>+<kbd>N</kbd> | Undo | <kbd>Ctrl</kbd>+<kbd>Z</kbd> |
| Open | <kbd>Ctrl</kbd>+<kbd>O</kbd> | Redo | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Z</kbd> |
| Save | <kbd>Ctrl</kbd>+<kbd>S</kbd> | Copy / Paste | <kbd>Ctrl</kbd>+<kbd>C</kbd> / <kbd>Ctrl</kbd>+<kbd>V</kbd> |
| Save As | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd> | Select all / Deselect all | <kbd>Ctrl</kbd>+<kbd>A</kbd> / <kbd>Ctrl</kbd>+<kbd>D</kbd> |

Export an animated GIF: **File → Export → Animated GIF...** Always save projects as **Pencil2D Project (\*.pclx)**.

## Tools {#tools}

| Tool | Key | Tool | Key | Tool | Key |
|---|---|---|---|---|---|
| Pencil | <kbd>N</kbd> | Brush | <kbd>B</kbd> | Select | <kbd>V</kbd> |
| Eraser | <kbd>E</kbd> | Bucket | <kbd>K</kbd> | Move | <kbd>M</kbd> |
| Pen | <kbd>P</kbd> | Eyedropper | <kbd>I</kbd> | Hand | <kbd>H</kbd> |

**While drawing:** hold <kbd>Space</kbd> and drag to move the view. Hold <kbd>Alt</kbd> and click to pick a color from the drawing. Hold <kbd>Shift</kbd> and drag to change the tool's width.

## Frames and Playback {#frames}

| Action | Keys |
|---|---|
| Play / Stop | <kbd>Ctrl</kbd>+<kbd>Enter</kbd> |
| Loop on / off | <kbd>Ctrl</kbd>+<kbd>L</kbd> |
| Next / previous frame | <kbd>.</kbd> / <kbd>,</kbd> |
| Next / previous keyframe | <kbd>Alt</kbd>+<kbd>.</kbd> / <kbd>Alt</kbd>+<kbd>,</kbd> |
| **Add Frame** (new blank keyframe) | <kbd>F7</kbd> |
| **Duplicate Frame** (copy this drawing to the next frame) | <kbd>F6</kbd> |
| **Remove Frame** (delete this keyframe) | <kbd>Shift</kbd>+<kbd>F5</kbd> |
| Move keyframe one frame later / earlier | <kbd>Ctrl</kbd>+<kbd>.</kbd> / <kbd>Ctrl</kbd>+<kbd>,</kbd> |
| Flip between the drawings before and after | <kbd>Alt</kbd>+<kbd>Z</kbd> |
| Onion skin: previous / next drawings | <kbd>O</kbd> / <kbd>Alt</kbd>+<kbd>O</kbd> |

**In the timeline:** click in the frame-number row, above a frame, to go to that frame. Click a keyframe to select it, then drag it to move it. <kbd>Shift</kbd>+click selects a range; <kbd>Alt</kbd>+click selects a keyframe and everything after it. The **fps** box sets the playback speed.

## Layers and View {#layers-view}

| Action | Keys |
|---|---|
| New bitmap layer | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd> |
| Show all layers again | <kbd>Alt</kbd>+<kbd>3</kbd> |
| Zoom in / out | Mouse wheel, or <kbd>Ctrl</kbd>+<kbd>↑</kbd> / <kbd>Ctrl</kbd>+<kbd>↓</kbd> |
| Zoom to 100 % | <kbd>1</kbd> |
| Reset zoom and rotation | <kbd>Ctrl</kbd>+<kbd>H</kbd> |
| Mirror the view (check your drawing) | <kbd>Shift</kbd>+<kbd>H</kbd> |

**Layers:** double-click a layer name to rename it. Drag a name up or down to reorder. Click the small round dot at the left of a name to hide or show the layer: filled means visible.

## I'm Stuck {#stuck}

| Problem | Try this |
|---|---|
| Nothing appears when I draw | Click your drawing layer (not **Camera Layer**). Press <kbd>N</kbd> for the Pencil. |
| "You are trying to modify a hidden layer!" | Click the empty dot at the left of the layer name to show it. |
| My drawing went onto the previous frame | Undo, press <kbd>F7</kbd> to add a keyframe, draw again. |
| I can't see my last drawing | Press <kbd>O</kbd> for onion skin. |
| The canvas is tilted, tiny or huge | <kbd>Ctrl</kbd>+<kbd>H</kbd>. If it's mirrored, press <kbd>Shift</kbd>+<kbd>H</kbd>. |
| Other layers disappeared | <kbd>Alt</kbd>+<kbd>3</kbd> (**View → Layer Visibility → All layers**). |
| A panel disappeared | **Windows → Reset Windows**. |
| It plays too fast or too slow | Check the **fps** box in the timeline (12 is normal). |
| A blank frame flashes when playing | Go to the empty keyframe and press <kbd>Shift</kbd>+<kbd>F5</kbd>. |
| The Bucket fills everything | Close the gap in your line. On a color layer, set **Reference** to **All layers**. |
| Pencil2D crashed | Start it again and choose to restore the project. |

Still stuck? Ask your neighbor, then your teacher. More help: [FAQ]({{ '/doc/faq.html' | relative_url }}) and the [User's Manual]({{ '/doc/manual/' | relative_url }}).

{% include series-nav.html series=site.data.course %}
