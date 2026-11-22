# P-8 · Semi-modular Percussion Synth Simulator

*English · [Italiano](README.it.md)*

A browser simulator of a semi-modular percussion synthesizer laid out like the Behringer Edge: two oscillators, ladder filter, three decay envelopes, 8-step sequencer and patch bay. It runs on computers, tablets and phones, and also **offline** as an installed app.

> Unofficial project, not affiliated with Behringer / Music Tribe. "Behringer" and "Edge" are trademarks of their respective owners and are mentioned only to describe the instrument the layout is based on. Graphics, code and sounds are original.

> The interface is in English, with an **IT** button in the header to switch to Italian (the choice is remembered). Panel labels use the same names as the hardware.

## Features

- **Two oscillators** (pulse / triangle), ±5 octaves each, with FM from OSC 1 to OSC 2 and **hard sync**.
- **Noise** white or pink, with external audio input.
- **4-pole ladder filter**: low-pass and high-pass, 20 Hz – 20 kHz, resonance up to self-oscillation (808-style kicks).
- **Three decay envelopes** (pitch, filter, VCA) with bipolar amounts; VCA attack FAST about 1 ms, SLOW 100 ms.
- **8-step sequencer** with PITCH and VELOCITY rows (0–5 V), tempo from 10 to 10,000 BPM: above roughly 2,000 BPM it becomes an audible oscillator.
- **SEQ PITCH MOD** to OSC 1 & 2, off, or OSC 2 only.
- **Clock** internal, external (ADV/CLOCK) or MIDI, with divisions from 1/4 to 1/32T (SCALE).
- **Full patch bay** with internal connections: a cable in an input jack replaces or adds to the internal signal, as described in the in-app guide.
- **MIDI** in/out via Web MIDI (channel, THRU, notes; receives and sends MIDI clock with start/stop).
- **On-screen keyboard** and computer keyboard (A W S E D F …, Z/X for octave, space = PLAY).
- **Effects pedalboard** (FX button, below the keyboard): the nine effect types found in Vital — overdrive, compressor, filter (LP/BP/HP with LFO, free or synced), EQ, chorus, flanger, phaser, delay (free or synced to the sequencer tempo) and reverb. Add the ones you want from the «＋ Add effect» menu, remove them with ×, reorder by dragging the name or with ◀ ▶; each pedal has its own footswitch and LED; settings and order are remembered.
- **16 factory presets** (kick, snare, hi-hats, toms, FM cowbell, acid bass, drone and example patches) and **user presets**, with export and import of the **whole session**.

## Quick start

1. Open the page and tap **▶ Switch on** (browsers only enable audio after a tap).
2. Pick a sound from the **PRESET** menu and press **PLAY/STOP**.
3. **TRIGGER** plays the current step without advancing; **ADVANCE** moves to the next step without playing.
4. To patch a cable, tap an **output** and then an **input**. Tapping an input that is already patched removes the cable.
5. The **?** button opens the full guide.

## MIDI controller and recording

- **MIDI LEARN** (computer, Chrome or Edge): open **MIDI**, press *Assign knobs and switches (MIDI LEARN)*, click a knob, switch, pedal knob, footswitch or SYNC, then move a knob/fader or press a button on your controller. Purple badges show the assigned CC or note. *Remove assignment* frees the selected control, *Clear all* removes every assignment, Esc or *Done* exits. Assignments are saved in the browser automatically; *Export/Import assignments* in the MIDI window saves them to a .json file, and *Export session* includes them together with the effects.
- Knobs and faders set the value directly; buttons (momentary or toggle, CC or note) flip switches and pedals on/off.
- If your controller has several modes, choose its user/custom mode, where knobs send standard CC messages; modes made for a specific DAW may send nothing usable.
- The **MIDI MONITOR** in the MIDI window shows the connected ports and the last messages received: use it to check that your controller is sending.
- **● REC** (or the **R** key) records the final output, effects included, and saves it as a WAV file. Files go to the Downloads folder; in Chrome and Edge on a computer the **📁** button next to REC lets you choose another folder, where recordings are then saved automatically (click 📁 again to change it or go back to Downloads).

## Presets and sessions

From the **PRESET** menu:

| Menu item | What it does |
|---|---|
| ＋ Save current sound… | Saves knobs, switches, cables and the 8-step sequence under a name (also with the SAVE button) |
| ★ name | Recalls one of your presets |
| ✕ Delete «name» | Deletes the loaded preset |
| ⇩ Export session… | Saves a session file named with date and time (e.g. `P8-session-2026-11-22-2135.json`). In Chrome and Edge on a computer the system *Save as* window lets you choose folder and name; elsewhere you can edit the name and the file goes to Downloads. A window lets you choose what to include (everything by default): user presets, current sound with sequence, tempo and scale, effects, MIDI assignments. Importing restores only the parts contained in the file |
| ⇧ Import session or presets | Adds the presets in the file and, if you confirm, restores the session |

Everything is stored in the browser. On iPhone and iPad the installed app has its own memory, separate from Safari: use Export and Import to move between them.

## Installing the app and offline use

The simulator is a PWA: after the first visit it also works without a connection.

- **iPhone / iPad (Safari)**: open the page, tap Share → **Add to Home Screen**.
- **Android (Chrome)**: menu ⋮ → **Install app**.
- **Computer (Chrome or Edge)**: click the install icon at the right of the address bar, or menu ⋮ → **Install**. The app opens in its own window.

When a new version is available, it is downloaded automatically the next time you open the app while online.

## Compatibility

- Audio: recent Chrome, Edge, Firefox and Safari (AudioWorklet, with an automatic fallback when unavailable).
- MIDI: Chrome and Edge on computers and Android. Safari and every browser on iPhone/iPad do not support Web MIDI.

## Credits

Developed with the assistance of AI. Design choices, testing and final review by the author.
