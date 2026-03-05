# Pulse Keys — Moog Edition

A browser-based synthesizer with a fully interactive piano keyboard, built as a single HTML file using the Web Audio API. No dependencies, no build step — just open and play.

## Features

- **Dual Oscillators** — Two independent oscillators with saw, square, triangle, and sine waveforms, octave shift, detune, and level controls
- **Sub Oscillator** — Additional sine/square/triangle sub oscillator for extra low-end
- **Filter** — Lowpass, highpass, and bandpass filters with cutoff, resonance, and a dedicated filter envelope (attack, decay, sustain, release, depth)
- **Amp Envelope** — Full ADSR envelope for amplitude shaping
- **LFO** — Modulation with multiple waveforms and targets (filter cutoff, pitch, amplitude)
- **Portamento** — Smooth glide between notes
- **Effects** — Delay (time, feedback, mix) and reverb (size, mix) with toggle controls
- **Preset System** — Factory presets included, plus save your own to localStorage
- **MIDI Support** — Connect hardware MIDI controllers and output to MIDI devices via Web MIDI
- **Sustain Pedal** — Toggle sustain via UI button or spacebar
- **Octave Control** — Shift the keyboard range up and down
- **Computer Keyboard** — Play notes using your QWERTY keyboard
- **Touch & Mouse** — Click or tap the on-screen piano keys with pointer event support

## Getting Started

Open `index.html` in a modern browser (Chrome, Firefox, Edge). That's it.

```
git clone <repo-url>
cd midi-piano
open index.html
```

## Keyboard Controls

| Key | Action |
|---|---|
| `a`–`l`, `w`–`p`, etc. | Play notes (piano-style layout) |
| `Space` | Toggle sustain |
| Oct -/+ buttons | Shift octave range |

## MIDI

Click the **MIDI** button to request Web MIDI access. Connected controllers will be detected automatically. You can also route output to MIDI devices using the output selector.

## Browser Support

Requires a browser with Web Audio API and Pointer Events support. Web MIDI is available in Chromium-based browsers.

## License

MIT
