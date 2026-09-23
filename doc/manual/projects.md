---
layout: page
title: Projects and Files
tagline: Creating, opening and saving projects, presets, autosave and crash recovery
comments: false
---

A Pencil2D project holds all your layers, drawings, sounds, palette and playback settings in one file. This chapter explains how to create, open and save projects, what is inside a project file, how presets let new projects start with your own setup, and how autosave and crash recovery protect your work. Read it before you start a long project.

Shortcuts are written in their Windows/Linux form. On macOS, use <kbd>Cmd</kbd> for <kbd>Ctrl</kbd>. On macOS, **Preferences** is in the **Pencil2D** application menu, not the **Edit** menu.

{% include toc.html %}

## Creating a new project {#new-project}

To start a new project, choose **File → New** (<kbd>Ctrl</kbd>+<kbd>N</kbd>). If the current project has unsaved changes, Pencil2D first asks whether to save them (see [Closing and unsaved changes](#closing)).

What the new project contains depends on your [preset settings](#presets):

- **By default**, you get the standard empty project: a **Camera Layer** with an 800 × 600 camera field, a **Bitmap Layer** that is ready to draw on, the default palette, and 12 fps. See [The default project]({{ '/doc/manual/getting-started.html#default-project' | relative_url }}).
- **If you made one of your presets the default**, the new project is a copy of that preset.
- **If Ask on startup is selected**, Pencil2D asks which preset to use (see [Choosing a preset](#choosing-a-preset)).

A new project has no file name until you save it. Its window title shows "Pencil2D v0.7.2".

## Opening projects {#opening}

To open a project, choose **File → Open** (<kbd>Ctrl</kbd>+<kbd>O</kbd>) and select a `.pclx` or `.pcl` file. A progress dialog ("Opening document...") appears while the project loads. Click **Abort** to cancel.

You can also open a project by passing it to Pencil2D from your system, for example with **Open with** in your file manager.

If the file can't be opened, a "Could not open file" dialog explains why and gives links for reporting the problem. If you open a file that Pencil2D isn't allowed to write to, it warns you right away so you can use **File → Save As...** to save somewhere else.

### Recent files {#recent-files}

**File → Open Recent** lists the last 10 projects you opened or saved, with the most recent at the top. Click one to open it. **Clear** at the bottom of the list empties it.

### Opening the last project at startup {#load-last}

To have Pencil2D reopen the project you last worked on every time it starts, go to **Edit → Preferences → Files** and select **Load last active file** under **Startup Settings**. This only applies at startup. **File → New** still uses your default preset.

## Saving {#saving}

- **File → Save** (<kbd>Ctrl</kbd>+<kbd>S</kbd>) saves the project to its current file. If the project has never been saved, it works like **Save As**.
- **File → Save As...** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>) opens the **Save animation** dialog, where you choose a file name, folder and format. From then on, **Save** writes to the new file.

For a new project, the file name suggested the first time is `MyAnimation.pclx` in your home folder. After that, Pencil2D suggests the last file name and folder you used. If you type a name without an extension, `.pclx` is added. After you save, the export dialogs suggest the same folder and base name for exported files.

While Pencil2D saves, a "Saving document..." progress dialog appears. The window title then shows the file path, and the unsaved-changes indicator in the [status bar]({{ '/doc/manual/interface.html#status-bar' | relative_url }}) is grayed out.

### Backup copies while saving {#save-backup}

When you save over an existing `.pclx` file, Pencil2D first copies the old file to a backup next to it, named like `MyAnimation.backup1.pclx`. It deletes the backup once the new file has been written successfully.

If a save fails, an error dialog explains what went wrong. Its **Copy to Clipboard** button copies the technical details, which are useful when you ask for help. The backup file is kept. If you find a `.backup` file next to your project, a save didn't finish. Keep the backup until you have checked that your project opens correctly. A backup is an ordinary project file, so you can open it directly.

> **Note:** Save errors are also written to a log file (`error-<date>.txt`) in a `logs` folder in Pencil2D's application data folder. Attach it if you report a bug.

## File formats {#file-formats}

Pencil2D can save a project in two formats. Choose the format with the file type list in the **Save animation** dialog.

| Format | Description | Use it when |
|---|---|---|
| **Pencil2D Project** (`.pclx`) | A single file containing the whole project | Always, unless you have a specific reason not to |
| **Legacy Pencil2D Project** (`.pcl`) | A project file plus a separate data folder | You need direct access to the frame images, or you work with an old version of Pencil2D |

### Inside a .pclx file {#pclx}

A `.pclx` file is a standard ZIP archive. It contains:

- `main.xml`: the project description, including layers, keyframe positions, camera keyframes, the current frame, frame rate, playback range, and the Pencil2D version that saved it.
- `data/`: one file per keyframe, plus the palette and sounds.
  - Bitmap keyframes are PNG images named `layer.frame.png`. For example, `003.012.png` is frame 12 of the layer whose internal ID is 3 (not necessarily its position in the Timeline).
  - Vector keyframes are `.vec` files with the same naming. Only Pencil2D can read them.
  - `palette.xml` holds the project palette.
  - Sound clips are stored as WAV files. Pencil2D converts every imported sound to WAV with FFmpeg.
- `mimetype`: a tiny file that identifies the archive as a Pencil2D project.

You never need to unpack a `.pclx` file yourself, but you can. Copy it, rename the copy to `.zip` and open it with any ZIP tool. This is useful for recovering drawings from a damaged file (see the [Project File Recovery Guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }})).

### The legacy .pcl format {#pcl}

A `.pcl` project is two things side by side: the `.pcl` file itself, which is the same XML as `main.xml`, and a folder with the same name plus `.data` (for example `MyAnimation.pcl.data`) that holds the keyframe images, palette and sounds.

Always keep the `.pcl` file and its `.data` folder together. If you move, copy or send only the `.pcl` file, your drawings are missing. For this reason `.pclx` is the recommended format. Pencil2D v0.7.2 can open and save both formats. It can also open projects from very old versions of Pencil.

## Presets {#presets}

A **preset** is a saved project that new projects start from. Use presets for a setup you use again and again, for example a particular camera size, frame rate, set of named layers, palette, or a background drawing.

### Creating a preset {#creating-a-preset}

1. Set up a project the way you want new projects to start: add, rename or remove layers, set the camera size in the camera layer's properties, set the fps, load a palette, and so on.
2. Go to **Edit → Preferences → Files**.
3. Click the **+** button ("Saving the current project as a preset"). The current project is saved as a new preset named "Preset 1", "Preset 2" and so on, and the name is ready to edit.
4. Type a name for the preset and press <kbd>Enter</kbd>.

To rename a preset later, double-click its name in the list. To delete one, select it and click **-**. The built-in **Blank** preset is the standard empty project described in [Creating a new project](#new-project).

Presets are stored as `.pclx` files in a `presets` folder in Pencil2D's application data folder. On Windows this is typically `%APPDATA%\Pencil2D\Pencil2D\presets`, on macOS `~/Library/Application Support/Pencil2D/Pencil2D/presets`, and on Linux `~/.local/share/Pencil2D/Pencil2D/presets`.
<!-- VERIFY: these paths follow Qt's QStandardPaths::AppDataLocation for organization "Pencil2D" and application "Pencil2D"; confirm them on each OS. -->

### Choosing the default preset {#default-preset}

In **Edit → Preferences → Files**, select a preset in the list and click **Make Default**. The default preset is shown in bold. **File → New** uses it, and so does startup unless another option is selected.

The **Startup Settings** section has three choices:

| Option | What happens at startup | What **File → New** does |
|---|---|---|
| **Ask on startup** | Pencil2D asks which preset to use | Asks which preset to use |
| **Load default preset** | Opens a new project from the default preset | Uses the default preset |
| **Load last active file** | Reopens the last project you opened or saved | Uses the default preset |

**Load default preset** is selected by default, with **Blank** as the default preset.

### Choosing a preset {#choosing-a-preset}

With **Ask on startup** selected, the **Choose a Preset for your Project** dialog opens when Pencil2D starts and whenever you choose **File → New**. Pick a preset from the list and click **OK**. If you click **Cancel**, no new project is created: you keep the current project, or at startup the standard empty project. In this dialog, the built-in empty project is listed as **Default**. Check **Always use this preset** to make your choice the default and stop the dialog from appearing. This switches the startup setting to use the default preset.

## Autosave {#autosave}

Autosave saves your project automatically after a set number of changes. It is **off** by default.

To turn it on, go to **Edit → Preferences → Files**, and under **Autosave documents**:

- Check **Enable autosave**.
- Set **Number of modifications before autosaving**. The default is 15, and it can be between 4 and 8192. Every action you can undo counts as one modification, for example a stroke, a fill or a move. Adding or moving keyframes creates no undo step, so it doesn't count.

How autosave behaves:

- **If the project has a file**, autosave runs **File → Save**, so it overwrites your project file in place. It uses the same format and the same [backup copy](#save-backup) as a normal save. It doesn't keep a separate autosave copy or older versions.
- **If the project has never been saved**, an **AutoSave Reminder** appears instead: "The animation is not saved yet. Do you want to save now?". Click **Yes** to save (you choose a file name), **No** to be asked again later, or **Never ask again** to stop the reminder until you restart Pencil2D.
- Saving by hand resets the count.

> **Tip:** Autosave overwrites your file, so it can't take you back to an earlier version. For long projects, also use **File → Save As...** now and then to keep numbered copies such as `scene1-v01.pclx` and `scene1-v02.pclx`.

## Crash recovery {#recovery}

While a project is open, Pencil2D keeps a working copy of it in a temporary folder. When Pencil2D closes normally, the working copy is deleted. If Pencil2D crashes, is force-quit, or the computer loses power, the working copy stays behind, and Pencil2D offers to recover it the next time it starts.

### The Restore Project dialog {#restore-dialog}

At startup, Pencil2D looks for projects left behind this way. For each one, it shows a **Restore project** dialog: "Pencil2D didn't close correctly. Would you like to restore the project?", followed by the project's name. The buttons are:

| Button | What it does |
|---|---|
| **Open** | Loads the recovered project |
| **Discard** | Deletes the leftover working copy permanently. You won't be asked about it again. |
| **Cancel** | Skips it for now. You will be asked again the next time Pencil2D starts. |

If recovery works, a "Recovery Succeeded!" message asks you to save immediately. The recovered project has no file name, so **File → Save** opens **Save As**. Save it under a new name, and don't overwrite your original file until you have checked the recovered project. If the working copy is too damaged, you see "Recovery Failed." instead.

Recovery can only restore what Pencil2D had written into its working copy. Drawings changed since the project was last saved or opened may be held only in memory and may not be recovered. Recovery is a safety net, not a replacement for saving often.
<!-- VERIFY: modified bitmap keyframes are kept in memory until save (BitmapImage::unloadFile skips modified images), so the recovered state is roughly the last open/save state. Confirm how much unsaved work 0.7.2 recovery actually restores. -->

### The temporary folder {#temporary-folder}

The working copies are in a `Pencil2D` folder inside your system's temporary folder, for example `%TEMP%\Pencil2D` on Windows. Each project gets a subfolder named after the project with a random suffix, such as `MyAnimation_Y2xD_a1b2c3d4`. An unsaved project uses the name `Default`.

To open this folder, choose **Help → Open Temporary Directory**. Pencil2D warns you first that the folder is meant for its own use. Don't change or delete anything in it while Pencil2D is running. For recovering drawings by hand from this folder or from a damaged project file, see the [Project File Recovery Guide]({{ '/doc/project-file-recovery-guide.html' | relative_url }}).

> **Warning:** Don't run two copies of Pencil2D at the same time. Pencil2D warns you if you try (see [Startup messages]({{ '/doc/manual/getting-started.html#startup-messages' | relative_url }})). Running two copies can cause data loss and confuse crash recovery.

## Closing and unsaved changes {#closing}

When you create a new project, open another project, or quit (**File → Exit**, <kbd>Ctrl</kbd>+<kbd>Q</kbd>) while the current project has unsaved changes, Pencil2D asks: "This animation has been modified. Do you want to save your changes?"

- **Save** saves first, using **Save As** if the project has no file yet. If you cancel the save dialog, Pencil2D doesn't continue.
- **Discard** throws away the changes and continues.
- **Cancel** returns to your project.

To see whether there are unsaved changes, look for the modified marker in the window title or the unsaved-changes indicator in the [status bar]({{ '/doc/manual/interface.html#status-bar' | relative_url }}).

## File size, length and memory {#performance}

Pencil2D can handle long animations, but some habits keep projects fast and files small.

- **Bitmap drawings grow with what you draw.** Each bitmap keyframe is stored as a PNG just large enough to hold its strokes. A stray mark far outside the camera field makes that image, and the file, much larger. Erase stray marks, and don't paint big areas off-screen unless you need them.
- **Held frames cost nothing.** A drawing held for several frames is stored once. Use exposure (holding a keyframe) instead of duplicating the same drawing onto many frames. See [Exposure]({{ '/doc/manual/timeline.html#exposure' | relative_url }}).
- **Imported footage is heavy.** Importing a video, animated GIF or image sequence creates one bitmap keyframe per frame. Import only the range you need, at the size you need. See [Importing and Exporting]({{ '/doc/manual/import-export.html' | relative_url }}).
- **Memory Cache Budget.** Pencil2D keeps recently used keyframe images in memory and unloads the others, reloading them from disk when needed. Set the budget in **Edit → Preferences → General → Advanced → Memory Cache Budget**. The default is 1024 MB, and it can be between 100 MB and 16000 MB. On a computer with plenty of memory, a larger budget makes scrubbing through long animations smoother. On a computer with little memory, lower it. Drawings you have changed but not saved always stay in memory, so saving regularly also frees memory. See [Preferences]({{ '/doc/manual/preferences.html#general' | relative_url }}).
- **Split very long works.** Pencil2D works best with one scene or shot per project. Split long films into several projects, export each one, and join them in a video editor. To reuse layers from one project in another, use **File → Import → Layers from Project file...**.
- **Sound clip limit.** A movie export can include at most 62 sound clips. When a project reaches 63 clips, Pencil2D warns you, and it refuses to export a movie until you remove some. See [Sound]({{ '/doc/manual/sound.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
