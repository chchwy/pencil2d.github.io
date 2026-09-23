---
layout: page
title: Command-Line Interface
tagline: Export projects from a terminal or a script, without opening the main window
comments: false
---

Pencil2D can export a project to an image sequence, a movie or an animated GIF from the command
line, without opening its main window. This is handy for exporting many projects at once, or for
re-exporting automatically after you change a project. This page lists every option and shows
examples for Windows, macOS and Linux.

{% include toc.html %}

## Usage {#usage}

```
pencil2d [options] [input]
```

`input` is the path to a Pencil2D project (`.pclx` or `.pcl`). Without `-o`, Pencil2D
starts as usual and opens that project in the main window. With one or more `-o` options, it
exports the project and quits without showing the main window.

## Options {#options}

| Option | What it does | Default |
|---|---|---|
| `-o`, `--export <output_path>` | Render the file to `<output_path>`. Repeat it to export several files in one run | None (opens the main window) |
| `--camera <layer_name>` | Name of the camera layer to use | The first camera layer |
| `--width <integer>` | Width of the output frames | Camera width |
| `--height <integer>` | Height of the output frames | Camera height |
| `--start <frame>` | The first frame you want to include in the exported movie | 1 |
| `--end <frame>` | The last frame to include. Can also be `last` or `last-sound` | `last` |
| `--transparency` | Render transparency when possible | Off |
| `-h`, `-?`, `--help` | Displays help on commandline options | |
| `--help-all` | Displays help including Qt specific options | |
| `-v`, `--version` | Displays version information | |

Details:

- **`--camera`**: if no camera layer has that name, Pencil2D prints a warning and uses the first
  camera layer, the lowest one in the layer list. Names are case-sensitive; put names with spaces
  in quotes.
- **`--width`, `--height`**: the camera view is stretched to fill the size you give. If you set
  only one of them, or change them by different amounts, the picture is distorted. Change both
  by the same percentage. A value that isn't a whole number is ignored with a warning.
- **`--start`**: must be 1 or higher; anything else is ignored with a warning.
- **`--end`**: `last` means the last keyframe in the project, and `last-sound` means the frame
  where the last sound clip ends. These are the same as the defaults in the export dialogs; see
  [Camera, Resolution and Range]({{ '/doc/manual/import-export.html#export-options' | relative_url }}). If `--end` is
  smaller than `--start`, Pencil2D warns you and exports only the start frame.
- **`--transparency`**: works for PNG, TIFF and WebP image sequences. It is ignored for JPG and
  BMP, and not supported for movies and GIFs from the command line (you get a warning).

`--export-sequence <output_path>` is also accepted as an older spelling of `--export`. It isn't
listed in `--help`.

## Output Formats {#output-formats}

The extension of each output path decides what gets exported:

| Extension | Result |
|---|---|
| `.png`, `.jpg`, `.jpeg`, `.tif`, `.tiff`, `.bmp`, `.webp` | Image sequence, one file per frame |
| `.mp4`, `.avi`, `.webm`, `.apng` | Movie |
| `.gif` | Animated GIF |

If the extension is missing or not in this list, Pencil2D prints *Warning: Output format is not
specified or unsupported. Using PNG.* and exports a PNG image sequence.

**Image sequences** are named like the ones exported from the app: the frame number, padded to
four digits, is added before the extension. `-o shots/walk.png` produces `shots/walk0001.png`,
`shots/walk0002.png`, and so on. The folder must already exist.

> **Note:** Use `.tiff` rather than `.tif`, and `.jpg` rather than `.jpeg`. Pencil2D always writes
> TIFF frames with a `.tiff` extension and JPEG frames with `.jpg`, so `-o walk.tif` gives oddly
> named files such as `walk.tif0001.tiff`.

**Movies and GIFs** are made with FFmpeg, like the movie export in the app, and use the project's
frame rate. Sound from visible sound layers is included in MP4, AVI and WebM files. A few
differences from the app:

- GIF and APNG files exported from the command line **play once**; there is no loop option.
- There is no transparency for movies or GIFs.
- Pencil2D doesn't check MP4 sizes on the command line. Use an even `--width` and `--height`
  for MP4, or the export fails.

