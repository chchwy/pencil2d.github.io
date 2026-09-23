---
layout: page
title: "Lesson 1: Meet Pencil2D"
tagline: Find your way around, draw, and make your first flipbook animation
comments: false
---

In this first lesson students learn that an animation is just a series of still drawings shown quickly, one after another. They find their way around Pencil2D, draw with the Pencil and Eraser, make a short flipbook of 3–5 drawings, play it in a loop and save it as a project they can open again next time.

> **Note:** On macOS, use <kbd>Cmd</kbd> wherever this lesson says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> for <kbd>Alt</kbd>. On many laptops, <kbd>F6</kbd> and <kbd>F7</kbd> need <kbd>Fn</kbd> held down.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | 60–75 minutes |
| **Level** | Complete beginner |
| **Animation principle** | Animation is a sequence of slightly different still drawings |
| **Pencil2D skills** | The main window, Pencil and Eraser, choosing colors, adding keyframes, playing and looping, saving and opening a `.pclx` project |
| **What students make** | A looping flipbook of 3–5 drawings, such as a growing flower or a blinking face |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Explain in their own words how a series of still pictures becomes movement.
2. Name the main parts of the Pencil2D window: canvas, **Tools**, **Options**, color panels and **Timeline**.
3. Draw and erase with the Pencil and Eraser, and change the color and line width.
4. Add new keyframes and draw a different picture on each one.
5. Play the animation, loop it and change how fast it plays.
6. Save the animation as a `.pclx` project and open it again.

## Before Class {#before-class}

- Install Pencil2D and check it works on a student account. See [Installing Pencil2D in a School Lab]({{ '/doc/course/#installing' | relative_url }}).
- Apply the [recommended settings]({{ '/doc/course/#recommended-settings' | relative_url }}) if you can.
- Create the class folder where students will save their work, and write its location on the board.
- Practice the **Step by Step** section yourself once. It takes about 15 minutes.
- **Optional warm-up materials:** a pad of sticky notes per pair, to make a 4-page paper flipbook in the first five minutes.
- **Optional starter file:** none is needed. Students start with a new, empty project.
- Print the [Quick Reference]({{ '/doc/course/quick-reference.html' | relative_url }}), one per computer.

## Key Ideas {#key-ideas}

**Animation is an illusion.** When we see pictures that change a little, one after another, very quickly, our brain joins them into movement. A flipbook works this way, and so does every cartoon, film and video game.

- If each picture changes **a little**, the movement looks smooth.
- If each picture changes **a lot**, the movement looks jumpy or fast.
- If two pictures in a row are the **same**, the movement stops for a moment. That's called a *hold*.

| Word | Meaning |
|---|---|
| **Frame** | One picture in the animation. The timeline numbers every frame: 1, 2, 3... |
| **Keyframe** | A frame where you made a drawing. In Pencil2D it shows as a block in the timeline. A keyframe's drawing stays on screen until the next keyframe. |
| **Playback** | Showing the frames one after another to see the movement |
| **Frame rate (fps)** | How many frames are shown each second. A new project uses 12 frames per second, or the last frame rate you set. |
| **Loop** | Playing the animation again and again without stopping |
| **Onion skin** | Seeing the previous drawing faintly while you draw the next one, like tracing paper |

**What to say:** "Today you'll make a flipbook on the computer. Each drawing is one page. Change each drawing only a little, and when we play it, it will move."

## Demo {#demo}

Spend about 10 minutes on the projector. Keep it quick: students will do all of this themselves.

1. **Start Pencil2D** and point out the parts of the window: the canvas in the middle, **Tools** and **Options** on the left, the color panels on the right and the **Timeline** at the bottom. (1 minute; the [Interface chapter]({{ '/doc/manual/interface.html#main-window' | relative_url }}) has the full tour.)
2. **Draw a flower pot and a tiny sprout** with the Pencil (<kbd>N</kbd>). Change color by clicking in the color wheel. Erase a mistake with the Eraser (<kbd>E</kbd>), then undo with <kbd>Ctrl</kbd>+<kbd>Z</kbd>.
3. **Turn on onion skin** with <kbd>O</kbd>. Say: "Now I'll be able to see my last drawing, like tracing paper."
4. **Press <kbd>F7</kbd>.** Point at the timeline: "A new, empty keyframe appeared on frame 2, and I'm on it. The faint drawing is frame 1." Draw the sprout a little taller.
5. **Repeat twice more**, growing a leaf, then a flower.
6. **Play it** with <kbd>Ctrl</kbd>+<kbd>Enter</kbd>, turn on the loop with <kbd>Ctrl</kbd>+<kbd>L</kbd>. Say: "It's very fast. Four drawings at 12 frames per second lasts a third of a second." Change the fps box in the timeline to 4 and play again.
7. **Save it** with <kbd>Ctrl</kbd>+<kbd>S</kbd>, showing the file name and the **Pencil2D Project (\*.pclx)** type.

