---
layout: page
title: Getting Started
tagline: Install Pencil2D, make your first animation, and learn the ideas everything else builds on
comments: false
---

This chapter takes you from download to a finished, saved animation. It covers installing Pencil2D on Windows, macOS and Linux, what you see the first time you start it, a short guided exercise, and the key ideas (camera, keyframes, layers) that the rest of the manual assumes you know. If you have never used Pencil2D before, read it from top to bottom.

This manual describes **Pencil2D v0.7.2**. Keyboard shortcuts are written in their Windows/Linux form. On macOS, use <kbd>Cmd</kbd> wherever this manual says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.

{% include toc.html %}

## Installing Pencil2D {#install}

Pencil2D is free and open source. Get it from the [download page]({{ '/download/' | relative_url }}). The download page always links to the current stable release. For other versions, see the [GitHub releases page](https://github.com/pencil2d/pencil/releases).

> **Note:** The [nightly builds]({{ '/download/nightly/' | relative_url }}) are development versions of a future release. They may behave differently from what this manual describes and may be unstable. Don't use them for important work.

### Windows {#install-windows}

Pencil2D for Windows 7 and later is distributed as a ZIP archive, in a 64-bit and a 32-bit version. Choose 64-bit unless you know your Windows is 32-bit.

> **Note:** A Windows installer is being introduced in the [nightly builds]({{ '/download/nightly/' | relative_url }}). For 0.7.2, use the ZIP file.

To install Pencil2D from the ZIP file:

1. Download the ZIP file from the [download page]({{ '/download/' | relative_url }}).
2. Unblock the file before extracting it: right-click it, choose **Properties**, tick **Unblock** on the **General** tab, and click **OK**. This stops Windows from blocking the files inside.
3. Right-click the ZIP file and choose **Extract All…**. Extract it to a permanent folder, for example a `Pencil2D` folder in your user folder or in `Program Files`.
4. Open the extracted folder and double-click `pencil2d.exe`.

Nothing needs to be installed. To make Pencil2D easier to start, right-click `pencil2d.exe` and pin it to the Start menu or taskbar. To remove Pencil2D, delete the folder. Your settings are stored per user, not in the program folder, so they are kept if you delete the folder or replace it with a newer version.

If Windows shows a blue "Windows protected your PC" (SmartScreen) message, click **More info** and then **Run anyway**. Pencil2D isn't digitally signed, so Windows is cautious about it. For step-by-step help with SmartScreen, unblocking, antivirus exceptions and permissions, see [How to Train Your Pencil2D]({{ '/doc/how-to-train-your-pencil2d.html' | relative_url }}).

> **Tip:** Don't run `pencil2d.exe` from inside the ZIP file without extracting it first. Windows then can't find the files next to it, and you get errors such as "Qt5Widgets.dll was not found". The [download page troubleshooting section]({{ '/download/#troubleshooting' | relative_url }}) explains this and other missing-DLL errors.

### macOS {#install-macos}

Pencil2D v0.7.2 for macOS is a DMG disk image. It requires macOS 10.14 or later. It is built for Intel Macs; on Apple Silicon Macs (M1 and later) it runs through Apple's Rosetta 2, which macOS offers to install the first time you open it.

1. Download the DMG from the [download page]({{ '/download/' | relative_url }}).
2. Open it and drag **Pencil2D** into your **Applications** folder.
3. Start Pencil2D from Applications or Launchpad.

Starting with v0.7.2, the app is notarized by Apple, so macOS no longer shows the "unidentified developer" warning. If macOS still refuses to open it, see the macOS entry in the [download page troubleshooting section]({{ '/download/#troubleshooting' | relative_url }}).

Other ways to get Pencil2D on a Mac:

- **Homebrew:** `brew install --cask pencil2d`
- **macOS 10.7 to 10.13:** the download page offers an older legacy build (v0.7.0). It doesn't get the latest fixes.

### Linux {#install-linux}

The download page offers Pencil2D as an **AppImage**, a single file that runs on most distributions without installation. It comes in 64-bit (`amd64`) and 32-bit (`i686`) versions. The AppImages require Ubuntu 16.04 or a comparable or newer distribution.

To run the AppImage:

1. Download the `.AppImage` file.
2. Make it executable, either from your file manager (**Properties → Permissions → Allow executing file as program**, or similar) or from a terminal:

   ```
   chmod +x pencil2d-linux-amd64-v0.7.2.AppImage
   ```

3. Double-click it, or run it from a terminal with `./pencil2d-linux-amd64-v0.7.2.AppImage`.

The download page also lists distribution packages (Arch Linux, Debian/Ubuntu, Fedora, FreeBSD) and a Flatpak (`flatpak install flathub org.pencil2d.Pencil2D`). Those packages are maintained separately and can be older than v0.7.2. Check the version in **Help → About** after you install one.

## First launch {#first-launch}

### Startup messages {#startup-messages}

Most of the time Pencil2D opens straight to an empty project. You may see one of these messages first:

- **An instance of Pencil2D is already open.** Pencil2D warns you if it is already running: "Running multiple instances of Pencil2D simultaneously is not recommended and could potentially result in data loss and other unexpected behavior." Click **Close** to cancel starting the second copy, or **Open** to start it anyway. Normally you should close it and switch to the window that is already open.
- **Restore Project?** If Pencil2D didn't close correctly last time, for example because it crashed or the computer lost power, it offers to restore the unsaved project. See [Crash recovery]({{ '/doc/manual/projects.html#recovery' | relative_url }}).
- **Choose a Preset for your Project.** This appears only if you have turned on **Ask on startup** in **Edit → Preferences → Files**. See [Presets]({{ '/doc/manual/projects.html#presets' | relative_url }}).

Pencil2D doesn't check for updates automatically. To check whether a newer version exists, choose **Help → Check for Updates**.

Pencil2D uses your system language if a translation for it exists. To change the language, go to **Edit → Preferences → General → Language** and restart Pencil2D. On macOS, **Preferences** is in the **Pencil2D** application menu instead of the **Edit** menu.

### What you see {#what-you-see}

A new project opens in the main window. The main parts are:

- The **canvas** in the middle, where you draw. A lighter rectangle marks the **camera field**, the area that ends up in your exported video. Everything outside it is shaded.
- The **Tools** panel on the left, with the **Options** panel for the current tool and the **Onion Skins** panel below it.
- The color panels on the right: **Color Box** (the color wheel), **Color Inspector** and **Color Palette**.
- The **Timeline** along the bottom, with two layers: **Bitmap Layer** (selected) and **Camera Layer**.
- Toolbars under the menu bar, and a status bar at the bottom of the window that shows help for the current tool and the zoom level.

The **Pencil** tool is selected, the playback speed is 12 frames per second, and each layer starts with one keyframe at frame 1. [The Interface]({{ '/doc/manual/interface.html' | relative_url }}) chapter covers every part of the window in detail.

![The Pencil2D 0.7.2 main window]({{ "/images/manual/main-window.png" | relative_url }})

*The Pencil2D main window with the default layout. This project has three layers and onion skin turned on.*

## Your first animation in five minutes {#first-animation}

In this exercise you animate a ball dropping onto the ground. It uses only the default project and a few keys.

1. **Check the layer.** In the Timeline, make sure **Bitmap Layer** is highlighted. If it isn't, click its name. You can't draw on the camera layer.
2. **Draw the first drawing.** Frame 1 already has a keyframe. With the **Pencil** tool (<kbd>N</kbd>), draw a small ball near the top of the camera field and a line near the bottom as the ground.
3. **Add a new keyframe.** Press <kbd>F7</kbd>, or click the **Add Frame** button next to **Keys:** in the Timeline. Pencil2D adds a blank keyframe at frame 2 and moves you there. The canvas looks empty because this is a new drawing.
4. **Turn on onion skin.** Press <kbd>O</kbd>, or choose **View → Onion Skin → Previous**. The previous drawing now shows faintly behind the current one, so you can see where the ball was.
5. **Draw the next position.** Trace the ground line again and draw the ball a little lower than before.
6. **Repeat.** Press <kbd>F7</kbd> and draw again until the ball reaches the ground. Try making the gaps between positions bigger as the ball falls, so it speeds up. Four to six drawings are enough.
7. **Play it.** Press <kbd>Ctrl</kbd>+<kbd>Enter</kbd>, or click the **Play** button in the Timeline. Press <kbd>Ctrl</kbd>+<kbd>L</kbd> (or click **Loop**) to repeat the playback, and press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> again to stop. To step through the drawings one frame at a time, use <kbd>.</kbd> (next frame) and <kbd>,</kbd> (previous frame).
8. **Adjust the timing.** Change the **fps** box in the Timeline to play faster or slower. To make one drawing stay on screen longer, see [Exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}).
9. **Save.** Press <kbd>Ctrl</kbd>+<kbd>S</kbd>. Because the project is new, a **Save animation** dialog opens. Choose a name and a folder, then click **Save**. The project is saved as a `.pclx` file.
10. **Share it (optional).** To turn the animation into a video or GIF, use **File → Export → Movie…** or **File → Export → Animated GIF…**. See [Importing and Exporting]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

