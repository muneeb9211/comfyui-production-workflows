# Talking Avatar (InfiniTalk)

Generate lip-synced talking character videos from a single image and audio file.

## What It Does

1. **Load Image + Audio** — Character portrait + speech audio
2. **Audio Separation** — Isolates vocals from background noise
3. **Wav2Vec Embeddings** — Extracts speech features for lip-sync
4. **Wan 2.1 + MultiTalk** — Generates video with accurate lip movement
5. **LightX2V LoRA** — Accelerates generation (4-step distillation)

Simple input, high-quality output. No voice cloning — just bring your audio.

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `wan2.1_i2v_480p_14B_fp16.safetensors` | `models/diffusion_models/` |
| `Wan2_1-InfiniTetalk-Single_fp16.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `umt5-xxl-enc-bf16.safetensors` | `models/text_encoders/` |

### VAE & CLIP
| Model | Path |
|---|---|
| `Wan2_1_VAE_bf16.safetensors` | `models/vae/` |
| `clip_vision_h.safetensors` | `models/clip_vision/` |

### LoRAs
| Model | Path |
|---|---|
| `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors` | `models/loras/` |

## Required Custom Nodes

- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [ComfyUI-MultiTalk](https://github.com/ShmuelRonen/ComfyUI-MultiTalk)

## Usage

1. Load a character portrait image (front-facing works best)
2. Load your audio file (speech)
3. Run — get a lip-synced video

## Tips

- Use a clear, front-facing portrait for best lip-sync accuracy
- Audio should be clean speech — use the built-in audio separation if noisy
- Output is 480p — upscale with the [video upscale utility](../bonus-utilities/) if needed
