---
layout: page
title: "Lesson 4: Layers, Line and Color"
tagline: The rough-to-clean-up workflow, color fills under the lines, a palette and a background
comments: false
---

Professional animators rarely draw a finished frame in one go. They sketch loose **roughs** to get the movement right, trace them with **clean lines**, fill in **color** and put everything on a **background**, each on its own layer. In this lesson students take their bouncing ball from Lesson 3 through that whole workflow and learn how layers, layer opacity, the Bucket tool and the color palette work together.

> **Note:** On macOS, use <kbd>Cmd</kbd> wherever this lesson says <kbd>Ctrl</kbd>, and <kbd>Option</kbd> for <kbd>Alt</kbd>. On many laptops, <kbd>F6</kbd> and <kbd>F7</kbd> need <kbd>Fn</kbd> held down.

{% include toc.html %}

## Overview {#overview}

| | |
|---|---|
| **Time** | 75–90 minutes |
| **Level** | Beginner (after Lesson 3) |
| **Animation principle** | Clean line and solid color: making each drawing clear and consistent (rough to clean-up) |
| **Pencil2D skills** | Renaming, ordering, hiding and fading layers; tracing; Bucket fill settings (**Reference**, **Blend mode**, **Expand fill**); building a palette; a held background; bitmap and vector layers |
| **What students make** | The bouncing ball, cleaned up and colored, on a background, exported as a GIF |

## Learning Objectives {#objectives}

By the end of the lesson, students can:

1. Describe the rough, clean-up, color and background stages and why each gets its own layer.
2. Fade a layer with **Layer / Keyframe opacity** and hide or show layers.
3. Trace clean, closed lines over a rough drawing.
4. Fill color on a separate layer under the lines with the Bucket tool, choosing the right **Reference** setting.
5. Build and name a small color palette and use it on every frame.
6. Explain the difference between bitmap and vector layers in one sentence each.

## Before Class {#before-class}

- Students need their Lesson 3 project. Keep a finished bounce ready for anyone who missed it.
- Work through **Step by Step** yourself (about 25 minutes). The Bucket's **Reference** setting is the part students find hardest, so practice explaining it.
- **Optional starter file** (`lesson04-start.pclx`): a bounce with a **Rough** layer already faded to 30 %, and empty **Line**, **Color** and **Background** layers in the right order. It saves about 10 minutes of setup.
- **Optional:** show a still from a cartoon next to its rough sketch (many "art of" books and animation blogs show these) so students see what clean-up means.

## Key Ideas {#key-ideas}

**Layers are like sheets of clear plastic stacked on top of each other.** You can draw on each sheet separately, and what's on a higher sheet covers what's below it. Splitting a drawing into layers means you can change one part without touching the others.

The layer stack for this lesson, top to bottom:

```
Top      Line         clean outlines, drawn by tracing the rough
         Color        flat color, underneath the lines
         Rough        your old ball, faded (hidden at the end)
         Shadow       from Lesson 3
         Ground       the ground line from Lesson 2 (hidden at the end)
         Background   sky and ground: one drawing, held for the whole animation
Bottom   Camera Layer
```

**Rough, then clean up.** Roughs are quick and messy: they're for getting the movement right. Clean-up means tracing each rough with one confident line, with the same thickness on every frame and every shape **closed**, so the Bucket can fill it.

**Color under the lines.** Putting color on its own layer under the lines keeps the lines crisp and lets you change colors without redrawing anything.

**A palette** is a small set of chosen colors. Using the same few colors on every frame stops the color from flickering and makes the animation look designed.

**Bitmap and vector.** A **bitmap** layer stores pixels, like a painting: what you draw is what you get. A **vector** layer stores lines as editable curves that stay sharp when scaled. This course uses bitmap layers. Vector layers are still a work in progress in Pencil2D v0.7.2, and the Pencil2D team recommends avoiding them for serious projects for now.

| Word | Meaning |
|---|---|
| **Layer** | One sheet in the stack. Each has its own keyframes. |
| **Rough** | A quick sketch used to plan the movement |
| **Clean-up** | Tracing roughs into final, clean lines |
| **Opacity** | How see-through something is. 100 % is solid, 0 % is invisible. |
| **Fill** | Coloring an enclosed area in one click, with the Bucket tool |
| **Palette** | The set of colors chosen for a project |
| **Background** | The scenery behind the moving parts |

**What to say:** "Real studios work in layers, like this: rough, clean line, color, background. It's a bit slower at first, but every stage is easy to fix."

## Demo {#demo}

About 12 minutes.

