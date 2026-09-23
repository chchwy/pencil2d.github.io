---
layout: page
title: "Lesson 9: Final Project"
tagline: Plan, animate and share a short film of 5 to 15 seconds
comments: false
---

Students make a short film from start to finish: an idea, a storyboard, an animatic, animation,
clean-up, camera and sound, and a final export. The project brings together everything from Lessons
1–8 and ends with a class screening. **Plan for 2–4 sessions**: three working sessions of 60–90
minutes plus a screening works well for most classes, and a fourth working session gives time for
polish.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | 2–4 sessions of 60–90 minutes, plus a screening |
| **Level** | After Lessons 1–8 |
| **Animation principle** | All of them: timing, spacing, anticipation, squash and stretch, follow-through, staging |
| **Pencil2D skills** | Everything so far, plus planning a project, building an animatic, and exporting MP4 and GIF |
| **What students make** | A finished 5–15 second film (60–180 frames at 12 fps), exported as MP4 (with sound if used) and as a GIF |

## Learning Objectives {#objectives}

By the end of the project, students can:

1. Turn an idea into a storyboard and an animatic with planned timing.
2. Manage a small production: set milestones, keep to them, and cut scope when needed.
3. Apply at least two animation principles on purpose, and point them out.
4. Give and use specific, kind feedback.
5. Export their film and share it safely.

## Before Class {#before-class}

- **Decide the format:** individual or pairs, and the length. 5–15 seconds sounds short, but at
  12 fps that is 60–180 frames.
- **Offer prompts** for students who are stuck: *a surprise*, *an object comes to life*, *a small
  creature with a big problem*, *the perfect jump*, *waiting*.
- **Print** the planning sheet and a storyboard page with 6–9 empty boxes.
- **File names and storage.** Choose a naming pattern that contains no personal information, for
  example `final-classcode-studentnumber.pclx`, and a place to save (a network folder or USB drive).
  Consider turning on autosave on every computer: **Edit → Preferences → Files → Enable autosave**
  (on macOS, Preferences is in the **Pencil2D** application menu).
- **Sound:** have headphones ready and a folder of sounds that you recorded or that are free to reuse
  (for example sounds released under CC0). Films without sound are fine, too.
- **Book the screening:** a room with a projector and speakers, and a date students can work towards.
- **Check your school's sharing policy** before promising that films will be posted anywhere.

## Key Ideas {#key-ideas}

**The production pipeline.** Studios work in stages, and each stage catches problems while they are
still cheap to fix:

| Stage | What it is | In Pencil2D |
|---|---|---|
| 1. Idea | One sentence: who wants what, and what happens | Paper |
| 2. Thumbnail storyboard | 6–9 small sketches of the key moments | Paper, or one drawing per keyframe |
| 3. Animatic | The storyboard drawings timed to the planned length, with sound | One keyframe per panel, timed with exposure ([Lesson 5]({{ '/doc/course/lesson-05.html' | relative_url }})) |
| 4. Key poses | The main drawings of every action | A **Rough** layer on top of the animatic |
| 5. In-betweens | The drawings that connect the keys | Onion skin, **Flip In-Between** |
| 6. Clean-up and color | Final lines and fills | **Line** and **Color** layers ([Lesson 4]({{ '/doc/course/lesson-04.html' | relative_url }})) |
| 7. Camera and sound | Camera moves and sound effects or dialogue | [Lesson 6]({{ '/doc/course/lesson-06.html' | relative_url }}), [Lesson 8]({{ '/doc/course/lesson-08.html' | relative_url }}) |
| 8. Export | The finished film | **File → Export → Movie...** and **Animated GIF...** |

**Scope.** A finished 8-second film beats an unfinished 30-second one. Good short films have one
clear idea, one or two characters, one to three shots, and a beginning, a middle and an end (setup,
action, payoff).

**Why an animatic?** It shows whether the story reads and whether the timing works *before* hours go
into drawing. If a moment feels slow in the animatic, it will feel slow in the finished film.

### Project planning sheet {#planning-sheet}

Students fill this in during the first session and get it signed off before animating.

| Item | Student's answer |
|---|---|
| Working title | |
| The idea in one sentence | |
| Character(s) | |
| Setting | |
| Beginning / middle / end | |
| Principles I will show (at least two) | |
| Length in seconds, and in frames (seconds × 12) | |
| Shots (wide, medium, close-up) and camera moves | |
| Sound: none, effects, music or dialogue? Where will it come from? | |
| Layers I will need | |
| If I run out of time, I will cut... | |
| Teacher sign-off | |

## Demo {#demo}

About 10 minutes, in the first session.

1. **Show a finished short** (yours, or one from a previous class), then the animatic it was made
   from. Ask: *"What changed between the two? What stayed the same?"*
