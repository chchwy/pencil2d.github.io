---
layout: page
title: Sound
tagline: Adding sound clips, timing animation to them, and exporting with sound
comments: false
---

You can add dialogue, music and sound effects to a Pencil2D project and time your drawings to them.
This chapter covers sound layers, importing clips, placing them on the timeline, listening while you
scrub, and getting the sound into your exported movie.

> **Note:** On macOS, press <kbd>Cmd</kbd> wherever this page says <kbd>Ctrl</kbd>, and
> <kbd>Option</kbd> wherever it says <kbd>Alt</kbd>.

{% include toc.html %}

## Sound layers {#sound-layers}

Sound lives on sound layers. A sound layer holds only sound clips. Each clip starts on a frame and
appears in the timeline as a bar as long as the sound. A new sound layer is empty.

To add one, use **Layer → New Sound Layer** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>W</kbd>) or the
add-layer button in the timeline, then type a name in the **Layer Properties** dialog. See
[Layers]({{ '/doc/manual/layers.html#managing-layers' | relative_url }}) for renaming, reordering and deleting layers.

A **hidden** sound layer (eye icon off) is muted: it doesn't play, it isn't heard while scrubbing,
and it is left out of movie exports. You can't import a clip onto a hidden layer.

## Adding sound {#adding-sound}

There are two ways to import a sound clip. Both place the clip on the **current frame** of a sound
layer. If a clip already starts on that frame, the new clip goes on the next frame where no clip
starts.

**From the File menu:**

1. Move the playhead to the frame where the sound should start.
2. Choose **File → Import → Sound...**
3. If the selected layer is not a sound layer, Pencil2D asks: "No sound layer exists as a
   destination for your import. Create a new sound layer?" Click **Create sound layer** and name the
   new layer, or click **Don't create layer** to cancel. The message appears whenever the selected
   layer isn't a sound layer, even if the project has sound layers elsewhere. To add the clip to an
   existing sound layer, select that layer first.
4. In the **Import sound** file dialog, pick your file and click **Open**.

**From the timeline:**

1. Select a sound layer and move the playhead to the start frame.
2. Use **Animation → Add Frame** (<kbd>F7</kbd>) or the add-frame button next to **Keys:** in the
   timeline. On a sound layer this doesn't create an empty keyframe. It opens the **Import sound**
   file dialog instead.
3. Pick your file and click **Open**.

While the file is converted, a progress window reads "Importing sound..." and you can click
**Abort**. If you cancel the file dialog or the import fails, nothing is added. When the import
succeeds, the clip grows in the timeline to its full length.

The clip is converted to WAV and stored **inside your project**, so you don't need the original file
afterwards. Uncompressed WAV is large, so long clips increase the size of your project file.

<!-- SCREENSHOT: Timeline with a sound layer holding two sound clips of different lengths, drawn as long bars -->

> **Note:** Sound import uses FFmpeg, the same program Pencil2D uses to import and export video.
> If FFmpeg is missing, importing sound fails. See
> [Importing and Exporting]({{ '/doc/manual/import-export.html' | relative_url }}) for details.

### Importing the sound track of a video {#movie-audio}

**File → Import → Movie Audio...** takes the sound out of a video file and adds it as a sound clip
on the current frame. It works like **Sound...**, but the file dialog (**Import movie**) lists video
files such as MP4, MOV, AVI, MKV and WebM. To import the pictures of a video, see
[Importing a movie]({{ '/doc/manual/import-export.html#import-movie' | relative_url }}).

## Supported formats {#formats}

The **Import sound** file dialog lists these formats:

| Format | Extension |
|---|---|
| WAV | .wav |
| MP3 | .mp3 |
| WMA | .wma |
| OGG | .ogg |
| FLAC | .flac |
| Opus | .opus |
| AIFF | .aiff |
| AAC | .aac |
| CAF | .caf |

FFmpeg converts every clip to WAV and removes metadata on import. WAV and MP3 are the most common and
are a safe choice. If a file in some other format won't import, convert it to WAV in an audio editor
first.

## Placing and moving clips {#moving-clips}

To move a clip to start on another frame, click it in the timeline to select it, then drag it left
or right. You can select several clips and move them together. See
[Selecting frames]({{ '/doc/manual/timeline.html#selecting-frames' | relative_url }}).

A clip's length in frames depends on the project's
[frame rate]({{ '/doc/manual/timeline.html#frame-rate' | relative_url }}). If you change the frame rate, each clip keeps its
start frame but its length in frames is recalculated, so it no longer lines up with the same
drawings. Set the frame rate before you time animation to sound.

