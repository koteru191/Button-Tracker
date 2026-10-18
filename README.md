# Button Auto-Clicker

A lightweight Windows app that watches your screen for a button and clicks it the moment it appears. You give it a screenshot of the button (a template), press Start, and it does the rest.
---
### Windows warnings

- **"Windows protected your PC" (SmartScreen):** the app is not code-signed. Click **More info**, then **Run anyway**.
- **Administrator prompt:** the app asks for administrator rights so that hotkeys and clicks work inside games. Click **Yes**.
- **Antivirus false positives:** programs that simulate mouse clicks are sometimes flagged. The full source code is in this repository so you can check it yourself.

---

## Quick start

1. Open the game and get the button on screen (windowed or borderless mode, not exclusive fullscreen).
2. In the app, click **Capture (3s delay)**. The app hides, and after 3 seconds your screen freezes into an overlay.
3. Drag a box tightly around the button. Include the parts that never change (for example a white icon or outline) and leave out parts that animate or change color. Press **Esc** to cancel.
4. Click **Start** (or press **F7**). After the start delay, the app begins scanning and clicking.
5. Press **F6** at any time to stop.

---

## Features

- Template matching that finds the button anywhere on screen
- White-pixel detection, so it still works when the button changes color or is semi-transparent over a moving background
- Scan the full screen or a custom region you draw (faster)
- Adjustable time between clicks, mouse hold time, and start delay
- Rebindable Start and Stop hotkeys (defaults: **F7** start, **F6** stop)
- Optional "return mouse after click"
- All settings saved automatically

---

## Settings

| Setting | What it does |
| --- | --- |
| **Match threshold** | How closely the screen must match the template. Higher is stricter, lower is more tolerant. A good range is 0.50 to 0.65. |
| **White level** | How bright a pixel must be to count as white. Lower it if the button isn't found, raise it if it matches too much. |
| **Time between clicks** | Pause after each click before scanning again. Keep it below the time between button appearances. |
| **Mouse hold time** | How long the mouse button is held down per click. Increase it if the game needs a longer press. |
| **Start delay** | Countdown after pressing Start, so you can switch to the game. |
| **Scan area** | Full screen, or a custom region. A small region scans much faster. |
| **Return mouse after click** | Moves the cursor back to where it was after each click. |
| **Keybinds** | Click a key button, then press the new key or combination. |
| **Always on top** | Keeps the app window above the game. |

Every number setting has a slider and a text box. Type a value and press **Enter**.

---

## Troubleshooting

**The button is never found**
- Recapture the template at the same resolution and window size you play at.
- Lower the match threshold a little, or lower the white level.
- Make sure the game is in windowed or borderless mode.
- Use a tighter template that only contains the parts of the button that never change.

**It clicks the wrong things**
- Raise the match threshold or the white level.
- Select a custom region so it only scans where the button can appear.

**The mouse moves to the button but the game ignores the click**
- Make sure the app is running as administrator (accept the prompt).
- Turn off exclusive fullscreen in the game.
- Increase **Mouse hold time**.
- Some games or their anti-cheat block simulated input. In that case this app can't click in them.

**The hotkeys don't work**
- Run the app as administrator.
- Pick a different key in Settings if another program already uses it.

**Reset everything**
- Close the app and delete `config.json` next to the exe.

---

## Limitations

- Windows only.
- Scans the primary monitor only.
- Left click only.
- The template is pixel-based, so changing the game resolution, window size, or UI scale means capturing a new template.
- Games that lock the cursor (most first-person shooters) usually ignore this kind of input.
---

Licensed under MIT
