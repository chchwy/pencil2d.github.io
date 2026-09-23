---
layout: page
title: "Teacher's Guide"
tagline: A free nine-lesson animation course for the classroom, taught with Pencil2D
comments: false
---

This course teaches the basics of hand-drawn 2D animation in nine lessons, using the free program Pencil2D v0.7.2. Each lesson fits one 60–90 minute session in a computer lab and includes a short demo for you to give, step-by-step instructions for students, a practice challenge and an assessment checklist. You don't need to be an animator to teach it: every lesson explains its animation principle in plain words and tells you what to show and say.

{% include toc.html %}

## Who This Course Is For {#audience}

- **Students aged about 10–18**, and adult beginners in evening classes or workshops.
- **Teachers of art, media, computing or after-school clubs.** No animation or Pencil2D experience is needed. Each lesson takes about 30 minutes to prepare if you work through the steps yourself first, and we recommend you do.
- **Mouse users.** A drawing tablet helps but isn't required (see [Hardware](#hardware)).

By the end of the course, students can:

- explain the core ideas of animation (frames, keyframes, timing, spacing, squash and stretch, easing, arcs, anticipation, follow-through, staging) and point them out in cartoons they watch
- plan an animation as key poses first, then fill in the in-betweens
- use onion skin, layers, the timeline, the camera and sound in Pencil2D
- clean up rough drawings, color them and put them on a background
- time animation to sound and draw mouth shapes for speech
- save their work as a Pencil2D project and share it as an animated GIF or a movie file
- plan a short film with a storyboard and animatic, then finish it

## Course Map {#course-map}

Lessons 1–4 build the foundation and should be taught in order. Lessons 5–8 build on each other, but you can skip any of them to fit your timetable; Lesson 8 also works straight after Lesson 4. Lesson 9 brings everything together.

| Lesson | Principle taught | Pencil2D skills | Students make | Time |
|---|---|---|---|---|
| [1. Meet Pencil2D]({{ '/doc/course/lesson-01.html' | relative_url }}) | Animation is a series of still drawings | Tour, Pencil and Eraser, color, adding keyframes, play and loop, save and open | A 3–5 drawing flipbook loop | 60–75 min |
| [2. The Bouncing Ball]({{ '/doc/course/lesson-02.html' | relative_url }}) | Timing and spacing | Onion skin, frame rate, keys then in-betweens, holds, loop | A one-second bouncing ball loop | 75–90 min |
| [3. Squash, Stretch and Easing]({{ '/doc/course/lesson-03.html' | relative_url }}) | Squash and stretch, slow in and slow out, arcs | Editing keyframes, new layers, layer order, animated GIF export | An improved ball with a shadow, shared as a GIF | 75–90 min |
| [4. Layers, Line and Color]({{ '/doc/course/lesson-04.html' | relative_url }}) | Clean line and solid color (rough to clean-up) | Layer opacity, tracing, Bucket fill settings, palette, background layer | A cleaned-up, colored loop on a background | 75–90 min |
| [5. The Flour Sack Jump]({{ '/doc/course/lesson-05.html' | relative_url }}) | Anticipation, follow-through, weight | Posing keyframes, Add and Subtract Exposure, dragging keyframes, Flip In-Between, playback Range | A 2–3 second flour sack jump and a timing variation | 60–90 min |
| [6. Camera Moves]({{ '/doc/course/lesson-06.html' | relative_url }}) | Staging; easing applied to the camera | Camera layer, camera size, camera keyframes, easing, movie export | A 6-second shot with a pan and a zoom, exported as MP4 | 60–90 min |
| [7. The Walk Cycle]({{ '/doc/course/lesson-07.html' | relative_url }}) | Cycles, the four walk positions, weight shift | Guide layers, keyframes on twos, onion skin both ways, Flip Rolling, Loop and Range, copying keyframes | A looping walk in place, 12–16 drawings | 60–90 min |
| [8. Sound and Lip Sync]({{ '/doc/course/lesson-08.html' | relative_url }}) | Timing to sound, mouth shapes | Importing sound, sound layers, sound scrub, copying keyframes, movie export with sound | A talking head saying a 2–4 second line, MP4 with sound | 60–90 min |
| [9. Final Project]({{ '/doc/course/lesson-09.html' | relative_url }}) | All of the above, planning a whole film | Everything so far, plus planning, an animatic, MP4 and GIF export | A 5–15 second film of the student's own | 2–4 sessions |

