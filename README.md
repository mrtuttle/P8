# P-8 · Semi-modular percussion synthesizer simulator

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
- **16 factory presets** (kick, snare, hi-hats, toms, FM cowbell, acid bass, drone and example patches) and **user presets**, with export and import of the **whole session**.

## Quick start

1. Open the page and tap **▶ Switch on** (browsers only enable audio after a tap).
2. Pick a sound from the **PRESET** menu and press **PLAY/STOP**.
3. **TRIGGER** plays the current step without advancing; **ADVANCE** moves to the next step without playing.
4. To patch a cable, tap an **output** and then an **input**. Tapping an input that is already patched removes the cable.
5. The **?** button opens the full guide.

## Presets and sessions

From the **PRESET** menu:

| Menu item | What it does |
|---|---|
| ＋ Save current sound… | Saves knobs, switches, cables and the 8-step sequence under a name (also with the SAVE button) |
| ★ name | Recalls one of your presets |
| ✕ Delete «name» | Deletes the loaded preset |
| ⇩ Export session | Creates `P8-sessione.json` with your presets and the current sound, including sequence, tempo and scale |
| ⇧ Import session or presets | Adds the presets in the file and, if you confirm, restores the session |

Everything is stored in the browser. The online version and the installed offline version have separate memories: use Export and Import to move between them.

## Offline use (iPhone, iPad, Android)

The simulator is a PWA: after the first visit it also works without a connection.

- **iPhone / iPad (Safari)**: open the page, tap Share → **Add to Home Screen**.
- **Android (Chrome)**: menu ⋮ → **Install app**.

## Compatibility

- Audio: recent Chrome, Edge, Firefox and Safari (AudioWorklet, with an automatic fallback when unavailable).
- MIDI: Chrome and Edge on computers and Android. Safari and every browser on iPhone/iPad do not support Web MIDI.

## Technical notes

The audio engine runs in an AudioWorklet at the full sample rate: polyBLEP anti-aliased oscillators, zero-delay-feedback (ZDF) ladder filter with saturation, exponential decay envelopes, patch bay processed sample by sample.

## Credits

Developed with the assistance of AI. Design choices, testing and final review by the author.
