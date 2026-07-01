# AuraConv‑Multi v3 — 50‑Track Live Block Filter

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Web_Audio_API-4A154B?logo=webaudio&logoColor=white" alt="Web Audio API">
  <img src="https://img.shields.io/badge/AudioWorklet-8A2BE2" alt="AudioWorklet">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License MIT">
  <img src="https://img.shields.io/badge/version-3.0.0-brightgreen" alt="Version">
</p>

**AuraConv‑Multi v3** is a real‑time, multi‑track audio processor that splits a single microphone input into **50 parallel channels**, each with a unique block‑size gate (from 10 samples up to 1 000 000 samples).  
All tracks are mixed through a global convolution reverb, and every track has a **dual‑layer visualiser** (waveform + gate position indicator) so you can see exactly how the block‑size filtering is shaping the sound.

No dependencies – just open the single HTML file in any modern browser and start experimenting.

* Cloudflare Demo - https://auraconv-multi.pages.dev

---

## 🚀 Overview

- **50 independent gate tracks** fed from one live microphone source.
- Each track has a log‑spread block size: 10, 13, 16, 20, …, 501k, 634k, 802k, 1M samples.
- **Global controls**: block duration, invert mode, convolution reverb (decay & dry/wet), master volume.
- **Per‑track mute** with smooth volume ramping.
- **Live visualisation**: real‑time waveform, gate‑overlay bar showing active/silent zones, moving dot for current position, and dB level meter.
- **Dark/light theme** (auto‑saved to localStorage, keyed for v3).
- **Keyboard shortcut** (`Space`) to start/stop audio.
- **Single‑file** – zero build tools, zero dependencies.

---

## 🎛️ Features

### 🎤 Multi‑Track Live Processing
- **50 parallel tracks**, each with its own `AudioWorklet` processor.
- Block sizes span from ultra‑fast 10‑sample chops (0.23 ms latency) to 1M‑sample drones (~22.7 s latency).
- Finely graded logarithmic spread – perfect for rhythmic, textural, and ambient exploration.
- All tracks share a single microphone input – no need for complex routing.

### ✂️ Gate Controls (Global)
- **Block Duration** (1–99%) – percentage of each block that passes audio.
- **Invert Blocking** – swap the silent and active regions, turning a gate into a chopper.
- Parameters are broadcast instantly to all 50 worklets.

### 🌌 Convolution Reverb
- Generated noise‑based impulse response with adjustable **decay** (0.5–12 s).
- **Dry/Wet mix** slider to blend the direct and reverberant signals.
- The impulse response is regenerated whenever decay changes – no clicks or glitches.

### 📊 Dual‑Layer Track Visualisation
Each track card displays:
- **Real‑time waveform** drawn in the track’s unique HSL colour.
- **Gate overlay bar** at the bottom that shows:
  - Highlighted active zone (audio passing).
  - A moving dot that tracks the current position inside the block.
  - The entire bar darkens when the gate is closed (muted).
- **GATE ON / GATE OFF** label with colour glow.
- **dB level indicator** (RMS‑based) updated every frame.

### 🔧 Global Controls
- All controls are placed in a single bar for quick access.
- Each slider shows its current value in real time.
- **Invert** toggle changes appearance and updates all tracks simultaneously.

### 💡 Usability
- Fully responsive grid layout (3 columns on desktop, 2 on mobile).
- Compact track cards with readable labels (e.g., `1.1k`, `25k`, `500k`, `1M`).
- Theme toggle persists between sessions (isolated `localStorage` key for v3).
- Graceful error handling for microphone access.

---

## 🧰 Technology Stack

| Layer                | Technology                          |
|----------------------|-------------------------------------|
| Audio Processing     | Web Audio API, `AudioWorklet`       |
| Visualisation        | HTML5 Canvas (per‑track)            |
| UI                   | Vanilla HTML/CSS/JS, CSS Variables  |
| Storage              | `localStorage` for theme            |
| Build                | None – single self‑contained HTML file |

---

## 🚀 Getting Started

1. **Download** the latest release or clone the repository.
2. **Open `index.html`** in a modern browser (Chrome, Firefox, Edge, Safari).
   > ⚠️ Microphone access requires a secure context (`localhost` or HTTPS).  
   > Use a simple server like `python -m http.server` if opening directly doesn’t work.
3. Click **“Start Audio”** and allow microphone access when prompted.
4. Play with the global sliders and mute/unmute tracks to explore the multi‑layered gate effects.

---

## 📈 What’s new in v3
- **50 tracks** (up from 12) with a logarithmic block‑size progression from 10 to 1 000 000 samples.
- 50 distinct HSL colours for better visual tracking.
- Compact track cards and label formatting (e.g., `1.1k`, `25k`, `500k`, `1M`).
- Optimised canvas height (60 px min) to display all 50 tracks without excessive scrolling.
- Separate theme storage key (`auraconv-multi-v3-theme`) to avoid conflicts with v2.
- Under the hood: all 50 worklets run in parallel, performance remains practical on modern hardware.

---

## 🗺️ Roadmap

Planned improvements – contributions are very welcome!

- [ ] **Per‑track volume & pan** – individual gain and stereo position per track.
- [ ] **Solo buttons** – isolate a single track with one click.
- [ ] **Custom block size assignment** – let users type any value per track.
- [ ] **Per‑track block duration & invert** – independent gate settings for each channel.
- [ ] **Save/load presets** – export the entire configuration as JSON.
- [ ] **Frequency spectrum view** – toggle between waveform and FFT per track.
- [ ] **Audio recording** – capture the master output to a WAV file.
- [ ] **MIDI control** – map parameters to MIDI CC messages.
- [ ] **Native desktop app** – Tauri wrapper for macOS/Windows/Linux.
- [ ] **PWA support** – offline use and mobile installation.

See [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to help.

---

## 🤝 Contributing

Contributions, issues, and feature requests are highly appreciated!

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/amazing-feature`).
3. Commit your changes (`git commit -m 'Add amazing feature'`).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 🙏 Acknowledgements

- Built entirely with the standard **Web Audio API** – no external libraries.
- Inspired by modular synthesis, rhythmic gating effects, and multi‑track audio workstations.

---

<p align="center">
  <sub>Made with ❤️ for sound tinkerers and real‑time audio explorers.</sub>
</p>
