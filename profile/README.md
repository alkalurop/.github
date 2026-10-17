# Alkalurops

> **Real-time, zero-latency generative visual infrastructure for live performance.**  
> Open-source (Apache 2.0) edge AI running alongside your DAW on a single laptop — no audio dropouts, no cloud reliance, no enterprise media server hardware required.

---

## Technical Context and Competitive Landscape

Live audio-visual performance currently faces a clear structural bottleneck across available toolsets:

1. **Pre-rendered video loops (Resolume, VDMX):** Reliable and industry-standard, but inherently static. Content playback remains fixed regardless of spontaneous live audio changes.
2. **Procedural shaders (Photism, Sphere V3):** Highly reactive to FFT peaks and amplitude, but limited to 2D geometric patterns and fixed visual ceilings.
3. **Enterprise 3D & Node Graphs (TouchDesigner, Notch, Custom UE5 Rigs):** Powerful output, but requires steep technical expertise, dedicated VJ operators, and high-cost hardware setups.

**Alkalurops bridges this gap:** A lightweight, local edge-AI pipeline that converts live DAW performance metrics into generative AI diffusion frames, composited directly inside Unreal Engine 5 in real time.

---

## Technical Features & Execution

- **Zero-Latency Audio Modulation:** Connects locally over UDP (OSC / MIDI) to map live audio stems, BPM, FFT frequency bands, and performance metrics directly into model parameter weights.
- **Local Edge Inference:** Executes distilled diffusion models (SDXL Turbo, LCM, Flux.1) locally using PyTorch accelerated via Apple Metal Performance Shaders (MPS `--force-fp16`) or PC GPUs.
- **Zero-Copy Shared Memory Passing:** Streams generated latent frames (e.g., 512x512) via Syphon (macOS) or NDI (Windows) directly into Unreal Engine 5 materials without disk I/O overhead.
- **Stage Safety Architecture:** Composites live generative AI textures with UE5’s deterministic lighting, volumetric fog, and Niagara particle systems to preserve system stability and prevent stage output dropouts.

---

## Ecosystem Comparison

| Tool / Category | Core Engine | Audio Reactivity | Generative AI? | Visual Depth / 3D? | Target Market & Cost |
| :--- | :--- | :--- | :---: | :---: | :--- |
| **Alkalurops** | **ComfyUI + Unreal Engine 5 (Syphon/NDI)** | **Deep OSC / Stems / FFT / MIDI** | **Yes (Live Local)** | **Yes (UE5 Engine)** | **Open Source Core / Single-laptop rig** |
| **Resolume / VDMX** | DXV/HAP Video Layer Mixer | FFT / BPM / MIDI | No | No | €299–€799 (Pre-rendered playback) |
| **DAW Plugins** *(Sphere, Photism)* | GLSL Procedural Shaders | FFT / Peak Analysis | No | Basic 3D | $30–$100 (Bedroom producer tier) |
| **TouchDesigner** | GPU Operator Graphs | Comprehensive OSC / DMX | Custom Python | Yes | $600–$2,200 (Commercial/Pro licensing) |
| **Notch / Enterprise** | Node-based 3D / VFX Engine | Live Audio / Depth Cams | No | Yes | $1,400–$2,500/yr (Windows/NVIDIA) |

*Note: Alkalurops is engineered to complement existing workflows. It can output live AI textures directly into Resolume, TouchDesigner, or MadMapper via Syphon/Spout/NDI.*

---

## System Architecture

```
[ Live DAW / DJ Software (Ableton, Traktor) ]
                     │
                     │  (OSC / MIDI over UDP)
                     ▼
       [ ComfyUI Edge AI Pipeline ]
  (PyTorch + MPS / TensorRT + SDXL Turbo)
                     │
                     │  (Live Video Stream via Syphon / NDI)
                     ▼
     [ Real-Time Engine (UE5 / TouchDesigner) ]
     (3D Scene, Dynamic Lights, Niagara FX)
                     │
                     ▼
            [ Live Stage Output ]
```

---

## Ecosystem Repositories & Tools

Beyond the core graphics engine, the **ixamal** toolset provides the audio routing, track intelligence, crate management, and stem separation modules that drive the real-time visual system.