For everything else about the formats, see
[Importing and Exporting]({{ '/doc/manual/import-export.html#export-movie' | relative_url }}).

## Examples by System {#examples}

Replace the paths with your own. Quote any path that contains spaces.

### Windows {#windows}

`pencil2d.exe` is in the folder you extracted Pencil2D to; the examples use
`C:\Pencil2D\pencil2d.exe`. It's a windowed program, so a console doesn't wait for it and doesn't
show its messages unless you pipe its output. In PowerShell, add `| Out-Host`:

```powershell
& "C:\Pencil2D\pencil2d.exe" "D:\Animations\walk.pclx" -o "D:\Animations\walk.mp4" | Out-Host
```

Export frames 1–24 at 1920×1080 as PNGs with a transparent background:

```powershell
& "C:\Pencil2D\pencil2d.exe" "D:\Animations\walk.pclx" -o "D:\Animations\frames\walk.png" --start 1 --end 24 --width 1920 --height 1080 --transparency | Out-Host
```

In Command Prompt (cmd), use `start /wait` so the command finishes before the next one starts:

```bat
start "" /wait "C:\Pencil2D\pencil2d.exe" "D:\Animations\walk.pclx" -o "D:\Animations\walk.gif"
```

Run without piping, `--help` and `--version` show their text in a message box.
<!-- VERIFY: message box behavior comes from Qt's QCommandLineParser on Windows GUI-subsystem apps; confirmed only that output goes to stdout when redirected. -->

### macOS {#macos}

The program is inside the app bundle:

```bash
/Applications/Pencil2D.app/Contents/MacOS/pencil2d ~/Animations/walk.pclx -o ~/Animations/walk.mp4
```

### Linux {#linux}

Make the AppImage executable once, then run it with the same options:

```bash
chmod +x pencil2d-linux-amd64-v0.7.2.AppImage
./pencil2d-linux-amd64-v0.7.2.AppImage ~/Animations/walk.pclx -o ~/Animations/walk.mp4
```

If you installed Pencil2D from Flathub, use `flatpak run org.pencil2d.Pencil2D` in place of the
program name. If you installed it from your distribution, run `pencil2d`.

### Several Outputs at Once {#multiple-outputs}

Repeat `-o` to export several formats from one run:

```bash
pencil2d walk.pclx -o walk.mp4 -o walk.gif -o frames/walk.png
```

## Batch Export {#batch-export}

To export every project in a folder to MP4, PowerShell:

```powershell
$p2d = "C:\Pencil2D\pencil2d.exe"
Get-ChildItem "D:\Animations\*.pclx" | ForEach-Object {
    $out = Join-Path $_.DirectoryName ($_.BaseName + ".mp4")
    & $p2d $_.FullName -o $out | Out-Host
    if (-not (Test-Path $out)) { Write-Warning "Export failed: $($_.Name)" }
}
```

macOS or Linux (bash or zsh):

```bash
P2D=/Applications/Pencil2D.app/Contents/MacOS/pencil2d   # or the path to your AppImage
for f in ~/Animations/*.pclx; do
  "$P2D" "$f" -o "${f%.pclx}.mp4"
  [ -f "${f%.pclx}.mp4" ] || echo "Export failed: $f"
done
```

> **Close Pencil2D before a batch export.** If Pencil2D is already running, every command-line
> run first shows the warning *An instance of Pencil2D is already open*. Click **Open** to
> continue the export or **Close** to skip it.

## Messages and Exit Status {#exit-status}

While it works, Pencil2D prints *Exporting image sequence...* or *Exporting movie...* for each
output, then *Done.* Warnings and errors go to the error output.

The program exits with:

- **0** when it has processed all outputs, or when you clicked **Close** in the
  *already open* warning.
- **1** when no input file was given with `-o`, or the project couldn't be opened. The reason is
  printed to the error output.

An exit status of 0 doesn't prove the files were written. Problems during the export itself, such
as a missing output folder, missing FFmpeg or an odd MP4 size, are not reported in the exit
status, and *Done.* is still printed. Check that the output files exist, as the batch examples
above do. If a movie fails, see the
[Video Export Troubleshooting Guide]({{ '/doc/video-export-troubleshooting-guide.html' | relative_url }}).

{% include series-nav.html series=site.data.manual %}