2. **Build a mini animatic live.** Draw four very rough panels on frames 1–4 of a layer called
   **Animatic**. Put the playhead on each one and press <kbd>Ctrl</kbd>+<kbd>+</kbd> to hold it for
   the right time. Play it. Say: *"Ten minutes of rough drawing, and we already know whether the joke
   works."*
3. **Show the milestones** below and where students will be at the end of each session.

## Step by Step {#steps}

Shortcuts are given for Windows and Linux. On macOS, use <kbd>Cmd</kbd> instead of <kbd>Ctrl</kbd>
and <kbd>Option</kbd> instead of <kbd>Alt</kbd>.

> **Going to a frame:** click in the row of frame numbers along the top of the timeline, above the
> frame you want. The playhead shows the number of the frame it is on. A single click on a cell in a
> layer's track selects that keyframe; it does not move the playhead.

**Stage 1–2: Idea and storyboard (session 1)**

1. Fill in the planning sheet. Keep the idea small.
2. Draw a thumbnail storyboard with 6–9 panels. Under each panel, write what happens and roughly how
   many seconds it lasts. Get the teacher's sign-off.

**Stage 3: Animatic (session 1–2)**

{: start="3"}
3. Create the project: **File → New**, then **File → Save As...** with your agreed file name. Check
   the frame rate (**12 fps**), and set the camera size by double-clicking **Camera Layer** in the
   timeline (**Camera Properties**; for example 1280 × 720).
4. Add a bitmap layer called **Animatic**. Draw each storyboard panel quickly on its own keyframe:
   frames 1, 2, 3, and so on (go to the frame, press <kbd>F7</kbd>, draw).
5. Time the panels: put the playhead on each panel and press <kbd>Ctrl</kbd>+<kbd>+</kbd>
   (**Animation → Timeline Selection → Add Exposure**) until it lasts as long as planned. One second
   is 12 frames. The last panel has nothing after it to push, so its length is set by where the film
   ends: tick **Range** and type the planned last frame in the second box.
6. If the film has sound, import it now with **File → Import → Sound...**, so you can time the
   panels to it.
7. Play the animatic with **Loop** on. Is the total length right? Does the story
   read? Fix it now: this is the cheapest moment to change anything.

**Stage 4–6: Animation (sessions 2–3)**

{: start="8"}
8. Add a **Rough** layer above the animatic. Draw the key poses of every action, using the animatic as
   a guide for position and timing. Hide the animatic when it gets in the way by clicking its
   visibility icon at the left end of its row in the timeline.
9. Add in-betweens with onion skin (<kbd>O</kbd> and <kbd>Alt</kbd>+<kbd>O</kbd>) and check them
   with **Flip In-Between** (<kbd>Alt</kbd>+<kbd>Z</kbd>).
10. Clean up on a **Line** layer and fill on a **Color** layer, as in Lesson 4. Only clean up once the
    rough animation plays well.
11. Save often (<kbd>Ctrl</kbd>+<kbd>S</kbd>). Before a big change, save a copy with
    **File → Save As...** and a version number (`-v2`). Paste and **Remove Frames** can't be undone
    yet.

**Stage 7: Camera and sound (session 3)**

{: start="12"}
12. Add camera keyframes on **Camera Layer** with the **Move** tool, and choose easing by
    right-clicking a camera keyframe (see Lesson 6). Make sure the last camera keyframe is on the
    last frame of the film.
13. Add or adjust sound: dialogue, effects on impact frames, music. Keep the whole project well below
    63 sound clips; above that, Pencil2D can't export a movie.

**Stage 8: Export (session 3 or 4)**

{: start="14"}
14. **Movie:** **File → Export → Movie...**, click **Browse...**, save as MP4. Check **Camera**,
    **Width** and **Height** (even numbers for MP4), and the **Range**. Tick **To the end of sound
    clips** if the sound runs past the last drawing. Click **OK**.
15. **GIF:** **File → Export → Animated GIF...**. Leave **Loop** ticked for a looping GIF. A GIF has
    no sound, and large GIFs make big files, so a smaller **Width** and **Height** (for example
    640 × 360) keeps it manageable.
16. **Watch the exported file** all the way through, outside Pencil2D. Check that the first and last
    frames are right, that the final hold is included, and that the sound is in sync.
17. Hand in the `.pclx` project and the exported files, named as agreed.

![The Export Movie dialog]({{ "/images/manual/export-movie.png" | relative_url }})

**Milestones**

| End of... | Must have | Nice to have |
|---|---|---|
| Session 1 | Signed planning sheet, storyboard, animatic started | Animatic finished |
| Session 2 | Animatic finished and peer-reviewed; key poses for every action | Most in-betweens |
| Session 3 | All in-betweens; camera and sound in; a first export | Clean-up and color |
| Session 4 (optional) | Clean-up, color, peer review of the rough cut, final export | Title and credits |