![A bouncing ball with onion skin: earlier positions in red, later ones in blue]({{ "/images/manual/onion-skin-example.png" | relative_url }})

*With the color onion skin options turned on, drawings before the current frame show in red and the ones after it in blue.*

> **Warning:** Add a keyframe before you draw a new drawing. If you move to an empty frame (for example with <kbd>.</kbd>) and draw without adding a keyframe first, your strokes go onto the previous keyframe by default, and they change that drawing. To change this behavior, see **When drawing on an empty frame** under [Preferences → Timeline]({{ '/doc/manual/preferences.html#timeline' | relative_url }}).

> **Tip:** To undo a mistake, press <kbd>Ctrl</kbd>+<kbd>Z</kbd>. To redo, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Z</kbd>.

## Key concepts {#key-concepts}

The rest of this manual uses the ideas below all the time. Each section links to the chapter that covers the feature in full.

### Infinite canvas and the camera field {#canvas-and-camera}

The canvas has no edges. You can draw anywhere and pan as far as you like. What gets **exported** is only what the camera sees. The **camera field** is the lighter rectangle on the canvas. In a new project it is 800 × 600 pixels (or the size you last set in a camera layer's properties), and the area outside it is shaded.

This means you can draw backgrounds bigger than the screen, keep reference sketches off to the side, and move, rotate or zoom the camera over time to pan across a scene. The camera is controlled by a **camera layer**. See [Camera]({{ '/doc/manual/camera.html' | relative_url }}) for how to change the camera size and animate it. See [Canvas and View]({{ '/doc/manual/canvas.html' | relative_url }}) for how to zoom, pan and rotate your *view* of the canvas. Changing your view doesn't change the export.

### Frames and keyframes {#frames-and-keyframes}

The Timeline is a row of numbered **frames**. At 12 frames per second, frames 1 to 12 make up one second of animation.

A **keyframe** is a frame that holds a drawing. Most frames are not keyframes. A keyframe stays on screen, or **is held**, until the next keyframe on the same layer. If you draw on frames 1, 3 and 7, the drawing from frame 1 shows on frames 1 and 2, the one from frame 3 shows on frames 3 to 6, and the one from frame 7 shows from frame 7 onward.

This is how traditional animators work: a drawing held for two frames is "on twos", and you only draw the frames that change. See [Timeline and Animation]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}) for how to add, move, duplicate and hold keyframes.

