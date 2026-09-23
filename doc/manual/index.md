---
layout: page
title: User's Manual
tagline: The complete guide to Pencil2D, from your first drawing to the last menu item
comments: false
redirect_from:
  - /doc/user-manual.html
  - /doc/reference-manual.html
---

This manual describes **Pencil2D 0.7.2**. If you are new to Pencil2D, read
[Getting Started]({{ '/doc/manual/getting-started.html' | relative_url }}) first: it walks you through installing the
program and making a short animation in a few minutes. The remaining chapters are a reference,
so jump to whichever one covers what you need.

If you teach animation, the [Classroom Course]({{ '/doc/course/' | relative_url }}) is a set of ready-to-use lessons
built on this manual. For quick answers, try the [FAQ]({{ '/doc/faq.html' | relative_url }}).

> **Note:** On macOS, press <kbd>Cmd</kbd> wherever this manual says <kbd>Ctrl</kbd>, and
> <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.

## First Steps {#first-steps}

| Chapter | What you'll find |
|---|---|
| [Getting Started]({{ '/doc/manual/getting-started.html' | relative_url }}) | Installing Pencil2D, your first animation, and the ideas the rest of the manual builds on |
| [The Interface]({{ '/doc/manual/interface.html' | relative_url }}) | A tour of the main window, its panels and toolbars, and how to arrange them |
| [Projects and Files]({{ '/doc/manual/projects.html' | relative_url }}) | Creating, opening and saving projects, file formats, autosave and crash recovery |

## Drawing {#drawing}

| Chapter | What you'll find |
|---|---|
| [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}) | Zooming, panning, rotating and flipping the view; grids, guides and perspective overlays |
| [Tools]({{ '/doc/manual/tools.html' | relative_url }}) | Every tool in the toolbox and every one of its options |
| [Selecting and Transforming]({{ '/doc/manual/selection.html' | relative_url }}) | Selecting, moving, scaling, rotating and flipping artwork; the clipboard; peg bar alignment |
| [Color and Palettes]({{ '/doc/manual/color.html' | relative_url }}) | The color wheel, the color inspector and working with palettes |
| [Layers]({{ '/doc/manual/layers.html' | relative_url }}) | Bitmap, vector, camera and sound layers, and how to manage them |

## Animating {#animating}

| Chapter | What you'll find |
|---|---|
| [Timeline and Animation]({{ '/doc/manual/timeline.html' | relative_url }}) | Keyframes, exposure, playback, frame rate, and editing frames on the timeline |
| [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}) | Seeing previous and next drawings while you animate |
| [Camera]({{ '/doc/manual/camera.html' | relative_url }}) | Camera size, camera moves, easing and camera paths |
| [Sound]({{ '/doc/manual/sound.html' | relative_url }}) | Adding sound clips and timing animation to them |

## Sharing Your Work {#sharing}

| Chapter | What you'll find |
|---|---|
| [Importing and Exporting]({{ '/doc/manual/import-export.html' | relative_url }}) | Bringing in images, sequences, GIFs, video and sound; exporting images, videos and GIFs |

## Reference {#reference}

| Chapter | What you'll find |
|---|---|
| [Preferences]({{ '/doc/manual/preferences.html' | relative_url }}) | Every setting in the Preferences dialog |
| [Keyboard Shortcuts]({{ '/doc/manual/shortcuts.html' | relative_url }}) | All default shortcuts, and how to change them |
| [Menu Reference]({{ '/doc/manual/menus.html' | relative_url }}) | Every menu item, with a link to where it is explained |
| [Command-Line Interface]({{ '/doc/manual/command-line.html' | relative_url }}) | Exporting from the command line and in scripts |
| [Glossary]({{ '/doc/manual/glossary.html' | relative_url }}) | Animation and Pencil2D terms |

## More Help {#more-help}

- [FAQ]({{ '/doc/faq.html' | relative_url }}): answers to the questions people ask most.
- [Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}): what to do
  when a movie won't export.
- [Project File Recovery Guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }}): getting your work back
  after a crash.
- [Video tutorials]({{ '/doc/tutorials.html' | relative_url }}) made by the community.
- Still stuck? Ask on the [forum](https://discuss.pencil2d.org/) or our
  [Discord server](https://discord.gg/8FxdV2g), or [report a bug](https://github.com/pencil2d/pencil/issues).

> **Help improve this manual.** The manual lives in the
> [pencil2d.github.io repository](https://github.com/pencil2d/pencil2d.github.io/tree/master/doc/manual).
> If something is wrong, out of date or unclear, open an issue or a pull request there.

{% include series-nav.html series=site.data.manual %}