For export detail, see [Exporting a movie]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}) and
[Exporting a GIF]({{ '/doc/manual/import-export.html#export-gif' | relative_url }}).

## Practice Challenge {#challenge}

**Basic:** A complete 5–10 second film with a clear beginning, middle and end, at least two animation
principles used on purpose, and an MP4 or GIF export.

**Stretch:** A 10–15 second film with two or more shots, at least one eased camera move, and sound
(effects, dialogue or music) in sync. Add a title card at the start and a credits card at the end.
Use first names or a nickname in the credits.

## Wrap-up {#wrap-up}

**Peer review.** Hold it twice if you can: once on the animatic (session 2) and once on the rough cut
(session 3 or 4). In pairs or small groups, each film is played at least twice. Reviewers answer:

1. What happens in the film? (If the answer doesn't match the idea, the story needs work.)
2. Where did your eye go? Was that where the animator wanted it?
3. Which moment felt too fast or too slow?
4. Where did you see anticipation, squash and stretch or follow-through?
5. Did anything pop, flicker or jump?
6. If there is sound: is it in sync?
7. **Two stars and a wish:** two things that work well, and one change that would make it better.

Feedback should be kind, specific and helpful: *"The crouch before the jump is too short to notice"*
is useful; *"It's weird"* is not.

**The screening.** Put all final MP4s in one folder, in a planned order, and play them on the big
screen like a festival. Introduce each film with its title and the animator's first name. Ideas:

- audience cards with one *"I liked..."* comment for each film;
- light-hearted awards for everyone (best timing, best sound, funniest moment, most improved);
- loop the GIFs on a screen in the hallway or at a parents' evening, if your school allows it;
- afterwards, discuss: *What would you do differently next time? What took longer than you expected?*

**Sharing safely.**

- Follow your school's policy. Get the permissions it requires (from students, and from parents
  where needed) before a film is shown outside the class or posted online.
- Films, file names and credits should contain no full names, addresses, school names, photos of
  faces or other personal information. Use first names or nicknames.
- Only use sounds and music that the students made themselves or that are free to reuse.
- Share through a platform the school has approved. Students under a platform's minimum age should
  not post themselves; the teacher can share on the class's behalf.

## Assessment Checklist {#assessment}

This rubric uses the same six criteria as the rubric in the [Teacher's Guide]({{ '/doc/course/' | relative_url }}).

| Criterion | 1 Beginning | 2 Developing | 3 Secure | 4 Excellent |
|---|---|---|---|---|
| **Timing** | Actions too fast or slow to read | Some actions read clearly | Holds and actions are well timed | Timing adds comedy, weight or emotion |
| **Spacing** | Jumps or uneven motion | Mostly even; some pops | Smooth, with easing where needed | Spacing clearly shows speed and weight |
| **Principle applied** | No principle visible | One principle, partly applied | Two principles applied on purpose | Several principles combine naturally |
| **Craft** | Hard to follow, unfinished | Readable, rough | Clean, consistent drawing and export | Polished lines, color, camera and sound |
| **Creativity** | Copies an example | Small personal touches | A clear idea of the student's own | A surprising or memorable idea |
| **Effort** | Planning skipped, milestones missed | Some stages done | All stages done, feedback used | Went beyond the brief and helped others |

Also check that the planning sheet, storyboard and animatic were completed, and that the export
plays correctly outside Pencil2D.

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| The film won't be finished in time | The idea is too big | Cut shots or characters now; a short finished film is the goal |
| The story isn't clear to others | The key moment is too short, or off screen | Hold the key moment longer; use a close-up |
| The export stops early or misses the final hold | Export ends at the last keyframe by default | Add a keyframe on the last frame, type the **End Frame**, or tick **To the end of sound clips** |
| The export shows the animatic | The animatic layer is still visible | Hide it or delete it before exporting |
| The MP4 won't export (odd width or height) | MP4 needs even numbers | Use even numbers such as 1280 × 720 |
| Movie export refuses because of sound clips | 63 or more clips in the project | Combine clips in an audio editor |
| The GIF is huge | GIFs don't compress well | Export a smaller size, or share the MP4 |
| Work was lost | No save, or a paste/remove that can't be undone | Save often and keep versions; see the [project recovery guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }}) |
| Export fails completely | FFmpeg problem | See the [video export troubleshooting guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}) |

## Going Further {#going-further}

- Make a class film: each student animates one shot of a shared story, and the teacher joins the
  exports in a video editor.
- Enter a student animation festival (check the rules and your school's policy first).
- Keep going with Pencil2D: the [User's Manual]({{ '/doc/manual/' | relative_url }}) covers every tool and setting, and the
  [Quick Reference]({{ '/doc/course/quick-reference.html' | relative_url }}) collects the shortcuts from this course.
- Ask questions and see other people's work on the [Pencil2D forum](https://discuss.pencil2d.org/).

{% include series-nav.html series=site.data.course %}