### Layers {#layers}

A project is a stack of **layers**, like sheets of transparent paper. Each layer has its own row of keyframes in the Timeline. Layers higher in the Timeline list are drawn in front of lower ones. Put things that move separately on separate layers: a background on one layer, a character on another, rough sketches on a third that you hide later.

Pencil2D has four layer types:

| Layer type | Holds |
|---|---|
| Bitmap | Pixel drawings |
| Vector | Line drawings stored as editable curves |
| Camera | The camera position, rotation and zoom over time |
| Sound | Audio clips |

See [Layers]({{ '/doc/manual/layers.html#layer-types' | relative_url }}) for adding, ordering and managing layers.

### Bitmap or vector? {#bitmap-vs-vector}

**Bitmap layers** store each drawing as pixels, like a painting program. They support every tool, including the feathered **Brush** and pixel smudging, and they are the best choice for most work: sketching, cleanup, coloring and painted backgrounds.

**Vector layers** store strokes as curves. Strokes stay sharp at any zoom and can be edited after you draw them. Their colors are linked to the palette, so replacing a palette color recolors every stroke that uses it (see [vector colors]({{ '/doc/manual/color.html#vector-colors' | relative_url }})). The Pencil2D team says the vector engine is still a work in progress and doesn't always behave as expected, so use bitmap layers for serious projects.

> **Tip:** If you aren't sure which to use, use a bitmap layer.

### The default project {#default-project}

A new project in Pencil2D v0.7.2 contains:

- A **Camera Layer** at the bottom, with a keyframe at frame 1 and an 800 × 600 camera field.
- A **Bitmap Layer** above it, with an empty keyframe at frame 1. This layer is selected, so you can start drawing right away.
- The default color palette and a playback speed of 12 fps.

Earlier versions also added a vector layer. Since v0.7.0 it is no longer included, but you can add one with **Layer → New Vector Layer**. To start every new project with your own layers, camera size or palette, save a project as a preset and make it the default. See [Presets]({{ '/doc/manual/projects.html#presets' | relative_url }}).

A project always has at least one camera layer. Pencil2D doesn't let you delete the last one.

{% include series-nav.html series=site.data.manual %}
