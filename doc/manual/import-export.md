---
layout: page
title: Importing and Exporting
tagline: Bringing images, video, sound and palettes in, and getting images, movies and GIFs out
comments: false
---

This chapter covers every item in the **File → Import** and **File → Export** menus: how to bring
pictures, image sequences, animated GIFs, video, sound, palettes and layers from other projects into
your animation, and how to export single images, image sequences, movies and animated GIFs. Read
it when you want to trace over reference material, reuse old work, or share a finished animation.

On macOS, press <kbd>Cmd</kbd> wherever this page says <kbd>Ctrl</kbd>.

{% include toc.html %}

## Before You Import {#before-you-import}

Most imports put pictures into the **current layer** at the **current frame** (where the playhead
is on the timeline). Before you import:

- Select a **bitmap layer** for images, image sequences, animated images and movie video. You
  can't import pictures into a vector, camera or sound layer; Pencil2D shows an error message
  instead. See [Layers]({{ '/doc/manual/layers.html#layer-types' | relative_url }}).
- Make sure the layer is visible. Pencil2D won't import into a hidden layer.
- Move the playhead to the frame where the first picture should go.

If the current frame already has a keyframe, the imported picture is pasted into that drawing
rather than replacing it. If there is no keyframe there, Pencil2D creates one.

Imported pictures keep their original pixel size. Pencil2D doesn't scale them to fit the camera,
so a large photo can extend well past the camera frame. Use the
[Select and Move tools]({{ '/doc/manual/selection.html#transforming' | relative_url }}) to resize it afterwards.

Pencil2D 0.7.2 doesn't support dragging files onto the window to import them. You can, however,
paste an image copied from another program; see [the clipboard]({{ '/doc/manual/selection.html#clipboard' | relative_url }}).

## Import Position {#import-position}

When you import an image, an image sequence, a predefined set or an animated image, Pencil2D asks
where to put it. The **Import position** dialog has one setting, **Import image/s relative to:**.
The picture is centered on the point you choose:

| Option | Where the picture's center goes |
|---|---|
| **Center of current view** | The middle of the canvas area you're looking at right now |
| **Center of canvas (0,0)** | The origin of the canvas, which is the camera's starting position in a new project |
| **Center of camera, current frame** | The camera's center at the current frame; every picture in a sequence uses this same spot |
| **Center of camera, follow camera** | The camera's center at the frame each picture lands on, so pictures follow a moving camera |

The two camera options are only available when there is a camera layer below the current layer
in the layer list. Pencil2D remembers your choice for next time.

<!-- SCREENSHOT: The "Import position" dialog with the "Import image/s relative to:" drop-down open, showing all four options -->

> **Tip:** Use **Center of camera, follow camera** when you import reference frames into a scene
> where the camera pans or zooms. Each frame then lines up with the camera at its own frame.

## Image {#import-image}

