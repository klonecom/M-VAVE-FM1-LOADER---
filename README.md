# M-VAVE FM-1 — Patch Bank Utility

**Soundspirate ☠**

A single-file, browser-based utility for transmitting `.syx` patch bank files to the M-VAVE FM-1 over Web MIDI. No install, no build step, no server — open the HTML file (or the hosted page) and go.

---

## Features

- Transmits `.syx` patch bank files to the FM-1 via the Web MIDI API
- Auto-detects the FM-1's MIDI output port when the OS exposes its name
- Validates standard SysEx framing (`F0` … `F7`) before sending and flags anything malformed
- Drag-and-drop or manual file selection
- Built-in **Manual** tab with step-by-step usage instructions
- Runs entirely client-side — no server, no accounts, no data collection

## Requirements

- **Chrome or Edge.** Web MIDI with SysEx access is not supported in Safari or Firefox.
- The FM-1 connected via a USB-MIDI interface (or USB, if the unit exposes a class-compliant MIDI port) before you initialize.
- A secure context — `https://` or `localhost`. The Web MIDI API will not run over plain `http://`. GitHub Pages serves over HTTPS by default, so hosted use is covered automatically.

## Usage

1. Open the tool (locally or at your hosted URL).
2. Click **Initialize Web MIDI** and accept the browser's SysEx permission prompt.
3. Confirm the FM-1 is selected as the output port (it's picked automatically when detected; otherwise choose it from the dropdown).
4. Drag a `.syx` bank file onto the file field, or select one manually.
5. Click **Send Bank To Hardware**.
6. On the FM-1 itself, assign the destination slot to store the incoming bank — the device has no way to confirm receipt automatically.

See the in-app **Manual** tab for the same walkthrough with more detail.

## Disclaimers

- **Unofficial tool.** This project is not affiliated with, endorsed by, or supported by M-VAVE. "M-VAVE" and "FM-1" are used only to identify the hardware this utility targets.
- **Transmit-only, by hardware design.** The FM-1 has no SysEx dump/output capability, so this tool cannot read or back up banks from the device — that's a limitation of the hardware, not the app.
- **No warranty.** This software is provided "as is," with no guarantee it will work correctly with your unit, firmware version, or setup. Use it at your own risk.
- **Back up before you overwrite.** Sending a bank replaces whatever is in the destination slot on the device. If you don't already have your factory or current patches backed up elsewhere, do that first — this tool cannot restore what it overwrites.
- **Malformed data risk.** Sending an invalid or corrupted `.syx` file could put the device into an unexpected state. The built-in framing check catches common issues but is not a full validator of FM-1-specific patch data.
- **No liability.** The author(s) are not responsible for data loss, corrupted patches, or any damage to your hardware resulting from use of this tool.
- **Privacy.** Everything happens locally in your browser via the Web MIDI API. No patch data, file contents, or usage information is collected, stored remotely, or transmitted anywhere.

## License

cc by nc

## Credits

Built by **Soundspirate ☠** (2026)
