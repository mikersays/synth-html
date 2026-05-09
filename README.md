# Pulse Keys — Moog Edition

A browser-based polyphonic synthesizer built entirely as a single HTML file using the Web Audio API. No dependencies, no build step — just open and play.

## Features

### Sound Engine

- **Dual Oscillators** — Saw, square, triangle, and sine waveforms with octave shift (-2 to +2), detune, and level controls
- **Sub Oscillator** — Dedicated oscillator one octave below with selectable waveforms
- **Noise Generator** — White noise with level control for texture and percussion
- **Unison Mode** — Stack 2–7 detuned copies of OSC1 with adjustable spread for thick, wide sounds
- **Moog Ladder Filter** — Custom AudioWorklet implementation with lowpass, highpass, bandpass, and notch modes, resonance up to self-oscillation, and drive saturation (falls back to BiquadFilter when AudioWorklet is unavailable)
- **Filter Envelope** — Dedicated ADSR envelope with depth control for the filter cutoff
- **Key Tracking** — Filter cutoff follows the played note pitch
- **Amp Envelope** — Full ADSR envelope for amplitude shaping
- **LFO** — Sine, saw, square, and triangle modulation routed to pitch, filter cutoff, or amplitude
- **Portamento & Legato** — Smooth glide between notes with optional legato mode that slides pitch without retriggering envelopes
- **Polyphony** — Up to 16 simultaneous voices with voice stealing

### Effects

- **Drive** — Waveshaper distortion with 4x oversampling
- **Chorus** — Modulated delay with rate and mix controls
- **Delay** — Tempo-free delay with feedback and mix
- **Reverb** — Convolution reverb with dynamically generated impulse response, size and mix controls
- **Compressor** — Output dynamics control
- **Anti-aliasing Filter** — 18 kHz brick wall to prevent digital artifacts

### Input

- **Computer Keyboard** — QWERTY piano-style layout across two rows
- **Mouse & Touch** — Click or tap the on-screen 25-key piano with pointer pressure velocity support
- **MIDI In** — Note on/off with velocity, sustain pedal (CC 64), mod wheel (CC 1), pitch bend
- **MIDI Out** — Route notes to external MIDI devices

### Presets & Sharing

- **12 Factory Presets** — Init, Bass Lead, Pad Swells, Arp Pluck, Lead Scream, Warm Strings, Acid House, Organ-ish, Kick Drum, Soft Bell, Vintage Keys, Deep Space
- **Custom Presets** — Save and load from browser localStorage
- **URL Sharing** — Generate shareable links with the full preset encoded in the URL

### Visualization

- **Oscilloscope** — Real-time waveform display
- **Spectrum Analyzer** — Animated frequency bar display

### Recording

- **Audio Capture** — Record the post-effects output and download as WebM

## Getting Started

Open `index.html` in a modern browser. Click **Start Audio** to initialize the audio context, then play.

```
git clone https://github.com/mikersays/synth-html.git
cd synth-html
open index.html
```

Or visit the [live demo on GitHub Pages](https://mikersays.github.io/synth-html/).

## Keyboard Controls

The keyboard uses a piano-style layout across two rows:

```
 S D   G H J        2 3   5
Z X C V B N M  ,  . /  Q W E R
C D E F G A B  C  D E  F G A B
```

Lower row plays white keys, upper row plays sharps/flats. The layout spans two octaves from the current base octave.

| Key | Action |
|---|---|
| `[` / `]` | Shift octave down / up |
| `Space` | Toggle sustain |

## MIDI

Click the **MIDI** button to request Web MIDI access. Connected controllers are detected automatically. The mod wheel (CC 1) controls LFO depth and the sustain pedal (CC 64) works as expected. You can also route note output to MIDI devices using the output selector.

## Browser Support

Requires a modern browser with Web Audio API and Pointer Events. The Moog Ladder filter uses AudioWorklet (Chromium, Firefox 76+, Safari 14.1+) with automatic BiquadFilter fallback. Web MIDI is available in Chromium-based browsers.

## Tech

Everything lives in a single `index.html` file (no build tools, no dependencies):

- **Web Audio API** — Oscillators, gain nodes, filters, waveshapers, convolver
- **AudioWorklet** — Custom Moog Ladder filter processor
- **Web MIDI API** — Hardware controller and output support
- **Canvas API** — Oscilloscope and spectrum analyzer rendering
- **MediaRecorder API** — Audio recording

## License

MIT
