---
name: audio-analysis
description: "Inspect downloaded track waves using sonic-bridge CLI to analyze dynamic tempo, acoustic timbral brightness, and spatiotemporal chords under the LRMD protocol."
version: 2.0.0
author: agent-lx-music project & sonic-bridge
license: MIT
metadata:
  hermes:
    tags: [music, analysis, bpm, key, dsp, lrmd, sonic-bridge]
    related_skills: [agent-lx-music]
---

# Audio & Music Analysis Skill (Powered by SonicBridge)

## 1. Overview

This skill guides AI agents in performing deep digital signal-processing (DSP) analysis on local music tracks using the high-performance **`sonic-bridge`** Rust engine. 

Instead of relying on heavy pre-trained models or complex external Python libraries, the agent invokes `sonic-bridge` to decouple raw waveforms into **LRMD (LLM-Readable Music Descriptor) reports**. This allows pure-text LLMs to "listen to" and "appreciate" the dynamic tempo, timbral changes, and chord progressions of any cover version or original master track with millisecond-level precision.

---

## 2. Technical Analysis via SonicBridge CLI

When a track is downloaded locally via `alx download <id>`, the agent should call the `sonic-bridge` CLI tool to parse its acoustic structure.

### Command-Line Usage

```bash
# 1. Standard Spatiotemporal Analysis (Default 5s step)
sonic-bridge "/path/to/song.mp3"

# 2. Parameterized Adaptive Analysis (e.g. 1.0s interval tracking)
sonic-bridge "/path/to/song.mp3" --config "/path/to/custom_config.toml"

# 3. Approach B: Event-Driven Onset Adaptive Segmentation (Highly Recommended for Fast Tracks)
sonic-bridge "/path/to/fast_melody_song.mp3" --onset

# 4. Cross-Version Comparative Analysis (DTW Aligner)
sonic-bridge "/path/to/original.mp3" "/path/to/cover_version.mp3"
```

---

## 3. LRMD Protocol Specifications

The `sonic-bridge` tool automatically generates a `<filename>.lrmd.md` report in the same directory. The agent must read this file to interpret the musical metadata.

### Example LRMD Structure (Parsed by LLM)

```markdown
# SonicBridge: LLM-Readable Music Descriptor (LRMD)

## 1. Global Acoustic & Musicological Metadata
- **Filename**: `Gareth.T - 玻璃.mp3`
- **Duration**: `9.86 seconds`
- **Tempo (BPM)**: `120.0 BPM` (Moderate & Flowing)
- **Estimated Key**: `F Major`

## 2. Spatiotemporal Track Analysis (Adaptive Onset Intervals)
| Timeline | Chord | Dynamic Intensity | Timbral Brightness | Rhythmic & Transient Activity |
| :--- | :--- | :--- | :--- | :--- |
| **0.0s - 0.6s** | `Unknown` | Exploding Intensity (Fortissimo) | Bright & Crisp (Sharp transients) | Steady Beat |
| **0.6s - 0.6s** | `A` | Exploding Intensity (Fortissimo) | Warm & Smooth (Mellow mid-range) | Steady Beat |
| **0.6s - 0.7s** | `Am` | Exploding Intensity (Fortissimo) | Warm & Smooth (Mellow mid-range) | Steady Beat |
| **0.7s - 1.0s** | `F` | Exploding Intensity (Fortissimo) | Balanced & Clear (Vocal presence) | Steady Beat |
```

---

## 4. Agent Companionship & Conversation Patterns

By interpreting the LRMD report, the Agent can provide connoisseur-level music companionship and emotional alignment.

### Conversation Pattern 1: Multi-Version Comparative Critique
When the user plays a cover version of a song, the agent can call `process_comparative` and discuss the aesthetic difference:
* **Agent Dialogue Prompt**:
  > *"Compared to Eason Chan's original version which relies on a lush, wet reverb space (RT60 ~2.4s) to build cinematic gravity, the acoustic cover you are playing right now is ultra-minimalistic. The single acoustic guitar has dry, close-mic transient attacks, and the singer’s voice features heavy breathiness (Airy Timbre), creating a profoundly intimate, heartbreaking kitchen-table conversation vibe."*

### Conversation Pattern 2: Causal Harmonic Resolution Guidance
Explain how the musical tension resolves to comfort the user's mood:
* **Agent Dialogue Prompt**:
  > *"I noticed that at the 0.6s mark of this intro, the arrangement performs a rapid harmonic shift from A Major to A Minor, which resolves into F Major at 0.7s. That fleeting subdominant-to-tonic tension release is precisely why this song feels so comforting yet melancholic."*