1. **Show the stack.** Open your Lesson 3 ball. Rename **Ball** to **Rough** and fade it to 30 % with **Layer → Layer / Keyframe opacity**.
2. **Trace one frame** on a new **Line** layer. Close every shape. Say: "One line, no scribbles, no gaps."
3. **Add a Color layer** and drag it under Line. Hide the Rough layer.
4. **Fill with the Bucket.** First with **Reference** set to **Current layer**: the whole camera frame fills, because the Color layer has no lines of its own. Undo, switch to **All layers**, click again: now it fills just the ball, under the lines. This mistake is worth showing on purpose.
5. **Build a palette**: add two colors with the **Add Color** button and name them.
6. **Add a Background layer** at the bottom and fill a sky, switching **Reference** back to **Current layer**.

<!-- SCREENSHOT: Options panel for the Bucket tool on a bitmap layer, showing Reference set to "All layers", Blend mode "Overlay", Color tolerance unticked and Expand fill ticked at 2 -->

## Step by Step {#steps}

### Turn the ball into a rough {#steps-rough}

1. **File → Open** your Lesson 3 project and save a copy with **File → Save As...** as `lesson04-ball-yourname.pclx`.
2. Double-click the layer name **Ball**, rename it `Rough` and click **OK**.
3. With **Rough** selected, choose **Layer → Layer / Keyframe opacity**. Under **Set opacity for:** choose **Layer**. Set the value to about 30 % with the slider or the number box, then click **Close**. The rough is now faint.

### Clean lines on a new layer {#steps-line}

4. Choose **Layer → New Bitmap Layer** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>B</kbd>) and name it `Line`. It appears at the top of the list and is selected.
5. Turn onion skin off for now (press <kbd>O</kbd> and <kbd>Alt</kbd>+<kbd>O</kbd>, or untick both groups in the **Onion Skins** panel), so you only see the rough and your new line.
6. Choose the **Pencil** (<kbd>N</kbd>), a dark line color and a **Width** of about 3–5.
7. On frame 1, trace the ball in one clean line. If you like, add a stripe or a simple face so the ball has two or three areas to color. Make sure every shape is **closed**: zoom in with the mouse wheel to check for gaps.
8. Look at the Rough row in the timeline: its keyframes are on frames 1, 3, 5, 7, 9, 11 and 12. For each one, go to that frame, press <kbd>F7</kbd> (the Line layer must be selected), and trace. For frame 12, go to frame 11 and press <kbd>F6</kbd> instead.
9. Keep the stripe or face the same on every frame, so it doesn't jump around.

> **Tip:** The **Pen** (<kbd>P</kbd>) draws smoother lines than the Pencil. Either works with the Bucket. The Pencil's hard-edged lines fill most cleanly.

### A palette for the project {#steps-palette}

10. Choose your first fill color in the **Color Box**. In the **Color Palette** panel, click the **Add Color** button (the plus icon). A new swatch appears at the end of the list with its name ready to edit.
11. Type a name such as `Ball red` and press <kbd>Enter</kbd>. To rename a swatch later, double-click it.
12. Add 2–4 more colors the same way: one for each area of the ball, one or two for the background. The palette is saved inside your `.pclx` project.

### Color under the lines {#steps-color}

13. Add another bitmap layer named `Color`. It appears at the top, above Line. Drag its name down so it sits **directly under Line**.
14. Hide every layer except **Line** and **Color**: click the small round dot at the left of the **Rough**, **Shadow** and **Ground** names so the dots are empty. (The Camera Layer can stay as it is.)
15. Click **Color** to select it, then choose the **Bucket** (<kbd>K</kbd>). In the **Options** panel set:
    - **Reference**: **All layers**. The Bucket then "sees" the lines on the Line layer while it fills the Color layer.
    - **Blend mode**: **Overlay** (the default).
    - **Expand fill**: ticked, at 2 (the default). This pushes the color slightly under the lines so no white gaps show.
    - **Color tolerance**: leave unticked.
16. Go to frame 1, click a swatch in your palette, and click inside each area of the ball. The color appears under the lines. You can also drag across several areas that need the same color.
17. For each of frames 3, 5, 7, 9 and 11: go to the frame, press <kbd>F7</kbd> (with **Color** selected), then fill. On frame 11 press <kbd>F6</kbd> to copy the colors to frame 12.
18. If a fill floods the whole camera frame, undo (<kbd>Ctrl</kbd>+<kbd>Z</kbd>): there is a gap in the line. Click **Line**, close the gap with the Pencil, click **Color** and fill again.

<!-- SCREENSHOT: Timeline for the finished lesson: layers Line, Color, Rough (hidden), Shadow, Ground (hidden), Background, Camera Layer; hidden layers show an empty dot and dimmed row -->

### Background {#steps-background}