The [Quick Reference]({{ '/doc/course/quick-reference.html' | relative_url }}) is a one-page sheet of shortcuts and fixes. Print one per computer.

## Installing Pencil2D in a School Lab {#installing}

Pencil2D is free for any use, including schools. Download it from the [download page]({{ '/download/' | relative_url }}). The full installation guide, with screenshots, is in [Getting Started]({{ '/doc/manual/getting-started.html#install' | relative_url }}). The notes below cover what matters in a lab.

### Windows {#install-windows}

Pencil2D for Windows comes as a **ZIP file**, not an installer. There is nothing to install: unzip it and run `pencil2d.exe`.

- **No administrator rights are needed** to run it. Students or teachers can unzip it into their own folder or a USB stick. For a whole lab, IT can place the unzipped folder in a shared location or copy it to each computer and add a shortcut to `pencil2d.exe`.
- Windows may block files downloaded from the internet. Before unzipping, right-click the ZIP file, choose **Properties**, tick **Unblock**, then unzip. See [How to Train Your Pencil2D]({{ '/doc/how-to-train-your-pencil2d.html' | relative_url }}).
- If Windows reports a missing file such as `MSVCP140.dll`, run the `vc_redist` installer in the Pencil2D folder. **This step needs administrator rights**, so ask IT. See the [download troubleshooting list]({{ '/download/#troubleshooting' | relative_url }}).
- Some school security policies block programs that run from user folders. If Pencil2D won't start, ask IT to allow `pencil2d.exe`.

### macOS {#install-macos}

Download the DMG file, open it and drag Pencil2D into the **Applications** folder. On a student account without administrator rights, drag it into a folder in the student's home folder instead. The v0.7.2 app is built for Intel Macs. On Apple silicon Macs (M1 and later) it runs through Apple's Rosetta 2, which macOS offers to install the first time it's needed.

### Linux {#install-linux}

Download the AppImage and make it executable (in most file managers: right-click, **Properties**, allow executing as a program; or run `chmod +x` on the file). No root access is needed. Pencil2D is also available as a Flatpak and in many distributions' package managers; see the [download page]({{ '/download/' | relative_url }}).

### Chromebooks, iPads and Android tablets {#install-chromebooks}

Pencil2D has no version for ChromeOS, iPadOS or Android, so these devices can't run the course. Some Chromebooks can run Linux programs if the school has turned on the Linux development environment, and the Linux version may work there, but this isn't a setup the Pencil2D team tests or supports.
<!-- VERIFY: Pencil2D on ChromeOS's Linux environment (Crostini) is untested; the download page offers no ChromeOS build. -->

### Check before the first lesson {#install-check}

On one lab computer, logged in as a student, start Pencil2D, draw something, press <kbd>F7</kbd>, draw again, press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> to play, then save the file to the folder students will use. Also try **File → Export → Animated GIF...** once. If all of that works, the lab is ready.

## Hardware {#hardware}

