# Juno-106 → FM-106

Play [FM-106](https://github.com/PatttF/fm-106) on an M-VAVE FM-1 from a real Roland Juno-106: every note, slider, switch and patch change, live.

**Open it:** https://fatcatstudios-hub.github.io/juno-to-fm106/ (Chrome or Edge, on a computer)

## Setup
1. Plug the FM-1 (running FM-106) into your computer with USB.
2. Juno **MIDI OUT** → your MIDI interface's **MIDI IN**.
3. On the Juno's back, set the **MIDI function** switch to **III** (sends sliders and patches).
4. On FM-106's **MIDI SETUP** page, set **PC IN** to **ON**.
5. Open the page, allow MIDI, pick both ports, press **Start**.

## What it does
- **Notes** go straight through.
- **Sliders and switches** (the Juno's SysEx) are paced: the newest value of each control goes out every 15 ms, and its final value is sent again when it stops. FM-106 takes one SysEx message at a time, so a fast slider move sent raw gets dropped halfway.
- **Patch changes:** FM-106 switches to the same preset number (bank A or B), then loads the Juno's exact panel settings live. The Juno's "store" message is never passed on, so FM-106's saved presets are never overwritten.
- An optional **flicker filter** ignores a worn slider flipping between two values.

One HTML file, no install, no server. MIDI stays on your computer.

## Credits
- FM-106 firmware by [PatttF](https://github.com/PatttF/fm-106).
- Made by [Fat Cat Studios](https://github.com/fatcatstudios-hub). MIT licence.

Not affiliated with Roland or M-VAVE. Juno-106 is a trademark of Roland Corporation.