<!-- SCREENSHOT: Pencil2D main window with a 4-drawing flower flipbook; onion skin showing the previous drawing faintly; timeline with keyframes on frames 1-4 and the fps box set to 4 -->

## Step by Step {#steps}

### Look around {#steps-tour}

1. Start Pencil2D. A new, empty project opens. In the **Timeline** at the bottom there are two layers: **Camera Layer** and **Bitmap Layer**. Click the name **Bitmap Layer** so it's highlighted. You will draw on this layer.
2. Find these panels:
   - **Tools** (top left): the drawing tools. Hover over a button to see its name and shortcut.
   - **Options** (left, under Tools): settings for the tool you're using, such as **Width**.
   - **Onion Skins** (left): settings for seeing other drawings while you draw.
   - **Color Box**, **Color Inspector** and **Color Palette** (right): for choosing colors.
   - **Timeline** (bottom): the layers, the frames and the play buttons.
3. If a panel disappears, open it again from the **Windows** menu, or choose **Windows → Reset Windows** to put everything back.
4. The white rectangle in the middle of the canvas is the **camera frame**. Only what's inside it appears when you export your animation, so keep your drawings inside it.

### Draw and erase {#steps-draw}

5. Click the **Pencil** in the **Tools** panel (or press <kbd>N</kbd>) and draw on the canvas.
6. Change the line thickness with the **Width** slider in the **Options** panel. You can also hold <kbd>Shift</kbd> and drag on the canvas to resize the pencil.
7. Choose a color: click in the ring and then the square of the **Color Box**, or click a color in the **Color Palette**.
8. Click the **Eraser** (or press <kbd>E</kbd>) and rub out part of your drawing. Press <kbd>N</kbd> to go back to the Pencil.
9. Made a mistake? **Edit → Undo** (<kbd>Ctrl</kbd>+<kbd>Z</kbd>) takes back the last step. **Edit → Redo** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Z</kbd>) puts it back.
10. To see your drawing bigger, roll the mouse wheel over the canvas. To move the view, hold <kbd>Space</kbd> and drag. **View → Reset** (<kbd>Ctrl</kbd>+<kbd>H</kbd>) puts the view back to normal.
11. When you've finished experimenting, clear the canvas with **Edit → Clear Frame**.

### Make your flipbook {#steps-flipbook}

Choose a subject: a **flower growing** from a pot, or a **face** that changes from a smile to a surprised "O". Keep it simple.

12. Check that **Bitmap Layer** is still highlighted and that the timeline shows you on frame 1. Draw your first picture: the pot with a tiny sprout, or the smiling face.
13. Turn on onion skin: **View → Onion Skin → Previous** (or press <kbd>O</kbd>).
14. Add a new keyframe: **Animation → Add Frame** (or press <kbd>F7</kbd>, or click the **Add Frame** button next to **Keys:** in the timeline). A new, empty keyframe appears on frame 2 and you are moved onto it. Your first drawing shows faintly underneath.
15. Draw the second picture. Redraw the parts that stay the same and change one thing a little: the sprout grows, the mouth starts to open.
16. Repeat steps 14 and 15 until you have 3–5 drawings.
17. To look at your drawings one by one, press <kbd>.</kbd> (next frame) and <kbd>,</kbd> (previous frame), or click in the row of frame numbers along the top of the timeline, above the frame you want.

> **Tip:** Always press <kbd>F7</kbd> *before* you start a new drawing. If you draw on a frame without a keyframe, Pencil2D may add your lines to the previous drawing instead.

### Play and loop {#steps-play}

18. Press the **Play** button in the timeline, or **Animation → Play** (<kbd>Ctrl</kbd>+<kbd>Enter</kbd>). Playback starts from the frame you're on. Press it again to stop.
19. Turn on the **Loop** button in the timeline, or **Animation → Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>), then play. The animation repeats until you stop it.
20. The box in the timeline that says **12 fps** is the frame rate. Click in it and type 4, then play again. Try 6 and 8. Pick the speed you like best.

<!-- SCREENSHOT: Timeline close-up labelling the frame numbers row, a keyframe block, the Add Frame / Remove Frame / Duplicate Frame buttons next to "Keys:", the Play and Loop buttons and the fps box -->

### Save and open again {#steps-save}

21. Choose **File → Save** (<kbd>Ctrl</kbd>+<kbd>S</kbd>). In the save window, go to your class folder and name the file like `lesson01-flower-yourname`. Leave the type as **Pencil2D Project (\*.pclx)** and click **Save**. The file name now appears in the title bar.
22. Close Pencil2D. If it says "This animation has been modified. Do you want to save your changes?", choose to save.
23. Start Pencil2D again and choose **File → Open** (<kbd>Ctrl</kbd>+<kbd>O</kbd>), or pick your file from **File → Open Recent**. Your flipbook is back, including the frame rate and loop setting.