- **A mouse is fine.** Every lesson can be done with a mouse. Students draw more slowly, so keep drawings simple: a ball, a sack and a stick-figure walk work well. The Pencil and Pen tools start with the **Stabilizer** set to **Strong**, which smooths shaky mouse lines. If a student finds the line lags behind the cursor, set **Stabilizer** to **Simple** or **None** in the **Options** panel.
- **Drawing tablets** make drawing feel natural. With a tablet, line width changes with pen pressure when **Pressure** is ticked in the **Options** panel (it's on by default for the Pencil, Pen, Brush and Eraser). Test the tablet driver before class.
- **Tablet tips.** On Windows, panning the canvas by dragging with a pen button can misbehave. Students should hold <kbd>Space</kbd> and drag to pan instead. Some Huion tablets lag unless "linear optimizer" is turned off in the tablet's own settings.
- **Keyboards.** On many laptops the <kbd>F6</kbd> and <kbd>F7</kbd> keys only work while holding <kbd>Fn</kbd>. The buttons next to **Keys:** in the Timeline do the same job.
- **Screens.** A larger screen shows more of the timeline. Headphones are needed for Lesson 8.

> **Note:** On macOS, use <kbd>Cmd</kbd> wherever this course says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> for <kbd>Alt</kbd>. **Preferences** is in the **Pencil2D** app menu instead of the **Edit** menu.

## Preparing the Lab {#preparing-the-lab}

### Recommended settings {#recommended-settings}

Change these two settings on each computer, logged in as a student, before the first lesson. Pencil2D remembers preferences per user account, so if your lab resets accounts when students log out, add this to the start of each lesson.

| Setting | Where | Change to | Why |
|---|---|---|---|
| Drawing on an empty frame | **Edit → Preferences → Timeline**, **When drawing on an empty frame:** | **Create a new (blank) key-frame** | By default Pencil2D keeps drawing on the previous keyframe, so students accidentally change an earlier drawing |
| Autosave | **Edit → Preferences → Files**, **Autosave documents** | Tick **Enable autosave** | Saves the project every 15 changes by default. Lower the number to save more often |

The lessons are written so that they work even without these changes: students press <kbd>F7</kbd> to add a keyframe before drawing on a new frame. See the full list of settings in [Preferences]({{ '/doc/manual/preferences.html' | relative_url }}).

> **Note:** Autosave writes to the project's file, so students must save their project with a name first. If the project has never been saved, Pencil2D asks "The animation is not saved yet. Do you want to save now?" instead.

<!-- SCREENSHOT: Preferences dialog, Timeline page, with "Create a new (blank) key-frame" selected under "When drawing on an empty frame:" -->

### A shared folder and starter files {#starter-files}

Create a class folder on the network drive or learning platform with two subfolders:

- **starter** (read-only for students): starter projects that you prepare, such as a bouncing ball project with a guide layer (Lesson 2). Each lesson's **Before Class** section describes its starter file in words so you can make it in a few minutes.
- **student work**: one folder per student or per pair.

Students open a starter file and immediately use **File → Save As...** to save their own copy in their folder. If they save over the starter, the next class gets their changes.

### Saving student work {#saving-work}

- Pencil2D projects are saved as **`.pclx`** files. A `.pclx` file holds every drawing, layer and setting in one file that's easy to copy, email or upload.
- The save window also offers **Legacy Pencil2D Project (\*.pcl)**. Tell students not to choose it: a `.pcl` project is a file *plus* a separate `.pcl.data` folder, and copying only the file loses the drawings.
- Agree on a naming pattern, such as `lesson02-ball-sam.pclx`, so you can find work quickly.
- To share an animation outside Pencil2D, students export it (an animated GIF from Lesson 3 onwards). The `.pclx` file stays the editable master copy.
- If Pencil2D closes unexpectedly, start it again: it offers to restore the project. See the [project recovery guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }}).

More detail: [Projects and Files]({{ '/doc/manual/projects.html' | relative_url }}).

## Running a Session {#running-a-session}

Each lesson follows the same shape:

| Part | Time | What happens |
|---|---|---|
| Warm-up | 5 min | Show a short clip (a cartoon, a game, a GIF) and ask students to spot the lesson's principle |
| Key ideas and demo | 10–15 min | You explain the principle and demonstrate the steps on the projector |
| Step by step | 30–45 min | Students follow the steps; you circulate |
| Practice challenge | 10–20 min | Basic version for everyone, stretch version for fast finishers |
| Share and wrap-up | 5–10 min | A few students play their work; the class discusses |

Tips from the classroom:

- **Keep demos short.** Show one idea, then let students try it. Ten minutes of watching is the limit for most groups.
- **Show mistakes.** When your demo goes wrong, and it will, fix it out loud. The **Common Problems** section of each lesson lists what trips students up.
- **Pair work** works well for younger students or when computers are scarce: one draws, one "directs" and checks the timing, then they swap every few drawings.
- **Draw simple.** Circles, sacks and stick figures teach the principles as well as detailed drawings. Tell students the goal is movement, not pretty pictures.
- **Play it back often.** Students should press play after every few drawings. Animation is judged in motion, not frame by frame.
- **Share at the end.** Play each student's loop on the projector, or walk the room while everyone's animation loops on screen. Praise one specific thing, such as "the ball speeds up nicely as it falls", before suggesting one improvement.
- **Paper still helps.** A sticky-note flipbook in Lesson 1 or a pencil spacing chart in Lesson 2 makes the ideas concrete before students touch the computer.

