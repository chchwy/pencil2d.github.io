---
layout: page
title: "Lesson 8: Sound and Lip Sync"
tagline: Import a line of dialogue, read the track, and make a character say it
comments: false
---

Students import a short recorded line of dialogue, listen to it frame by frame, and animate a mouth
that matches it. They then export a movie that has the sound in it. Lip sync is timing work, so it
builds on everything students have learned about keyframes and exposure. It is also the lesson
students usually enjoy most, because the character finally talks.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | One session, 60–90 minutes |
| **Level** | Intermediate, after Lessons 1–7 (it also works straight after Lesson 4) |
| **Animation principle** | Timing to sound; mouth shapes for sounds; the picture slightly ahead of the sound |
| **Pencil2D skills** | **File → Import → Sound...**, sound layers, moving a clip, **Sound on/off**, **Sound scrub on/off**, copy and paste of keyframes, **File → Export → Movie...** with sound |
| **What students make** | A talking head saying a 2–4 second line, exported as MP4 with sound |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Import a sound clip into Pencil2D and place it on the timeline.
2. Use sound scrubbing to find the frame where each sound in a line starts.
3. Choose mouth shapes by what they *hear*, not by how a word is spelled.
4. Time mouth shapes slightly ahead of the sound and export a movie with the sound in it.

## Before Class {#before-class}

- **Headphones** for every student. A lab full of students scrubbing sound is loud.
- **Dialogue clips.** Each student needs a clip of 2–4 seconds with one clear line, saved as WAV or
  MP3. Some options:
  - you record 6–10 short lines (for example *"Oh, hello!"* or *"Wait. Where's my sandwich?"*) and
    put them in a shared folder;
  - students record their own lines with a voice recorder app or a free audio editor.
- **Privacy.** Follow your school's policy on recording students' voices. Lines should not contain
  names, addresses or other personal information. Students who don't want to use their voice can pick
  one of your clips.
- **Test on one lab computer** that importing a clip and exporting an MP4 both work. Pencil2D uses
  FFmpeg for both. If either fails, see the
  [video export troubleshooting guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).
- **Print** the mouth chart below, and give students paper for a track-reading table.
- **Optional starter file** (`lipsync-start.pclx`, 12 fps): a layer named **Head** with a face that has
  no mouth, and an empty layer named **Mouth** above it.

## Key Ideas {#key-ideas}

**Lip sync** means matching mouth shapes to the sounds of speech. Animate what you *hear*, not the
spelling: "hello" sounds like *h-eh-l-oh*, and the "gh" in "night" has no mouth shape at all.

**Fewer shapes look better.** Real mouths don't hit every sound, and a mouth that changes on every
frame flickers. Hit the vowels and the sounds that close the lips (M, B, P), skip small sounds in
between, and hold most shapes for at least 2 frames.

**The mouth chart.** Six shapes cover nearly everything; two more are optional:

| Shape | Sounds | Looks like |
|---|---|---|
| **Closed** | M, B, P, and silence | Lips pressed together |
| **Open** | A, I (as in "cat", "hi") | Jaw dropped, mouth wide open |
| **Wide** | E, and C, D, G, K, N, S, T, Y, Z | Mouth wide, teeth together or nearly |
| **Round** | O (as in "go") | Open circle |
| **Pucker** | OO, U, W, Q | Small, pushed-forward circle |
| **F / V** | F, V | Top teeth resting on the bottom lip |
| *L* (optional) | L, TH | Mouth open, tongue touching the top teeth |
| *Rest* (optional) | Pauses | Relaxed, lips just apart |

<!-- SCREENSHOT: A mouth chart with the eight mouth shapes drawn in a simple cartoon style, labeled Closed, Open, Wide, Round, Pucker, F/V, L and Rest -->

**Lead the sound.** We notice a picture slightly before we process the sound that goes with it, so
lip sync looks right when each mouth shape appears a little *before* its sound: about 1 frame early
at 12 fps (about 2 frames at 24 fps). Sound effects such as a door slam are different: put them
exactly on the frame of the impact.

**Frame math.** At 12 fps, one second is 12 frames. If a clip starts on frame 13, a sound half a
second into the clip lands on frame 13 + 6 = 19.

| Word | Meaning |
|---|---|
| Lip sync | Matching mouth shapes to dialogue |
| Phoneme | A single sound of speech, such as "oh" or "m" |
| Track reading | Listening to the sound frame by frame and writing down where each sound starts |
| Scrubbing | Dragging the playhead to hear and see the animation frame by frame |
| Lead | Showing a mouth shape a frame or two before its sound |

## Demo {#demo}

About 10 minutes.

1. **Say it in a mirror.** Have the class say "Oh, hello!" slowly while watching a partner's mouth
   (or their own in a phone camera). Ask: *"How many different shapes did you see?"* Usually 4 or 5,
   not one per letter.