## Practice Challenge {#challenge}

**Basic:** Finish a flipbook of 4 drawings that loops smoothly. Make the last drawing lead back into the first one, for example a flower that grows and then shrinks, or a face that opens its mouth and closes it again. Save it as `.pclx`.

**Stretch: the blinking face.** Make a face that blinks, with the eyes open most of the time.

1. On frame 1, draw a face with open eyes.
2. Press **Animation → Duplicate Frame** (<kbd>F6</kbd>) three times. You now have four copies of the face on frames 1–4.
3. Go to frame 2 and erase the eyes, then draw them half closed. On frame 3, draw them closed. On frame 4, half closed again.
4. Play it: the face blinks nonstop. Now make it hold the open eyes. Click the keyframe on frame 2 in the Bitmap Layer row to select it, then hold <kbd>Shift</kbd> and click frame 4 to select frames 2–4. Drag the selected blocks to the right so they start on frame 10.
5. Play in a loop at 12 fps. The eyes stay open for frames 1–9, then blink. Try other positions: when does it look most natural?

## Wrap-up {#wrap-up}

Play a few flipbooks on the projector (or have everyone play their loop and walk around the room). Discussion questions:

- Which flipbooks move smoothly, and which jump? What's different about their drawings?
- What happened when you changed 12 fps to 4 fps? Did the drawings change, or only the speed?
- Where have you seen a *hold* in a cartoon: a moment where nothing moves?
- What would you need to make an animation that lasts 10 seconds at 12 fps? (Answer: 120 frames, though not 120 different drawings, as holds can repeat a drawing.)

## Assessment Checklist {#assessment}

| Look for | Met? |
|---|---|
| The flipbook has 3–5 drawings, each on its own keyframe | |
| Each drawing changes a little from the one before | |
| The student can play, stop and loop the animation | |
| The student changed the frame rate and can say what it does | |
| The project is saved as `.pclx` in the right folder with a clear name | |
| The student reopened the file successfully | |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| Nothing appears when I draw | The **Camera Layer** is selected, or the Eraser is active | Click **Bitmap Layer**, press <kbd>N</kbd> for the Pencil |
| Warning: "You are trying to modify a hidden layer!" | The layer is hidden | Click the small round dot at the left of the layer's name so it's filled in again |
| My new drawing was added to the previous one | You drew on a frame without a keyframe | Undo, press <kbd>F7</kbd>, then draw. Or use the [recommended setting]({{ '/doc/course/#recommended-settings' | relative_url }}) |
| I can't see my previous drawing | Onion skin is off | Press <kbd>O</kbd> (**View → Onion Skin → Previous**) |
| An empty frame flashes during playback | An extra blank keyframe was added | Go to it and choose **Animation → Remove Frame** (<kbd>Shift</kbd>+<kbd>F5</kbd>) |
| The canvas is tilted, mirrored or tiny | A view shortcut was pressed (<kbd>R</kbd>, <kbd>Z</kbd>, <kbd>Shift</kbd>+<kbd>H</kbd>, number keys) | **View → Reset** (<kbd>Ctrl</kbd>+<kbd>H</kbd>); for a mirrored view, **View → Horizontal Flip** again |
| A panel disappeared | It was closed or dragged away | **Windows → Reset Windows** |
| The file won't open on another computer, or drawings are missing | It was saved as **Legacy Pencil2D Project (\*.pcl)** | Open it on the original computer and use **File → Save As...** with **Pencil2D Project (\*.pclx)** |
| The animation plays once and stops | Loop is off | Turn on **Loop** (<kbd>Ctrl</kbd>+<kbd>L</kbd>) |

## Going Further {#going-further}

- Make the same flipbook on paper with sticky notes and compare it with the computer version.
- Try the other drawing tools: the **Pen** (<kbd>P</kbd>) makes smooth lines and the **Brush** (<kbd>B</kbd>) makes soft ones. See [Tools]({{ '/doc/manual/tools.html' | relative_url }}).
- Read more about [keyframes and the timeline]({{ '/doc/manual/timeline.html#keyframes' | relative_url }}) and about [saving projects]({{ '/doc/manual/projects.html#saving' | relative_url }}).
- Look up "persistence of vision" and "phenakistiscope": animation toys from the 1800s that work the same way.
- Next lesson: [The Bouncing Ball]({{ '/doc/course/lesson-02.html' | relative_url }}), where timing and spacing make a drawing feel heavy or light.

{% include series-nav.html series=site.data.course %}