19. Add a bitmap layer named `Background` and drag it to the bottom of the list, just above the Camera Layer.
20. Show the **Ground** layer again for a moment, as a guide. On **Background**, frame 1, draw a horizon line at the ground's height and any simple scenery. Keep it inside the camera frame.
21. With the Bucket on the Background layer, set **Reference** to **Current layer**, then fill the sky and ground. (With **All layers**, the ball's lines on frame 1 would cut a ball-shaped hole into the background.)
22. Hide **Ground** again and show **Shadow**. Keep **Rough** hidden. Because the background is one keyframe on frame 1, it stays in place for the whole animation.

### Check and export {#steps-export}

23. Turn on **Loop** and play. Look for flickering colors, lines that jump, or frames with missing color.
24. Save (<kbd>Ctrl</kbd>+<kbd>S</kbd>), then export a GIF as in Lesson 3: **File → Export → Animated GIF...**, **Browse...**, name it `lesson04-ball-yourname.gif`, **OK**. Hidden layers such as Rough are not exported.

## Practice Challenge {#challenge}

**Basic:** Finish the clean line, color and background for the whole bounce, using only colors from your palette. Export the GIF.

**Stretch:** Choose one:

- **Shading:** add a `Shade` layer between Line and Color and fill a darker version of the ball color on the side away from the light. Keep the light coming from the same side on every frame.
- **Clean up your Lesson 1 flipbook** with the same rough, line, color and background workflow.
- **Share your palette:** export it with **File → Export → Palette** and have a partner load it into their project with **File → Import → Replace Palette...**, so you can make matching animations.

## Wrap-up {#wrap-up}

Show a few finished GIFs next to the same student's Lesson 2 rough. Questions:

- What changed between the rough and the finished version? What stayed the same?
- Why is the color on its own layer, under the lines?
- What happened when the Bucket's **Reference** was set to **Current layer** on the Color layer? Why?
- Did anyone's colors flicker? What causes that?
- Where would a studio use this workflow, and why do they split the work into stages?

## Assessment Checklist {#assessment}

| Look for | Met? |
|---|---|
| Layers named Line, Color, Rough and Background, in a sensible order | |
| Rough faded while tracing, and hidden in the final export | |
| Clean, closed lines of even thickness on every frame | |
| Color on its own layer under the lines, with no gaps or leaks | |
| Colors come from a named palette and don't flicker between frames | |
| A background held for the whole animation | |
| The student can explain the **Reference** setting | |
| GIF exported and project saved as `.pclx` | |

## Common Problems {#troubleshooting}

| Problem | Why it happens | Fix |
|---|---|---|
| The fill covers the whole camera frame | There's a gap in the line, or **Reference** is **Current layer** on the Color layer | Close the gap on the Line layer; set **Reference** to **All layers** |
| The fill stops at rough lines or at the ground line | **All layers** uses every *visible* bitmap layer | Hide Rough, Shadow and Ground before filling |
| Color covers the lines | Filled on the Line layer, or Color is above Line | Undo; select **Color**; drag Color below Line |
| A thin white edge between line and color | **Expand fill** is off or too small | Tick **Expand fill**, try 3 or 4 |
| Filling frame 3 changed the color on frame 1 | The Color layer had no keyframe on frame 3 | Undo, press <kbd>F7</kbd> first, then fill |
| New rough drawings are dark, not faded | Layer opacity only affects keyframes that existed when it was set | Set the layer opacity again |
| The rough shows up in the exported GIF | The Rough layer is visible | Hide it (empty dot), export again |
| A ball-shaped hole in the background | The background was filled with **Reference** on **All layers** | Undo; set **Current layer**; fill again |
| Lines or colors jitter during playback | Each frame was traced or colored differently | Trace carefully over the rough; use palette colors only |
| My palette colors are missing in a new project | The palette is saved in each project | **File → Export → Palette**, then **File → Import → Replace Palette...** in the new project |

## Going Further {#going-further}

- Try the Bucket's **Behind** blend mode: it fills *behind* existing lines on the same layer, a quick alternative to a separate Color layer. See [Bucket]({{ '/doc/manual/tools.html#bucket' | relative_url }}).
- Try **View → Layer Visibility → Relative** (<kbd>Alt</kbd>+<kbd>2</kbd>) to fade every layer except the one you're working on. <kbd>Alt</kbd>+<kbd>3</kbd> shows all layers again. See [layer visibility]({{ '/doc/manual/canvas.html#layer-visibility' | relative_url }}).
- Read more about [layer types]({{ '/doc/manual/layers.html#layer-types' | relative_url }}), [layer opacity]({{ '/doc/manual/layers.html#opacity' | relative_url }}) and [the palette]({{ '/doc/manual/color.html#palette' | relative_url }}).
- Save a project with your favorite layer setup as a preset in **Edit → Preferences → Files**, so new projects start with it. See [Presets]({{ '/doc/manual/projects.html#presets' | relative_url }}).
- Next lesson: [The Flour Sack Jump]({{ '/doc/course/lesson-05.html' | relative_url }}), where a character shows weight and anticipation.

{% include series-nav.html series=site.data.course %}
