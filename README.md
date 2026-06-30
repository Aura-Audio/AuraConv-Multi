# AuraConv‑Multi — Multi‑Track Live Block Filter

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Web_Audio_API-4A154B?logo=webaudio&logoColor=white" alt="Web Audio API">
  <img src="https://img.shields.io/badge/AudioWorklet-8A2BE2" alt="AudioWorklet">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License MIT">
</p>

**AuraConv‑Multi** is a real‑time, multi‑track audio processing tool that splits a live microphone input into **nine parallel channels**, each applying a different AuraConv block‑size filter.  
Every track runs its own `AudioWorklet` processor, so you can hear (and see) exactly how a 10‑sample gate differs from a 100,000‑sample gate – all at the same time.  
A global convolution reverb, dry/wet mix, and per‑track mute controls make it a powerful playground for rhythmic chopping, drone layering, and sound design experimentation.

---

## Overview

AuraConv‑Multi takes a single microphone source, duplicates it across nine independent signal chains, and processes each copy with a distinct **block‑length gate** (10, 50, 100, 500, 1k, 5k, 10k, 50k, 100k samples).  
All tracks are summed together through a shared convolution reverb and master gain stage.  

The interface displays a **real‑time waveform** for every track, colour‑coded by block size, plus a dB level indicator – so you can immediately see the rhythmic texture each filter creates.

Everything runs in the browser with **zero dependencies** – just open `index.html` and start experimenting.

---

## Features

### 🎤 Multi‑Track Live Processing
- **9 independent tracks** – all fed from the same microphone input.
- Each track uses a dedicated `AudioWorklet` processor with a fixed block‑length gate: 10, 50, 100, 500, 1k, 5k, 10k, 50k, and 100k samples.
- **Per‑track mute** – instantly silence or restore any track without affecting others.

### ✂️ Block Filter Parameters (Global)
- **Block Duration** (1–99 %) – how much of each block is silenced.
- **Invert Blocking** – swap the silent and live portions of each block, turning a gate into a chopper.

### 🌌 Spatial & Ambience
- **Convolution Reverb** – generated decaying‑noise impulse response with adjustable decay (0.5–12 s).
- **Dry/Wet Mix** – blend the direct signal with the reverberant tail.

### 📊 Real‑Time Visualisation
- **Per‑track waveform** canvas – each track’s output is drawn in real time.
- **Colour‑coded tracks** – from cyan (10 sp) to purple (100k sp) for instant identification.
- **dB level indicator** on each track, showing current signal strength.

### 🎛️ Intuitive Controls
- **Global sliders** for duration, decay, dry/wet, and master volume.
- **Dark / Light theme** with persistent preference.
- **Keyboard shortcut** (`Space`) to start/stop the audio engine.
- **Single‑file HTML** – no build tools, no npm, no hassle.

---

## 🚀 Getting Started

1. **Clone or download** the repository:
   ```bash
   git clone https://github.com/your-username/auraconv-multi.git
   ```
2. **Open `index.html`** in a modern browser (Chrome, Firefox, Edge, Safari).
   > ⚠️ Microphone access requires a secure context (`localhost` or HTTPS).  
   > Use a simple local server (e.g., `python -m http.server`) if opening the file directly doesn’t work.
3. Click **“Start Audio”** and allow microphone access.
4. Adjust the global controls and mute individual tracks to explore the effect of different block sizes.

---

## 🧰 Technology Stack

| Layer               | Technology                          |
|----------------------|-------------------------------------|
| Audio Processing     | Web Audio API, `AudioWorklet`       |
| Visualisation        | HTML5 Canvas                        |
| UI                   | Vanilla HTML/CSS/JS, CSS Variables  |
| Storage              | `localStorage` for theme preference |
| Build                | None – pure single‑file HTML        |

---

## 🗺️ Roadmap

Planned enhancements – contributions are very welcome!

- [ ] **Custom Block Sizes** – let users assign any block size to each track.
- [ ] **Solo Mode** – listen to one track in isolation with a single click.
- [ ] **Pan & Spatialisation** – independent stereo panning per track.
- [ ] **Per‑Track Effects** – add filters (LP/HP/BP), delay, or distortion to individual channels.
- [ ] **Preset Management** – save/load full session configurations.
- [ ] **Audio Recording** – capture the master output to WAV/MP3.
- [ ] **Spectrum Analyser** – switch waveform view to frequency spectrum per track.
- [ ] **MIDI Mapping** – control mutes, volume, and parameters via MIDI.
- [ ] **Custom Impulse Responses** – upload your own IR files for the reverb.
- [ ] **Responsive Mobile Layout** – optimised experience on phones and tablets.

---

## 🤝 Contributing

Contributions, issues, and feature requests are highly appreciated!

1. Fork the repo.
2. Create a feature branch (`git checkout -b feature/amazing-idea`).
3. Commit your changes (`git commit -m 'Add amazing idea'`).
4. Push to the branch (`git push origin feature/amazing-idea`).
5. Open a Pull Request.

Please make sure your code follows the existing style and is well tested.

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