### 🎛️ [ixamal/ix](https://github.com/ixamal/ix) — *The Performance Bridge*
* **For DJs & Producers:** The central nervous system for your live set. `ix` taps into your DAW or DJ deck in real time, translating every beat, drop, filter sweep, and stem channel into clean data streams your visual rig can understand automatically.
* **Developer Notes:** High-throughput UDP OSC daemon written for sub-millisecond event dispatching. Handles client registration, event loop isolation, and custom OSC schema mapping between DJ software and edge inference nodes.

---

### 🔊 [ixamal/stems](https://github.com/ixamal/stems) — *Real-Time Stem Separation & Demux*
* **For DJs & Producers:** Instantly isolate drums, bass, vocals, and synths on the fly. Isolating stems gives your visuals surgical accuracy—letting your lighting react solely to the vocal channel while the background 3D stage pumps to the kick drum.
* **Developer Notes:** Python/C++ wrapper optimized for local GPU tensor acceleration (Metal / CUDA). Takes incoming multi-channel audio feeds, extracts dynamic stem stems using fast neural audio separation, and outputs separate RMS/FFT streams per channel.

---

### 📦 [ixamal/crate](https://github.com/ixamal/crate) — *Smart Track & Metadata Vault*
* **For DJs & Producers:** Stop guessing what visual theme fits a track. `crate` catalogs your library, analyzing energy levels, key changes, and genre characteristics so your visual templates switch dynamically as soon as you cue up the next track.
* **Developer Notes:** SQLite/Vector-backed library management service. Parses track ID3 tags, Rekordbox/Traktor XML collections, and pre-computed audio embeddings to provide low-latency lookups during live performances.

---

### 🕳️ [ixamal/blackhole](https://github.com/ixamal/blackhole) — *Zero-Latency Audio Routing Pipeline*
* **For DJs & Producers:** Pure, pristine internal audio routing. Route multi-channel stem audio from your DJ software or DAW straight into the AI visual engine without audio dropouts, latency penalties, or buffer overruns on stage.
* **Developer Notes:** Virtual audio driver integration layer and loopback pipeline optimized for macOS CoreAudio / Windows WASAPI. Guarantees isolated buffer queues so heavy GPU execution never causes host audio driver starvation.

---

### 🔥 [ixamal/ix_bangers](https://github.com/ixamal/ix_bangers) — *Preset Packs & Peak-Time Visual LoRAs*
* **For DJs & Producers:** High-octane visual presets, LoRA weights, and UE5 stage scenes tuned for peak-time energy. Instant plug-and-play visual profiles built to turn sound waves into massive stage visuals out of the box.
* **Developer Notes:** Collection of fine-tuned LoRA weights, prompt scheduling profiles, ComfyUI workflow JSON schemas, and pre-built UE5 material instances tuned for rapid model swapping during active performance.

---

### 🌐 [ixamal/grid](https://github.com/ixamal/grid) — *Multi-Display & Stage Mapping Controller*
* **For DJs & Producers:** Take control of any room. `grid` handles your projection mapping, multi-screen stage layouts, and LED wall routing so your live AI visuals look crisp across every display in the venue.
* **Developer Notes:** Multi-viewport spatial renderer and display router using Syphon/Spout and NDI pipelines. Supports edge blending, UV warping, and dynamic frame scaling across multi-monitor GPU setups.

---

## Licensing & Distribution Strategy

Alkalurops is developed under the **Apache 2.0 License**.

- 🛠️ **Open Core (Apache 2.0):** CLI engine, OSC listener nodes, and core Python scripts remain fully open-source for community development and custom integration.
- 🎛️ **Commercial Application:** Standalone GUI desktop application in development for plug-and-play live execution.
- 🏟️ **Enterprise & Media Server Integration:** Custom node modules and stage deployment solutions for venues and production environments.

---

## Development Roadmap

1. **Phase 1 (Current):** ComfyUI local optimization on Apple Silicon / CUDA, UDP OSC listener nodes, distilled model integration (SDXL Turbo / LCM).
2. **Phase 2:** Zero-copy Syphon / NDI frame exporter nodes with dynamic bindings to Unreal Engine 5 material instances.
3. **Phase 3:** Pre-built 3D stage environments, audio-reactive Niagara particle setups, and TouchDesigner C++ integration nodes.

---

## Community & Contributions

Contributions, feedback, and architectural discussions from audio engineers, VJs, graphics developers, and ML researchers are welcome. Please refer to the open issues and pull request guidelines in the repository.