## Multiple clips {#multiple-clips}

A sound layer can hold many clips one after another, and you can have as many sound layers as you
like. All clips play together, and export mixes them into a single track.

- To add another clip to the same layer, move the playhead past the end of the first clip and import
  again.
- To repeat a clip, put the playhead on its first frame and use **Animation → Duplicate Frame**
  (<kbd>F6</kbd>). The copy is placed right after the clip.
- Clips can also be copied and pasted like other frames; see
  [Copy and paste]({{ '/doc/manual/timeline.html#copy-paste' | relative_url }}).
- Putting dialogue, music and effects on separate layers makes it easier to mute one of them by
  hiding its layer.

### Limit on the number of clips {#clip-limit}

Movie export can't handle an unlimited number of sound clips. When you import or duplicate a clip
and the project then has **63** or more clips in total, Pencil2D warns you: "You currently have a
total of *N* sound clips. Due to current limitations, you will be unable to export any animation
exceeding 63 sound clips. We recommend splitting up larger projects into multiple smaller project to
stay within this limit."

With 63 or more clips, **File → Export → Movie...** refuses to start and shows the same message. The
count includes every clip on every sound layer, **hidden layers included**. Keep the whole project
at **62 clips or fewer** if you want to export it as a movie. To stay under the limit, combine short
clips into longer ones in an audio editor, delete sound layers you don't need, or split a long film
into several projects.

## Playing sound {#playback}

Sound plays when you play the animation (see [Playback]({{ '/doc/manual/timeline.html#playback' | relative_url }})). If you
start in the middle of a clip, the clip starts from the matching point. Playback runs until the end
of the last clip, even if the last drawing comes earlier.

The **Sound on/off** button in the timeline's playback controls mutes or unmutes playback. It is on
by default, and it doesn't affect export.

> **Warning:** During playback in Pencil2D the sound may seem to lag behind the pictures. The larger
> the project, with many layers and frames, the more noticeable this gets. It was listed as a known
> issue for 0.7.0. Sound scrubbing and the exported movie are not affected, so use scrubbing to check
> lip-sync and exact timing.
<!-- VERIFY: whether the playback audio delay (#1567, #1179) still occurs in 0.7.2; the 0.7.2 release notes no longer list it as a known issue and list a fix for "sounds being timed incorrectly during playback" (#1918). -->

## Sound scrubbing {#scrubbing}

With sound scrubbing on, Pencil2D plays a short snippet of the sound each time the playhead moves
while the animation is stopped. The snippet plays when you click or drag in the frame numbers along
the top of the timeline, and when you step frames with <kbd>.</kbd> and <kbd>,</kbd>. Scrubbing lets you find the exact frame a word or a
beat lands on.

- Turn it on or off with the **Sound scrub on/off** button in the timeline's playback controls. It is
  off by default, and Pencil2D remembers the setting.
- Set the snippet length under **Sound scrub** in
  [Preferences → Timeline]({{ '/doc/manual/preferences.html#timeline' | relative_url }}). The default is 100 ms and the
  maximum is 200 ms. The minimum is the duration of one frame at the project's frame rate, but never
  more than 100 ms.

## What the timeline shows {#timeline-display}

Pencil2D does **not** draw a waveform. A clip appears as a plain colored bar from its start frame to
its end. To find where words or beats fall, use [sound scrubbing](#scrubbing). Another option is to
note the times in an audio editor and convert them to frames (seconds × frame rate + 1).

## Removing sound {#removing-sound}

- **One clip:** put the playhead anywhere on the clip and use **Animation → Remove Frame**
  (<kbd>Shift</kbd>+<kbd>F5</kbd>) or the remove-frame button next to **Keys:** in the timeline.
- **Several clips:** select them and choose **Animation → Timeline Selection → Remove Frames**.
  Pencil2D asks for confirmation, and this can't be undone.
- **A whole sound layer:** select it and choose **Layer → Delete Current Layer**.
- To keep the clips but silence them, hide the layer instead.

## Exporting with sound {#exporting}

Sound is included when you export a movie with **File → Export → Movie...**. See
[Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}) for all the options. For sound, note
the following:

- By default the export ends at your last drawing. Tick **To the end of sound clips** to extend the
  end frame to the end of the last clip.
- Clips are placed at their start frames and trimmed to the frame range you export.
- All clips on visible sound layers are mixed into a single track. Hidden sound layers are left
  out.
- Animated GIFs never contain sound.
- Movie export refuses to start when the project has 63 or more clips; see
  [Limit on the number of clips](#clip-limit).

If the video won't export at all, see the
[Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
