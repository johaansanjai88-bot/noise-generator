# 🌊 Noise Generator

A browser-based ambient noise generator built with the **Web Audio API**. No dependencies — single HTML file, works offline.

## Features

- **3 Noise Types**
  - **White Noise** — equal energy across all frequencies; great for masking distractions
  - **Pink Noise** — bass-boosted, natural-sounding; popular for focus and sleep
  - **Brown Noise** — deep, rumbling tone; like heavy rain or a waterfall

- **Real-time Oscilloscope** — live waveform display for each noise type

- **EQ Controls**
  - Volume slider
  - Bass shelf filter (±20 dB at 200 Hz)
  - Treble shelf filter (±20 dB at 3 kHz)

- **5 Presets** — Focus, Sleep, Rain, Ocean, Flat

- **Auto-stop Timer** — set 15 min, 30 min, or 1 hour sleep timer with countdown

## Usage

1. Open `index.html` in any modern browser
2. Select a noise color (White, Pink, or Brown)
3. Pick a preset or adjust Bass/Treble manually
4. Click **Start**
5. Optionally set a sleep timer

## How It Works

Noise is generated procedurally using the Web Audio API:
- **White noise** — random samples uniformly distributed between -1 and 1
- **Pink noise** — Paul Kellet's refined algorithm using 7 filter stages to approximate the 1/f power spectrum
- **Brown noise** — integrated white noise (random walk / Brownian motion)

All noise is generated into a 2-second looping `AudioBuffer`, passed through `BiquadFilter` nodes for EQ, then to a `GainNode` for volume control.

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome  | ✅ Full |
| Firefox | ✅ Full |
| Safari  | ✅ Full |
| Edge    | ✅ Full |

## License

MIT