To import a single picture, choose **File → Import → Image...**, pick a file and click **Open**,
then choose an [import position](#import-position) and click **OK**.

Supported formats: PNG, JPG/JPEG, BMP, TIFF (.tif, .tiff) and WebP.

The picture goes into the current frame of the current bitmap layer. After the import, the
playhead moves forward one frame, so you can import the next picture straight away.

## Image Sequence {#import-image-sequence}

An image sequence is a set of numbered pictures, one per frame, such as frames exported from
another program or a scanned pencil test.

To import one:

1. Select a bitmap layer and move the playhead to the frame where the sequence should start.
2. Choose **File → Import → Image Sequence...**.
3. In the **Import image sequence** dialog, click **Browse...** and select all the pictures you
   want. Hold <kbd>Ctrl</kbd> or <kbd>Shift</kbd> to select several files. The selected files
   appear in the **File** box.
4. Set **Import an image every # frame**: `1` puts a picture on every frame, `2` on every second
   frame (animating "on twos"), and so on up to `64`.
5. Click **OK**, choose an [import position](#import-position), and click **OK** again.

A progress window, **Importing image sequence...**, appears while the pictures load. Click
**Abort** to stop; pictures already imported stay in place.

<!-- SCREENSHOT: The "Import image sequence" dialog with several files listed in the File box and "Import an image every # frame" set to 2 -->

> **Note:** Pencil2D imports the files in the order the file dialog hands them over, which is the
> order shown in the **File** box. It doesn't sort them by name. If your frames come in out of
> order, use [Image Predefined set](#import-predefined-set) instead, which places each picture by
> the number in its file name.

## Image Predefined Set {#import-predefined-set}

**File → Import → Image Predefined set...** imports a numbered set of pictures and puts each
one on the frame that matches the number in its file name. For example, `Joe001.png` goes to
frame 1, `Joe005.png` to frame 5 and `Joe012.png` to frame 12. Gaps in the numbering become
gaps between keyframes, so you can keep the timing you planned elsewhere.

To use it:

1. Choose **File → Import → Image Predefined set...**. The **Import predefined keyframe set**
   dialog opens.
2. Click **Browse...** and select **one** picture from the set.
3. Pencil2D looks in the same folder for every file with the same name prefix, the same number of
   digits and the same extension. The preview table lists each file under **Files** and the frame
   it will go to under **KeyFrame Pos**.
4. Click **OK**, choose an [import position](#import-position), and click **OK** again.

Pencil2D creates a **new bitmap layer** named after the prefix (`Joe` in the example above) and
imports the pictures into it, so you don't need to select a layer first.

File names must end in a number just before the extension, and that number must be 1 or higher.
A file numbered 0 (such as `Joe000.png`) is skipped. If the file you picked doesn't fit the
pattern, Pencil2D shows an **Invalid path** message and the **OK** button stays disabled.

## Animated GIF and WebP {#import-gif}

To import an animated GIF or animated WebP as individual frames:

1. Select a bitmap layer and move the playhead to the first frame.
2. Choose **File → Import → Animated Image...**.
3. In the **Import animated image** dialog, click **Browse...** and choose a `.gif` or `.webp`
   file.
4. Set **Import an image every # frame** (1–64), then click **OK**.
5. Choose an [import position](#import-position) and click **OK**.

Each frame of the animation becomes a keyframe, spaced by the number of frames you chose. The
progress window **Importing Animated Image...** has an **Abort** button for large files.

If the file is a still image rather than an animation, Pencil2D reports that the selected image
has a format that does not support animation.

> **Note:** In 0.7.2 the choice in the **Import position** dialog is not applied to animated
> images. Where the frames land depends on how the canvas view is panned and zoomed, so you may
> need to move them afterwards.
<!-- VERIFY: Editor::importAnimatedImage() ignores ImportImageConfig (settled) and positions frames from view()->getView().dx()/dy(); confirm in the app where frames actually land. -->

## Movie Video {#import-movie}

**File → Import → Movie Video...** turns a video clip into a series of bitmap keyframes, one per
frame. It's useful for rotoscoping or for tracing live-action reference.

To import a video:

1. Select a bitmap layer and move the playhead to the frame where the clip should start.
2. Choose **File → Import → Movie Video...** and pick the file.
3. Wait while the **Importing movie...** progress window works. Click **Abort** to cancel.

Supported file types: AVI, MPEG (.mpg, .mpeg), MOV, MP4, MKV, OGV, SWF, FLV, WebM and WMV.

What to expect:

- Pencil2D uses [FFmpeg](#ffmpeg) to extract the frames at your project's
  [frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}). A 10-second clip in a 12 fps project becomes
  120 frames. Set the frame rate you want **before** importing.
- Each frame is centered on the camera at the frame it lands on (the same as
  **Center of camera, follow camera**). No position dialog is shown.
- If the clip would produce more than 200 frames, Pencil2D warns you that this could take some
  time and asks whether to proceed.
- A project can hold up to 9999 frames. If the clip would run past frame 9999, the import stops
  with **Imported movie too big!** Shorten the clip, or import it from an earlier frame.
- Only the picture is imported. To bring in the clip's soundtrack, use
  [Movie Audio](#import-sound).

> **Tip:** Every video frame becomes a full bitmap keyframe, which makes projects large and slow.
> Trim the clip to just the part you need in a video editor first, and consider a lower project
> frame rate for reference footage.

## Sound and Movie Audio {#import-sound}

**File → Import → Sound...** adds a sound clip at the current frame. Supported formats: WAV,
MP3, WMA, OGG, FLAC, Opus, AIFF, AAC and CAF.

**File → Import → Movie Audio...** does the same, but lets you pick a video file (the same types
as [Movie Video](#import-movie)) and imports only its soundtrack.

Both need a sound layer to be selected. If the current layer isn't a sound layer, Pencil2D offers
to create one: click **Create sound layer**, type a name, and click **OK**. Placing, moving and
playing clips is covered in [Sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}).

## Palette {#import-palette}

Two items at the bottom of the **Import** menu load colors from a palette file. Both accept
Pencil2D palettes (`.xml`) and GIMP palettes (`.gpl`).

- **Replace Palette...** removes the current palette and loads the file in its place. If your
  vector drawings use colors from the current palette, Pencil2D first warns that the colors in
  strokes will be altered and asks you to confirm with **Open Palette**.
- **Append to Palette...** adds the file's colors to the end of the current palette.

See [Color and Palettes]({{ '/doc/manual/color.html#palette' | relative_url }}) for working with palettes.

## Layers from Another Project {#import-layers}

**File → Import → Layers from Project file...** copies layers from another Pencil2D project into
the one you have open. Use it to reuse a background, a character or a sound track across scenes.

1. Choose **File → Import → Layers from Project file...**.
2. Under **1. Select Project file:**, click **Select File** and open a `.pclx` or `.pcl` project.
3. Under **2. Select layers from file:**, click the layers you want. Hold <kbd>Ctrl</kbd> or
   <kbd>Shift</kbd> to select several.
4. Click **Import layers**. The layers are added on top of your layer list.
5. Import more layers if you like, then click **Close**.

Any layer type can be imported, including camera and sound layers, with all of its keyframes. If
a layer's name is already used in your project, Pencil2D gives the imported layer a new name. The
colors used by imported vector layers are added to the end of your palette so the drawings keep
their original colors.

<!-- SCREENSHOT: The "Import Layers from other *.pclx files" dialog with a project selected and two layers highlighted in the list -->

## Exporting: What Ends Up in the File {#what-gets-exported}

All exports render your animation **through a camera**. Only what is inside the camera frame is
exported, exactly as the camera sees it on each frame, including camera moves. Everything outside
the camera frame on the infinite canvas is left out. See [Camera]({{ '/doc/manual/camera.html' | relative_url }}).

- **Hidden layers are not exported.** Only a layer's own visibility (its eye icon) matters. The
  canvas's [layer visibility mode]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}) doesn't affect
  exports.
- Onion skins, overlays, grids and the camera border are never exported.
- The background is plain white, or transparent where the format allows it and you turn on
  **Transparency**. The canvas background you chose in Preferences is not exported.
- Movies and GIFs play at the project's [frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}).
  There is no separate frame rate setting in the export dialogs.

### Choosing a File Name {#export-file}

Every export dialog has a **File** box at the top. You can't type in it; click **Browse...** to
choose a folder and file name. The format of movie exports is chosen by the file type you pick
in this save dialog. Click **OK** to start the export, or **Cancel** to close the dialog.

### The Default Export Location {#export-location}

When you open a project with **File → Open**, or save one with **File → Save As**, Pencil2D sets
the default location of every export type to the project's folder, with the project's name as the
file name. For example, after opening `D:\Animations\walk.pclx`, a movie export suggests
`D:\Animations\walk.mp4`. After that, each export type remembers the last location you used.

If you haven't opened or saved a project through the file dialog yet, exports suggest your home
folder and the name `untitled`.

### Camera, Resolution and Range {#export-options}

The image, image sequence, movie and GIF export dialogs share these settings (the single-image
dialog has no range settings):

| Option | What it does | Default |
|---|---|---|
| **Camera** | Which camera layer to render through, if your project has several | The selected layer if it's a camera layer, otherwise the first camera layer |
| **Resolution** / **Width**, **Height** | Size of the exported pictures, in pixels | The selected camera's size |
| **Start Frame** | The first frame to export | 1 |
| **End Frame** | The last frame to export | The last keyframe in the project |
| **To the end of sound clips** | Sets **End Frame** to the frame where the last sound clip ends | Off |

The resolution follows the [camera size]({{ '/doc/manual/camera.html#camera-size' | relative_url }}) and resets when
you pick a different camera. You can enter any size: the camera view is scaled to fill it. If
the width and height aren't in the same proportion as the camera, the picture is **stretched**,
so change both by the same percentage. Exporting larger than the camera is useful for sharp
vector drawings; bitmap drawings just get scaled up.

> **Tip:** The default **End Frame** is the last *keyframe*, which is shown for one frame only.
> If your last drawing is held for several frames, raise **End Frame** to include them.

## Image {#export-image}

**File → Export → Image...** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd>) saves the frame
at the playhead as a single picture.

![The Export image dialog]({{ "/images/manual/export-image.png" | relative_url }})

| Option | What it does | Default |
|---|---|---|
| **Camera** | Camera layer to render through | See [above](#export-options) |
| **Resolution** | Width and height, 1 to 4096 pixels each | Camera size |
| **Format** | PNG, JPG, BMP, TIFF or WEBP | PNG |
| **Transparency** | Leaves the background transparent instead of white. Not available for JPG and BMP | Off |

Changing **Format** changes the file extension in the **File** box to match.

## Image Sequence {#export-image-sequence}

**File → Export → Image Sequence...** (<kbd>Ctrl</kbd>+<kbd>R</kbd>) saves every frame in a
range as a separate numbered picture. It has the same **Camera**, **Resolution**, **Format** and
**Transparency** options as [Image](#export-image), plus a **Range** section:

![The Export image sequence dialog]({{ "/images/manual/export-image-sequence.png" | relative_url }})

| Option | What it does | Default |
|---|---|---|
| **Start Frame**, **End Frame** | The frames to export | 1 to the last keyframe |
| **To the end of sound clips** | Extends **End Frame** to the end of the last sound clip | Off |
| **Export keyframes only** | Exports only the frames where the currently selected layer has a keyframe | Off |

**File names.** Pencil2D adds the frame number, padded to four digits, to the name you choose. If
you choose `walk.png`, the files are `walk0001.png`, `walk0002.png`, and so on. The number is
always the frame's position on the timeline, so exporting frames 10–20 gives `walk0010.png` to
`walk0020.png`, and **Export keyframes only** leaves gaps in the numbering.

A progress window, **Exporting image sequence...**, shows how far the export has got. Click
**Abort** to stop it.

> **Tip:** Image sequences are the most flexible way out of Pencil2D. Export PNG frames with
> **Transparency** on, then combine them in a video editor or compositing program when you
> need a format or quality setting that the movie export doesn't offer.

## Movie {#export-movie}

**File → Export → Movie...** renders your animation to a video file using [FFmpeg](#ffmpeg).

To export a movie:

1. Choose **File → Export → Movie...**.
2. Click **Browse...**, choose where to save, and pick a file type: **MP4**, **AVI**, **WebM**
   or **APNG**. If the name doesn't end in one of these extensions, Pencil2D adds `.mp4`.
3. Check **Camera**, **Resolution** and **Range**, and the options below.
4. Click **OK**. The **Exporting movie** window shows two progress bars and the current step.
   Click **Cancel** to stop.
5. When the export finishes, Pencil2D asks **Finished. Open movie now?**

![The Export Movie dialog]({{ "/images/manual/export-movie.png" | relative_url }})

| Option | What it does | Default |
|---|---|---|
| **Width**, **Height** | Video size in pixels, up to 9999 | Camera size |
| **Start Frame**, **End Frame** | The frames to include | 1 to the last keyframe |
| **To the end of sound clips** | Extends **End Frame** to the end of the last sound clip | Off |
| **Loop** | Makes the animation repeat forever. APNG only in this dialog | Off, unless the dialog opens with an `.apng` file name |
| **Transparency** (under **Exporter Settings**) | Keeps the background transparent. WebM and APNG only | Off |

Options that don't apply to the chosen file type are grayed out.

### Formats {#movie-formats}

| Format | Sound | Transparency | Loop | Notes |
|---|---|---|---|---|
| MP4 | Yes | No | No | The default. Width and height must be even numbers |
| AVI | Yes | No | No | |
| WebM | Yes | Yes | No | |
| APNG | No | Yes | Yes | Animated PNG; plays in most web browsers |

**Odd sizes and MP4.** The MP4 format can't use an odd width or height. If either one is odd,
the dialog shows *The MP4 format does not support odd width* (or *height*) and the **OK**
button is disabled. Add or subtract one pixel, or choose another format.

### Sound in Movies {#movie-sound}

Sound clips on visible sound layers are mixed into MP4, AVI and WebM files and trimmed to the
exported range. Clips on hidden sound layers are left out. For more, see
[Sound]({{ '/doc/manual/sound.html' | relative_url }}).

A movie can't be exported if the project contains 63 or more sound clips: Pencil2D shows an
error before the export dialog opens. It also warns you when you import that many clips. Split
very long projects into several shorter ones to stay under the limit.

## Animated GIF {#export-gif}

**File → Export → Animated GIF...** saves your animation as a `.gif` file that plays in web
browsers and chat apps. The **Export Animated GIF** dialog has the same **Camera**,
**Resolution** and **Range** settings as the [movie export](#export-movie), plus:

![The Export Animated GIF dialog]({{ "/images/manual/export-animated-gif.png" | relative_url }})

| Option | What it does | Default |
|---|---|---|
| **Loop** | On: the GIF repeats forever. Off: it plays once and stops | On |

When the export finishes, Pencil2D asks **Finished. Open file location?**

Limits of GIF export in 0.7.2:

- **256 colors.** Pencil2D builds one palette of up to 256 colors for the whole animation.
  Gradients and soft brushes may show banding or dithering.
- **No transparency.** GIFs always get a white background.
- **No sound.**
- **Memory use.** The whole animation is kept in memory while the GIF is encoded, so long or
  large GIFs need a lot of RAM.
- **Timing.** GIF stores frame times in hundredths of a second, so some frame rates are rounded.

The [Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}) explains
these limits in more detail and offers workarounds.

## Palette {#export-palette}

**File → Export → Palette** saves your current palette to a file. Choose **Pencil2D Palette**
(`.xml`) to use it in another Pencil2D project, or **GIMP Palette** (`.gpl`) to use it in other
programs that read GIMP palettes. See [Color and Palettes]({{ '/doc/manual/color.html#palette' | relative_url }}).

## FFmpeg {#ffmpeg}

Pencil2D uses a separate program, FFmpeg, for movie export, animated GIF export, movie video
import and sound import (it converts every sound clip, including movie audio). Image and image
sequence import and export don't need it.

FFmpeg ships with the Windows and macOS downloads and the Linux AppImage. Pencil2D looks for it
here:

| System | Location |
|---|---|
| Windows | `plugins\ffmpeg.exe` in the folder that contains `pencil2d.exe` |
| macOS | `Pencil2D.app/Contents/MacOS/plugins/ffmpeg` |
| Linux | A `plugins` folder next to the `pencil2d` program, otherwise any `ffmpeg` on your `PATH` |

If FFmpeg is missing, imports fail with **FFmpeg Not Found**, and exports fail with an error.
Antivirus software sometimes quarantines `ffmpeg.exe` on Windows.

If a movie or GIF export fails, is silent, is blurry, or has the wrong colors or timing, work
through the [Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

## Exporting Without Opening Pencil2D {#command-line}

You can also export images, image sequences, movies and GIFs from a terminal or a script, without
opening the main window. See the [Command-Line Interface]({{ '/doc/manual/command-line.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