## Adapting the Course {#adapting}

**Shorter sessions (45 minutes).** Split each lesson in two: the demo and steps in the first session, the practice challenge and sharing in the second. Or skip the stretch challenges and use the starter files so students spend their time animating, not setting up.

**Longer sessions or extra time.** Use the stretch challenges and the **Going Further** ideas. Lessons 3 and 4 combine well into one long project: bounce, then clean up and color.

**Younger students (about 10–12).**

- Stay with Lessons 1–4 and choose from 5–7.
- Use fewer drawings: a 4-drawing flipbook, a ball bounce with 4 drawings on twos.
- Give them the recommended settings and starter files so there is less to set up.
- Teach the shortcuts on the Quick Reference one at a time. Menus and buttons are fine.

**Older or experienced students.** Ask for more drawings (animation "on ones"), stricter spacing charts, and more personal final projects. Add the **Going Further** links to the reference manual.

**Mixed abilities.** Every lesson has a basic and a stretch challenge. Fast finishers can also help a neighbor, which is often the most useful thing in the room.

**Language.** Pencil2D is translated into many languages: **Edit → Preferences → General**, **Language**. Restart Pencil2D after changing it. Menu names in this course are in English.

## Assessment {#assessment}

Each lesson ends with an **Assessment Checklist** you can tick while students share their work. For a grade, use this rubric on each lesson's output or on the final project.

| Criterion | 1 Beginning | 2 Developing | 3 Secure | 4 Excellent |
|---|---|---|---|---|
| Timing | Action too fast or slow to read | Readable but uneven | Action takes a believable amount of time | Timing adds character or humor |
| Spacing | Drawings evenly spaced or jumping | Some speed change | Clear speeding up and slowing down where needed | Spacing is deliberate and smooth throughout |
| Principle applied | Principle not visible | Principle attempted | Principle clearly visible | Principle used with control and exaggeration |
| Craft | Drawings hard to read, file unsaved | Readable drawings, some problems | Clear drawings, tidy layers, saved as `.pclx` and exported | Clean, consistent drawings and polished result |
| Creativity | Copies the example exactly | Small personal change | Own idea within the task | Surprising, personal idea that still meets the task |
| Effort and process | Stopped early | Worked through most steps | Planned keys, tested often, fixed problems | Revised the work after feedback |

Keep the focus on movement. A simple circle that bounces well earns more than a detailed drawing that doesn't move.

## Getting Help {#help}

- The [User's Manual]({{ '/doc/manual/' | relative_url }}) explains every tool, panel and setting. Good places to start are [The Interface]({{ '/doc/manual/interface.html' | relative_url }}), [Timeline and Animation]({{ '/doc/manual/timeline.html' | relative_url }}) and [Onion Skin]({{ '/doc/manual/onion-skin.html' | relative_url }}).
- The [FAQ]({{ '/doc/faq.html' | relative_url }}) answers common questions about installing, saving and exporting.
- Ask the Pencil2D community on the [forum](https://discuss.pencil2d.org/) or on [Discord](https://discord.gg/8FxdV2g). Teachers are welcome, and so are your students' animations.
- Found a bug? Report it on the [bug tracker](https://github.com/pencil2d/pencil/issues).

## Copy, Translate and Adapt {#license}

This course, like the rest of the pencil2d.org website, is released under **CC0 1.0 Universal**: it's in the public domain. You may copy, print, translate, shorten, remix and share it, in class or in your own published materials, without asking permission and without crediting us. A link back to pencil2d.org is appreciated but not required. If you make a translation or an improved version, please tell us on the [forum](https://discuss.pencil2d.org/) so other teachers can use it too.

{% include series-nav.html series=site.data.course %}
