---
layout: page
title: FAQ
tagline: Frequently Asked Questions
comments: true
---

Quick answers to the questions people ask most about Pencil2D 0.7.2. Each answer links to the
[User's Manual]({{ '/doc/manual/' | relative_url }}) for the full details. If your question isn't here, ask on the
[forum](https://discuss.pencil2d.org/) or suggest it in the comments below.

> **Note:** On macOS, press <kbd>Cmd</kbd> wherever this page says <kbd>Ctrl</kbd>, and
> <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>. **Edit → Preferences** is under the
> **Pencil2D** app menu on macOS.

{% include toc.html %}

## Installing and running {#installing}

### Which operating systems does Pencil2D run on? {#supported-systems}

Pencil2D 0.7.2 is available for:

- **Windows 7 or later**, 64-bit and 32-bit.
- **macOS 10.14 or later.** The download is an Intel app; on Apple Silicon Macs it runs through
  Rosetta 2.
- **Linux**, as a 64-bit or 32-bit AppImage for Ubuntu 16.04 or newer (or a distribution of the
  same age), and through Flatpak, Arch, Debian/Ubuntu and Fedora packages.
- **FreeBSD**, as a package or port.

Legacy builds without security fixes exist for older systems: 0.7.0 for macOS 10.7–10.13 and
0.6.6 for Windows XP and Vista. Everything is on the [download page]({{ '/download/' | relative_url }}); see also
[Installing Pencil2D]({{ '/doc/manual/getting-started.html#install' | relative_url }}).

### Pencil2D won't start, or says a .dll file is missing {#wont-start}

- **Windows:** Pencil2D comes as a ZIP file. Right-click it, choose **Extract All…**, and run
  `pencil2d.exe` from the extracted folder; running it from inside the ZIP causes errors such as
  *Qt5Widgets.dll was not found*. If Windows blocks the download, follow
  [How to Train Your Pencil2D]({{ '/doc/how-to-train-your-pencil2d.html' | relative_url }}).
- **macOS:** 0.7.2 is a DMG notarized by Apple, so it opens normally once you drag it into
  **Applications**. For older or nightly builds, right-click the app and choose **Open**.

For *MSVCP140.dll* and other messages, see the
[troubleshooting list on the download page]({{ '/download/#troubleshooting' | relative_url }}).

### How do I change the language? {#language}

Go to **Edit → Preferences → General** and choose a language in the **Language** box. Restart
Pencil2D for the change to take effect. See [Preferences]({{ '/doc/manual/preferences.html#general' | relative_url }}).

### The icons are tiny or the text looks wrong on my high-resolution screen {#hidpi}

High-DPI scaling is still an [open issue](https://github.com/pencil2d/pencil/issues/597). This
**legacy workaround for Windows**, first shared by user Jeetman, still helps on some screens:

1. Right-click `pencil2d.exe` (or your Pencil2D shortcut) and choose **Properties**.
2. Open the **Compatibility** tab and click **Change high DPI settings**.
3. Tick **Override high DPI scaling behavior** and set **Scaling performed by** to **System**.
4. Click **OK**, then **Apply**, and start Pencil2D again.

On Linux and macOS, try starting Pencil2D with the environment variable `QT_SCALE_FACTOR=1.5`.
<!-- VERIFY: QT_SCALE_FACTOR is standard Qt 5 behavior, not tested against the 0.7.2 release builds -->

### What are nightly builds? {#nightly-builds}

[Nightly builds]({{ '/download/nightly/' | relative_url }}) are test versions built automatically from the latest
development code. They have fixes and features before a release, but may also have new bugs, so
keep backups if you use one for real work.

## Getting started and learning to animate {#getting-started}

### I'm a beginner. How do I learn to animate? {#learn-to-animate}

Start with [Getting Started]({{ '/doc/manual/getting-started.html#first-animation' | relative_url }}), which walks you
through a short first animation, then try the lessons in the [Classroom Course]({{ '/doc/course/' | relative_url }}).
Resources shared by other users on our forum:

- [Some basic advice to get started](https://discuss.pencil2d.org/t/1074/2)
- [A collaborative list of learning resources](https://discuss.pencil2d.org/t/1090)
- [An essential animation reading list](https://discuss.pencil2d.org/t/559)
- Community video tutorials on the [tutorials page]({{ '/doc/tutorials.html' | relative_url }})

### Should I use a bitmap layer or a vector layer? {#bitmap-or-vector}

Use **bitmap layers**. They are the default in new projects and support every tool. Vector layers
still exist, but the vector engine is a work in progress and doesn't always behave as expected,
so avoid it for serious projects for now. See [Layer types]({{ '/doc/manual/layers.html#layer-types' | relative_url }})
and [Key concepts]({{ '/doc/manual/getting-started.html#key-concepts' | relative_url }}).

### What is the difference between a frame and a keyframe? {#frame-vs-keyframe}

A keyframe holds a drawing, which stays on screen until the next keyframe on the same layer. Add
one with <kbd>F7</kbd> (**Add Frame**). See [Keyframes]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}).

## Drawing and tools {#drawing}

### Why can't I draw? {#cant-draw}

Check these, most common first:

- **The layer is hidden.** Pencil2D shows *"You are trying to modify a hidden layer!"* Click the
  layer's eye icon in the timeline to show it, or select another layer.
- **A camera or sound layer is selected.** Drawing tools only work on bitmap and vector layers.
  Click a bitmap layer in the timeline.
- **The wrong tool is active.** The Hand, Move, Select and Eyedropper tools don't draw. Press
  <kbd>N</kbd> for the Pencil or <kbd>B</kbd> for the Brush.
- **You're using the Pencil on a vector layer.** On vector layers the Pencil draws invisible
  guide lines for filling. Use the Pen, or turn on **View → Show Invisible Lines** to see them.
- **The color or the layer is transparent.** Check the alpha value in the
  [Color Inspector]({{ '/doc/manual/color.html#color-inspector' | relative_url }}), and check
  **Layer → Layer / Keyframe opacity**.

The status bar at the bottom of the window shows a short hint for the active tool. See
[Tools]({{ '/doc/manual/tools.html' | relative_url }}) and [Layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}).

### I drew on a new frame, but an earlier drawing changed {#drew-on-previous-key}

When you draw on a frame that has no keyframe, Pencil2D by default draws on the previous
keyframe, the one being held on screen. To change this, go to
**Edit → Preferences → Timeline** and under **When drawing on an empty frame:** choose
**Create a new (blank) key-frame** or **Duplicate the previous key-frame**. The setting applies
to the Pencil, Pen, Polyline, Bucket and Brush tools; the Eraser never creates a keyframe. See
[Preferences]({{ '/doc/manual/preferences.html#timeline' | relative_url }}). To start a new drawing without changing the
setting, press <kbd>F7</kbd> first.

### My lines look pixelated or jagged. How do I get smooth lines? {#smooth-lines}

- **Pick a smooth tool.** The Pencil draws hard-edged lines on purpose. The
  [Pen]({{ '/doc/manual/tools.html#pen' | relative_url }}) has an **Anti-Aliasing** option (on by default), and the
  [Brush]({{ '/doc/manual/tools.html#brush' | relative_url }}) has soft edges set by **Feather**.
- **Keep canvas antialiasing on:** **Edit → Preferences → General → Antialiasing**.
- **Draw at your final size.** Bitmap layers are made of pixels, so zooming in past 100% shows
  them. Set the [camera size](#canvas-size) to your output resolution before you start, and
  don't export larger than the camera, which enlarges the pixels.
- **For steadier strokes**, use the [Stabilizer]({{ '/doc/manual/tools.html#stabilizer' | relative_url }}).

### Does Pencil2D have a shape tool? {#shape-tool}

There is no rectangle or ellipse tool. For straight lines and polygons, use the
[Polyline tool]({{ '/doc/manual/tools.html#polyline' | relative_url }}) (<kbd>Y</kbd>): click to place points, then
double-click or press <kbd>Enter</kbd> to finish, or <kbd>Esc</kbd> to cancel. Turn on
**Bézier** for curved segments.

### Does Pencil2D have a text tool? {#text-tool}

Not yet ([feature request](https://github.com/pencil2d/pencil/issues/1079)). Make text, or precise
shapes, in another program, save them as a PNG with a transparent background, and bring them in
with **File → Import → Image…** ([Importing images]({{ '/doc/manual/import-export.html#import-image' | relative_url }})).

### The Bucket tool won't fill an area, or fills too much {#bucket-fill}

- **Close the gaps.** A bitmap fill spreads through any gap in the lines. Zoom in and close it.
- **Filling right up to soft lines.** Tick **Expand fill** (on by default, 2 px) to push the fill
  under the edge of the line, or tick **Color tolerance** and raise it.
- **Line art on a separate layer.** Set **Reference** to **All layers** so the fill uses the lines
  on the other layers as borders, while painting on the current layer.
- **Filling underneath the lines.** Set **Blend mode** to **Behind**.

See the [Bucket tool]({{ '/doc/manual/tools.html#bucket' | relative_url }}) for every option.

### Can I copy and paste part of a drawing into another frame, in place? {#copy-paste-in-place}

Yes. Select the area with the Select tool (<kbd>V</kbd>) and press <kbd>Ctrl</kbd>+<kbd>C</kbd>
(or <kbd>Ctrl</kbd>+<kbd>X</kbd> to cut). Go to another keyframe, or create one with
<kbd>F7</kbd>, and press <kbd>Ctrl</kbd>+<kbd>V</kbd>: the artwork is pasted at the same position.
**Edit → Paste from Previous Keyframe** (<kbd>Ctrl</kbd>+<kbd>←</kbd>) copies the previous
keyframe, or the selected area of it, onto the current keyframe in one step. See
[The clipboard]({{ '/doc/manual/selection.html#clipboard' | relative_url }}).

### How do I flip or mirror a drawing? {#flip}

- **To flip only your view** (to check a drawing, as animators do with a mirror), use
  **View → Horizontal Flip** (<kbd>Shift</kbd>+<kbd>H</kbd>) or **View → Vertical Flip**
  (<kbd>Shift</kbd>+<kbd>V</kbd>). The artwork doesn't change. See
  [Flipping the view]({{ '/doc/manual/canvas.html#flip' | relative_url }}).
- **To flip the artwork itself**, select it with the Select tool (<kbd>V</kbd>) and use
  **Edit → Selection → Flip X** or **Flip Y**. These have no default shortcut; you can assign
  one to **Selection: Horizontal Flip** and **Selection: Vertical Flip** in
  **Edit → Preferences → Shortcuts**. See [Transforming]({{ '/doc/manual/selection.html#transforming' | relative_url }}).

### I changed a color and a vector drawing changed color everywhere {#vector-color-linking}

On vector layers, strokes and fills are linked to palette swatches. When you change a swatch with
right-click → **Replace** in the Color Palette, every vector stroke that uses it changes too, on
every frame. To recolor only new strokes, **Add** a new swatch and draw with that. Bitmap layers
aren't affected. See [Vector colors]({{ '/doc/manual/color.html#vector-colors' | relative_url }}).

### How do I use a drawing tablet? Pressure isn't working {#tablet}

- Make sure **Pressure** is ticked in the Options panel for the tool you use. The Pencil,
  Eraser, Pen and Brush support it; the Polyline and Smudge tools don't.
- Install the latest driver from your tablet's manufacturer, then restart Pencil2D.
- **Huion tablets** may lag or draw uneven strokes. Try disabling "linear optimizer" in the
  tablet's driver settings ([details](https://discuss.pencil2d.org/t/difficulty-with-huion-tablet/1369/9)).
- **On Windows**, panning with the pen's middle or right button can make Pencil2D misbehave. Hold
  <kbd>Space</kbd> and drag with the pen tip instead. If it has already happened, click once on
  the canvas with a mouse.

More in [Common tool options]({{ '/doc/manual/tools.html#common-options' | relative_url }}).

### My panels disappeared. How do I get the layout back? {#reset-layout}

Choose **Windows → Reset Windows** to put every panel back in its default place. To show a
single panel, pick it in the **Windows** menu. If you can't move or close panels, turn off
**Windows → Lock Windows**. Toolbars and the status bar are under **Windows → Toolbars** and
**Windows → Status Bar**. See [Arranging windows]({{ '/doc/manual/interface.html#arranging-windows' | relative_url }}).

### How do I reset preferences? {#reset-preferences}

There is no single reset button. **Tools → Reset to default** resets all tool settings,
**Edit → Preferences → Shortcuts → Restore Default Shortcuts** resets shortcuts, and
**Windows → Reset Windows** resets the panel layout. To reset everything, close Pencil2D and delete its settings. On Windows, delete the registry key
`HKEY_CURRENT_USER\Software\Pencil\Pencil`. On Linux, delete `~/.config/Pencil/Pencil.conf`. On
macOS, delete `~/Library/Preferences/com.pencil.Pencil.plist`.
<!-- VERIFY: paths derived from QSettings("Pencil", "Pencil") and Qt's default locations; the macOS file name and the Flatpak location (probably under ~/.var/app/org.pencil2d.Pencil2D/config/) were not tested -->

## Animation and timeline {#animation}

### How do I change the frame rate (FPS)? {#fps}

Use the **fps** box in the Timeline's playback controls (tooltip: *Frames per second*). It
accepts 1 to 90, is saved with the project, and is used for both playback and export. New
projects start at 12 fps. Changing it doesn't move your keyframes; each frame just gets shorter
or longer. See [Frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}).

### How do I animate on twos? {#on-twos}

A keyframe stays on screen until the next one, so put your drawings on every second frame (frames
1, 3, 5, …) and each one lasts two frames. To convert an animation made on ones, select its
keyframes in the timeline and choose **Animation → Timeline Selection → Add Exposure**
(<kbd>Ctrl</kbd>+<kbd>+</kbd>). Each selected keyframe gets one more frame. See
[Exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}).

### How do I make the timeline longer? I can only see 240 frames {#timeline-length}

The timeline extends itself when you add keyframes near its end, so you don't normally need to
do anything. To set the displayed length yourself, go to **Edit → Preferences → Timeline** and
change **Timeline length:** (1 to 9999 frames, default 240). The timeline stops at frame 9999,
but for long films one project per shot works better; see [Performance](#memory) and
[The timeline]({{ '/doc/manual/timeline.html#anatomy' | relative_url }}).

### How do I copy frames to another project? {#copy-frames-between-projects}

Open the project you want to copy into, then choose **File → Import → Layers from Project
file…**. Select the other project, select the layers you want and click **Import layers**. Each
layer arrives with all of its keyframes. Within one project, you can copy keyframes by
selecting them in the timeline and pressing <kbd>Ctrl</kbd>+<kbd>C</kbd> and
<kbd>Ctrl</kbd>+<kbd>V</kbd>. See [Copying frames]({{ '/doc/manual/timeline.html#copy-paste' | relative_url }}).

## Camera {#camera}

### How do I change the size of the canvas? {#canvas-size}

The canvas is infinite. The rectangle in the middle is the **camera**, the area that gets
exported. To change its size, double-click the camera layer's name in the timeline. The
**Camera Properties** dialog opens, and you can set **Camera size:** there. For MP4 export, use
even numbers, such as 1920 × 1080.

To use a different size for every new project, set up a project the way you like, then save it
as a preset with the **+** button in **Edit → Preferences → Files** and click **Make Default**.
See [Camera size]({{ '/doc/manual/camera.html#camera-size' | relative_url }}) and
[Presets]({{ '/doc/manual/projects.html#presets' | relative_url }}).

### Part of my drawing is missing from the export {#outside-camera}

Only what's inside the camera rectangle is exported, and hidden layers are skipped. Move or
resize the camera so it covers your drawing, and make sure every layer you want is visible. If
the project has more than one camera layer, choose the right one in the **Camera** box of the
export dialog.

### How do I animate the camera (pan, zoom, rotate)? {#animate-camera}

Select the camera layer, add keyframes where the camera should change, and adjust the camera on
each keyframe with the Move tool (<kbd>M</kbd>): drag inside it to move it, drag a corner to
scale it, and drag the round handle to rotate it. Pencil2D moves the camera smoothly between
keyframes. Right-click a camera keyframe to choose an easing, and tick **Show path** in the
Options panel to see and adjust the path. See [Camera]({{ '/doc/manual/camera.html#camera-tool' | relative_url }}) and
[Easing]({{ '/doc/manual/camera.html#easing' | relative_url }}).

## Sound {#sound}

### How do I import sound? {#import-sound}

1. Move the playhead to the frame where the sound should start.
2. Choose **File → Import → Sound…**. If the current layer isn't a sound layer, Pencil2D offers
   to create one; click **Create sound layer** and give it a name. (With a sound layer already
   selected, you can also press <kbd>F7</kbd>.)
3. Pick the sound file. The clip appears on the sound layer as a bar as long as the sound.

If a clip already starts at that frame, the new one goes on the next free frame. To use the
soundtrack of a video file, choose **File → Import → Movie Audio…** instead. The timeline doesn't
show a waveform. See [Adding sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}).

### Which sound formats are supported? {#sound-formats}

WAV, MP3, WMA, OGG, FLAC, Opus, AIFF, AAC and CAF. Pencil2D converts every imported sound to WAV
using the FFmpeg program included with it. Movie export only works with fewer than 63 sound
clips in the whole project; Pencil2D warns you when you reach the limit. See
[Formats]({{ '/doc/manual/sound.html#formats' | relative_url }}).

### I imported a sound but I can't hear it {#no-sound}

- Check the **Sound on/off** button in the timeline's playback controls, and your system volume.
- Clips imported with Pencil2D versions older than 0.7.0 may play cut short on Windows. Delete
  them and import them again.
- In large projects, the sound can seem to lag behind the pictures during playback in the editor.
  Exported videos are not affected.
  <!-- VERIFY: whether this 0.7.0 known issue (#1567, #1179) still applies to 0.7.2; the 0.7.2 release notes no longer list it. --> To hear the sound while you drag the playhead, turn on **Sound scrub on/off** in the
  playback controls.

If the problem is in the exported video, see *Audio issues* in the
[Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

### My sound is out of sync after exporting {#sound-sync}

Export timing follows the frames and the project's frame rate, so it is usually more accurate
than playback in the editor. If you changed the fps after placing sounds, check the timing again.
To shift the soundtrack of a finished video, use a free editor such as
[Shotcut](https://shotcut.org), [Kdenlive](https://kdenlive.org/) or
[DaVinci Resolve](https://www.blackmagicdesign.com/products/davinciresolve/).

## Importing and exporting {#import-export}

### Can I import a video? {#import-video}

Yes. Select a bitmap layer, move the playhead to where the video should start, and choose
**File → Import → Movie Video…**. Pencil2D turns the video into one keyframe per frame at the
project's frame rate, and warns you before importing a large number of frames. The video must
fit before frame 9999. Animated GIF and WebP files are imported with
**File → Import → Animated Image…**. See [Importing video]({{ '/doc/manual/import-export.html#import-movie' | relative_url }}).

### How do I export an MP4 for YouTube or social media? {#export-mp4}

1. Set the [camera size](#canvas-size) to your target resolution, for example 1920 × 1080 for a
   landscape video or 1080 × 1920 for a vertical one.
2. Choose **File → Export → Movie…**.
3. Click **Browse…** and save as `.mp4` (the default).
4. Check **Resolution** (MP4 needs even numbers) and the **Start Frame** and **End Frame**.
5. Click **OK**.

Visible sound layers are included automatically. See
[Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}). If the export fails, see the
[Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

### Why is my exported video shorter or longer than expected? {#export-length}

- **The end is cut off.** **End Frame** starts at the last keyframe (sound clips don't count), so a
  drawing on the last keyframe appears for only one frame. Raise **End Frame** in the export dialog, or tick
  **To the end of sound clips** to export until the sound ends.
- **It runs too long.** A stray keyframe far down the timeline, on any layer including the
  camera layer, extends **End Frame**. Delete it or lower **End Frame**.
- **It plays too fast or too slow.** The video uses the project's [frame rate](#fps).

### How do I export an animated GIF? {#export-gif}

Choose **File → Export → Animated GIF…**, click **Browse…** to choose where to save it, set the
resolution and frame range, tick **Loop** if it should repeat, and click **OK**. GIF export
doesn't support transparency. See [Exporting a GIF]({{ '/doc/manual/import-export.html#export-gif' | relative_url }}).

### How do I export with a transparent background? {#transparent-background}

Hide or delete any layer you used as a background; hidden layers aren't exported. Then:

- **Images:** use **File → Export → Image…** or **Image Sequence…**, choose PNG, WEBP or TIFF
  as the **Format**, and tick **Transparency**. JPG and BMP don't support it.
- **Video:** use **File → Export → Movie…**, save as `.webm` or `.apng`, and tick
  **Transparency**. MP4, AVI and GIF can't be transparent.

See [Exporting an image sequence]({{ '/doc/manual/import-export.html#export-image-sequence' | relative_url }}).

## Files, saving and crashes {#files}

### What are .pclx and .pcl files? {#pclx-pcl}

**.pclx** is the Pencil2D project format; use it. It is a ZIP archive containing `main.xml` (the
project structure) and a `data` folder with one PNG file per bitmap keyframe, a `.vec` file per
vector keyframe, the palette (`palette.xml`) and copies of your imported sounds. To look inside,
make a copy and rename the copy's extension to `.zip`.

**.pcl** is the legacy format. The `.pcl` file only holds the project structure; the drawings are
in a folder next to it named `yourfile.pcl.data`. If you move or send a `.pcl` project, keep both
together. See [File formats]({{ '/doc/manual/projects.html#file-formats' | relative_url }}).

### How do I turn on autosave? {#autosave}

Go to **Edit → Preferences → Files** and, under **Autosave documents**, tick
**Enable autosave**. **Number of modifications before autosaving:** sets how often it saves
(4 to 8192 changes, default 15); a change is a stroke or an action such as moving or clearing a
frame. Autosave is off by default.

Autosave only works after you have saved the project once. Until then, it shows an
**AutoSave Reminder** asking you to save. See [Autosave]({{ '/doc/manual/projects.html#autosave' | relative_url }}).

### Where are autosaves and backups stored? {#backup-location}

- **Autosave** saves over your project file, exactly like **File → Save**. It doesn't create a
  separate file.
- **While saving a .pclx**, Pencil2D copies the previous version to a file such as
  `yourfile.backup1.pclx` next to your project, and deletes it once the save succeeds. If you
  find one, a save failed, and it holds your previous version.
- **Working files** for open projects are kept in a `Pencil2D` folder in your system's temporary
  folder. **Help → Open Temporary Directory** opens it. Don't change anything there.

Pencil2D doesn't keep version history, so save numbered copies at milestones
(`shot01_001.pclx`, `shot01_002.pclx`, …) with **File → Save As…**.

### Pencil2D crashed. Can I get my work back? {#crash-recovery}

When Pencil2D starts after closing unexpectedly, it may show a **Restore project** dialog. Click
**Open** to recover the project, then save it right away under a new name. Recovery can only
restore what was written to disk, so it's no substitute for saving often and turning on
[autosave](#autosave). See [Crash recovery]({{ '/doc/manual/projects.html#recovery' | relative_url }}).

If a saved file won't open or looks damaged, follow the
[Project File Recovery Guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }}). When you report a crash,
use the **Copy to Clipboard** button in the error dialog to include its details.

## Performance {#performance}

### Drawing lags or my lines trail behind the pen {#stroke-lag}

The Pencil, Pen and Brush use the **Strong** stabilizer by default, which smooths lines by
making them follow the cursor with a delay. Set **Stabilizer** to **Simple** or **None** in the
Options panel for a more direct feel. See [Stabilizer]({{ '/doc/manual/tools.html#stabilizer' | relative_url }}).

### Pencil2D gets slow or crashes in big projects {#memory}

Drawings you haven't saved yet are kept in memory, so long projects with many layers can use a
lot of it. To stay safe:

- **Save early and often.** After a save, Pencil2D can release frames it isn't showing.
- **Split long animations into one project per shot or scene**, then join the exported videos in
  a video editor. A damaged file then only costs you one shot.
- **Keep the camera at the size you need.** Larger frames use more memory.
- **Adjust the memory budget.** **Edit → Preferences → General → Memory Cache Budget** sets how
  much memory Pencil2D uses for frames (default 1024 MB).

See [Projects and Files]({{ '/doc/manual/projects.html' | relative_url }}) and
[Preferences]({{ '/doc/manual/preferences.html#general' | relative_url }}).

## Contributing and support {#support}

### Is Pencil2D really free? Can I use it for commercial work? {#license}

Yes. Pencil2D is free and open source under the
[GNU General Public License, version 2](https://www.gnu.org/licenses/gpl-2.0.html). You can use it
for any purpose, including commercial projects.

### I found a bug. How do I report it? {#report-bug}

First try the latest [nightly build](#nightly-builds) to see whether it's already fixed. Then use
**Help → Report a Bug**, which opens the
[issue tracker](https://github.com/pencil2d/pencil/issues). Search it for your problem, and if
it's new, open an issue with your Pencil2D version (**Help → About**), your operating system, the
steps to reproduce the bug, and any error details. For help that isn't a bug, ask on the
[forum](https://discuss.pencil2d.org/) or [Discord](https://discord.gg/8FxdV2g).

### How can I help Pencil2D? {#contribute}

Pencil2D is made by volunteers in their spare time. You can help by reporting bugs, testing
nightly builds, translating, writing tutorials, answering questions on the forum, or
contributing code (C++ and Qt). See the [Contribute page]({{ '/contribute/' | relative_url }}) and the
[community page]({{ '/community/' | relative_url }}).

---

Some of the original FAQ answers were contributed by users Piggy, chchwy, Jeetman, morr and
josemoreno.