2. **Import.** In Pencil2D, import a clip with **File → Import → Sound...**. Point out the colored bar
   on the new sound layer: it is as long as the sound.
3. **Scrub.** Turn on **Sound scrub on/off** and drag slowly across the frame-number row. Say:
   *"Now we can hear exactly which frame each sound is on."*
4. **Track reading.** Step through with <kbd>.</kbd> and write three or four rows of a track-reading
   table on the board.
5. **Before and after.** Show a finished lip sync (yours) with the mouth exactly on the sound, then
   with every mouth keyframe moved one frame earlier. Ask which looks better.

## Step by Step {#steps}

Shortcuts are given for Windows and Linux. On macOS, use <kbd>Cmd</kbd> instead of <kbd>Ctrl</kbd>
and <kbd>Option</kbd> instead of <kbd>Alt</kbd>.

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the
> frame you want. The playhead shows the number of the frame it is on. A single click on a cell in a
> layer's track selects that keyframe; it does not move the playhead.

**Part A: Set up (10 minutes)**

1. Open the starter file, or create a new project with a **Head** layer and a **Mouth** layer above it.
   Save it as `lipsync-yourname.pclx`.
2. Check that the frame rate box on the timeline says **12 fps** *before* you import any sound. If you
   change the frame rate later, the sound stays on its start frame but no longer lines up with your
   drawings.
3. On the **Head** layer, frame 1, draw a face without a mouth. Make the mouth area large enough to draw
   in comfortably.

**Part B: Import the sound (5 minutes)**

{: start="4"}
4. Go to frame **1**. Choose **File → Import → Sound...**.
5. Pencil2D says *"No sound layer exists as a destination for your import. Create a new sound
   layer?"* Click **Create sound layer**, name the layer **Voice**, and click **OK**.
6. Pick your clip (WAV, MP3, OGG and FLAC are among the formats Pencil2D accepts) and click **Open**.
   After a short *"Importing sound..."* message, the clip appears as a bar on the **Voice** layer.
7. Give the character a moment before it speaks. Click the first frame of the clip (frame 1 of the
   **Voice** track) to select it, then press on it again and drag it to the right until it starts on
   frame **13**, one second in.
8. Play (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). Playback runs to the end of the clip. The **Sound
   on/off** button in the playback controls mutes and unmutes sound.

> **Tip:** Another way to import: add a sound layer with **Layer → New Sound Layer**
> (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>W</kbd>). With that layer selected, **Add Frame**
> (<kbd>F7</kbd>) opens the file dialog, and the clip starts at the playhead.

<!-- SCREENSHOT: Timeline with three layers (voice sound layer with a clip bar starting at frame 13, mouth, head), and the Sound on/off and Sound scrub on/off buttons highlighted in the playback controls -->

**Part C: Read the track (15 minutes)**

{: start="9"}
9. Click the **Sound scrub on/off** button in the playback controls. Now each time the playhead moves,
   Pencil2D plays a short snippet of sound.
10. Press <kbd>.</kbd> (**Next Frame**) and <kbd>,</kbd> (**Previous Frame**) to step through the
    line one frame at a time. You can also drag slowly in the frame-number row.
11. On paper, write a track-reading table: the frame where each sound starts, and the mouth shape from
    the chart. For "Oh, hello!" starting on frame 13 it might look like this (your frames will be
    different):

    | Frame | Sound heard | Mouth shape |
    |---|---|---|
    | 13 | "Oh" | Round |
    | 17 | (pause) | Closed |
    | 19 | "he-" | Wide |
    | 21 | "-l-" | L (or Wide) |
    | 22 | "-lo!" | Round |
    | 26 | (end) | Closed |

**Part D: Animate the mouth (25 minutes)**

{: start="12"}
12. Click the **Mouth** layer. On frame 1, draw the **Closed** mouth. It stays on screen until the next
    mouth keyframe.
13. For each row of your table, go to **one frame earlier** than the frame you wrote down (the lead),
    press <kbd>F7</kbd>, and draw the mouth shape. For the table above, that means frames 12, 16, 18,
    20, 21 and 25.
14. **Reuse shapes** instead of redrawing them. Save first (<kbd>Ctrl</kbd>+<kbd>S</kbd>), because
    pasting frames can't be undone yet. Click an earlier mouth keyframe with the shape you need in the
    **Mouth** track, press <kbd>Ctrl</kbd>+<kbd>C</kbd>, go to the frame where you need it, and
    press <kbd>Ctrl</kbd>+<kbd>V</kbd>. Press <kbd>Ctrl</kbd>+<kbd>D</kbd> to clear the selection.
15. Play and watch the mouth, not the table. To repeat one word over and over, tick **Range**, set the
    two boxes around that word, and turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>).
16. To nudge a mouth keyframe, put the playhead on it and use **Animation → Move Frame Backward**
    (<kbd>Ctrl</kbd>+<kbd>,</kbd>) or **Move Frame Forward** (<kbd>Ctrl</kbd>+<kbd>.</kbd>).

