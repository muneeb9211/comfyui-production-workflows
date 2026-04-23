# AI Music Generation (AceStep)

Generate original music with control over lyrics, genre, instruments, and style — all inside ComfyUI.

## What It Does

1. **AceStep Model** — 3.5B parameter music generation model
2. **Text Encoding** — Processes lyrics and style tags
3. **Latent Audio Generation** — Creates music in latent space via KSampler
4. **VAE Decode** — Converts latent to waveform
5. **MP3 Export** — Saves the final track

You control the genre, tempo, instruments, vocals, and lyrics through text prompts.

## Required Models

### Checkpoints
| Model | Path | Source |
|---|---|---|
| `ace_step_v1_3.5b.safetensors` | `models/checkpoints/` | [HuggingFace](https://huggingface.co/ACE-Step/ACE-Step-v1-3.5B) |

## Required Custom Nodes

- AceStep ComfyUI nodes (install via ComfyUI Manager)

## Usage

1. Write your song prompt — include genre, mood, instruments
2. Write lyrics (or leave empty for instrumental)
3. Adjust KSampler settings (steps, cfg, seed)
4. Run — get an MP3 file

## Prompt Tips

```
Genre: Pop Rock
Mood: Upbeat, energetic
Instruments: Electric guitar, drums, bass, synth
Tempo: 120 BPM
Vocals: Female, clear
```

## VRAM

12GB+ sufficient. Single model, relatively lightweight compared to video workflows.
