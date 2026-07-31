# Comic-book-lettering-tool
This is a productivity enhancer tool for comic artists using Adobe Illustrator. It's a plug-in for Illustrator that automatically creates bubble wraps for your chosen text. You can edit font, font appearance and bubble appearance as well. 
# Ellipse Text — Adobe Illustrator CEP Plugin

A comic lettering panel for Adobe Illustrator that places any text, centre-aligned, inside an ellipse (speech balloon) shape. Text wraps naturally to the curve in a single continuous, editable text frame.

![Illustrator version](https://img.shields.io/badge/Illustrator-CC%202024%2B-orange)
![CEP version](https://img.shields.io/badge/CEP-6.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## Features

- Types text into a single area-text frame shaped to an ellipse
- Centre-aligned horizontally and vertically by default
- Configurable ellipse size, font, font size, and line spacing
- Colour pickers for text, balloon fill, and stroke
- Optional balloon shape drawn behind the text
- Everything placed as a grouped, fully editable object on the artboard

---

## Requirements

- Adobe Illustrator CC 2024 or later (tested on version 29.x)
- Windows or macOS

---

## Installation

### Step 1 — Unlock unsigned extensions

CEP extensions must be unlocked before Illustrator will load them. This is a one-time step.

**Windows** — open PowerShell as Administrator and run:

```powershell
reg add "HKEY_CURRENT_USER\Software\Adobe\CSXS.9"  /v PlayerDebugMode /t REG_SZ /d 1 /f
reg add "HKEY_CURRENT_USER\Software\Adobe\CSXS.10" /v PlayerDebugMode /t REG_SZ /d 1 /f
reg add "HKEY_CURRENT_USER\Software\Adobe\CSXS.11" /v PlayerDebugMode /t REG_SZ /d 1 /f
reg add "HKEY_CURRENT_USER\Software\Adobe\CSXS.12" /v PlayerDebugMode /t REG_SZ /d 1 /f
```

**macOS** — open Terminal and run:

```bash
defaults write com.adobe.CSXS.9  PlayerDebugMode 1
defaults write com.adobe.CSXS.10 PlayerDebugMode 1
defaults write com.adobe.CSXS.11 PlayerDebugMode 1
defaults write com.adobe.CSXS.12 PlayerDebugMode 1
```

### Step 2 — Copy the plugin folder

Copy the entire `illustrator-ellipse-text` folder into Adobe's CEP extensions directory.

**Windows:**
```
C:\Program Files (x86)\Common Files\Adobe\CEP\extensions\
```
> Tip: paste this path directly into File Explorer's address bar. Create the `CEP\extensions` folders if they don't exist.

**macOS:**
```
~/Library/Application Support/Adobe/CEP/extensions/
```
> Tip: in Finder press `Cmd + Shift + G` and paste the path above.

The final structure should look like this:
```
CEP/extensions/illustrator-ellipse-text/
├── CSXS/
│   └── manifest.xml
├── css/
│   └── styles.css
├── js/
│   ├── CSInterface.js
│   └── main.js
├── jsx/
│   └── ellipse.jsx
└── index.html
```

### Step 3 — Open the panel

Restart Illustrator, then go to:

**Window → Extensions → Ellipse Text**

---

## Usage

1. Open any Illustrator document.
2. Open the panel via **Window → Extensions → Ellipse Text**.
3. Type your lettering text in the **Content** field — words wrap automatically to fit the ellipse shape.
4. Set the **Width** and **Height** of the ellipse in pixels.
5. Enter a **font PostScript name** (see tip below).
6. Adjust **size**, **line gap**, and colours as needed.
7. Toggle **Draw ellipse / balloon shape** to show or hide the balloon behind the text.
8. Click **PLACE TEXT**.

The result is placed as a group called **"Ellipse Text"** centred on the active artboard, ready to move, scale, or edit.

---

## Finding a font's PostScript name

Illustrator requires the PostScript name of a font, not its display name.

To find it: place a text frame in Illustrator with your chosen font active, then go to **Type → Find/Replace Font**. The PostScript name appears in brackets next to the font, for example `[Bangers-Regular]`. Use that exact string in the Font field.

Common comic lettering fonts:

| Display name | PostScript name |
|---|---|
| Bangers | `Bangers-Regular` |
| Comic Neue Bold | `ComicNeue-Bold` |
| Arial Bold | `Arial-BoldMT` |

---

## Tips for comic lettering

- Type in **ALL CAPS** for a classic balloon look.
- A stroke width of **2–3 pt** on a **300 px wide** balloon looks natural at print resolution.
- After placing, the text frame inside the group is fully editable — double-click to edit the text or adjust character styles directly in Illustrator.
- To make a thought bubble, draw a custom cloud path over the ellipse after placing.
- The ellipse and text group can be freely scaled; use **Object → Transform → Scale** with **Scale Strokes & Effects** ticked to keep stroke width proportional.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Panel missing from Window → Extensions | Confirm the PlayerDebugMode registry keys were set and Illustrator was fully restarted. |
| "No active document" error | Open a document in Illustrator before clicking Place Text. |
| Font not applied | Double-check the PostScript name using Type → Find/Replace Font. |
| Text overflows the ellipse | Reduce font size, increase ellipse dimensions, or shorten the text. |

---

## License

MIT — free to use, modify, and distribute.