> **Note:** In a large project, sound during playback inside Pencil2D can seem slightly late. Sound
> scrubbing and the exported movie are what count; when in doubt, export a quick test movie.

**Part E: Export with sound (5 minutes)**

{: start="17"}
17. Choose **File → Export → Movie...**. Click **Browse...**, name the file `lipsync-yourname.mp4` and
    save it as MP4.
18. Under **Range**, tick **To the end of sound clips**. Otherwise the movie ends at your last
    drawing and may cut off the end of the line.
19. Keep **Width** and **Height** even numbers (MP4 requires it) and click **OK**. When Pencil2D asks
    *"Finished. Open movie now?"*, click **Yes** and check the sync.

Things to know about sound in exports:

- An **animated GIF** has no sound. Use a movie format such as MP4 when sound matters.
- Hidden sound layers are left out of the movie.
- If the project has **63 or more** sound clips in total, Pencil2D refuses to export a movie. That
  won't happen in this lesson, but it can in a long final project.
- The sound is stored inside the `.pclx` file, so the project still has its sound on another computer.

More detail: [Adding sound]({{ '/doc/manual/sound.html#adding-sound' | relative_url }}),
[Sound formats]({{ '/doc/manual/sound.html#formats' | relative_url }}), [Sound]({{ '/doc/manual/sound.html' | relative_url }}) and
[Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

## Practice Challenge {#challenge}

**Basic:** A talking head that says a 2–4 second line, using at least five different mouth shapes,
with M/B/P sounds closed, shapes leading the sound by one frame, and an MP4 export with sound.

**Stretch:** Choose one:

- **Acting:** find the most important word in the line. Raise the eyebrows or tilt the head on it,
  and add a blink after the line ends.
- **Dialogue:** two characters, each with their own clip on their own sound layer, taking turns.
- **Sound effects:** give your flour sack from Lesson 5 a *whoosh* on the jump and a *thud* exactly on
  the landing frame.

## Wrap-up {#wrap-up}

Play the movies with sound for the class. First watch one with eyes closed, then with eyes open.

Discussion questions:

- Which mouth shapes did you use most? Which did you never need?
- Did leading the sound by one frame make a difference you could see?
- Where did you skip sounds, and did anyone notice?
- Apart from the mouth, what else could show *how* the character says the line?

## Assessment Checklist {#assessment}

| Look for | Evidence |
|---|---|
| Track reading | A table with frame numbers and mouth shapes, made by scrubbing |
| Shapes match sounds | Shapes follow what is heard, not the spelling; M/B/P close the lips |
| Timing | Mouth shapes lead the sound slightly; no shape is noticeably late |
| No flicker | Most shapes are held 2 frames or more; small sounds are skipped |
| Export | MP4 with sound, the whole line included, in sync |
| Reflection | Student can explain one timing decision they made |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| "No sound layer exists..." appears | The selected layer isn't a sound layer | Click **Create sound layer**, or select your sound layer before importing |
| <kbd>F7</kbd> opened a file dialog | The sound layer is selected; **Add Frame** on a sound layer imports a clip | Cancel, click the **Mouth** layer, then press <kbd>F7</kbd> |
| The import fails | Unusual file type, or FFmpeg problem | Convert the clip to WAV or MP3 in an audio editor and try again; see the [troubleshooting guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}) |
| No sound when playing | **Sound on/off** is off, the sound layer is hidden, or the volume is down | Turn sound on, show the layer, check the headphones |
| No sound when scrubbing | **Sound scrub on/off** is off | Click the button in the playback controls |
| The mouth is in sync in one place and late in another | The frame rate was changed after importing | Put the frame rate back, or re-time the mouth keyframes |
| The mouth flickers | Shapes last only 1 frame | Hold shapes for 2 frames or more; drop small sounds |
| The movie ends before the voice finishes | The export range stops at the last drawing | Tick **To the end of sound clips**, or type the **End Frame** |
| The movie has no sound | It was exported as a GIF, or the sound layer was hidden | Export as MP4 with the sound layer visible |
| Movie export refuses to start and talks about sound clips | 63 or more clips in the project | Combine clips in an audio editor, or split the film into parts |

## Going Further {#going-further}

- Import the sound track of a video with **File → Import → Movie Audio...** (see
  [Sound]({{ '/doc/manual/sound.html' | relative_url }})).
- Use a free audio editor to see the waveform of your clip. Pencil2D shows a clip as a plain bar
  without a waveform. The loud peaks show where the vowels are.
- Switch the timecode display: click the small menu button just after **Sound scrub on/off** in the
  playback controls and choose **SMPTE Timecode** to see minutes, seconds and frames. This helps when
  you match times noted in an audio editor.
- Next: [Lesson 9: Final Project]({{ '/doc/course/lesson-09.html' | relative_url }}).

{% include series-nav.html series=site.data.course %}
