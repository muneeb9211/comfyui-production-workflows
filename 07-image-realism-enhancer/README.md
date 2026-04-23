# Image Realism Enhancer

Transform AI-generated images into photorealistic results using a multi-stage pipeline — skin detail, lighting correction, and super-resolution upscaling.

## What It Does

1. **Z Image Turbo / Flux** — Base image generation with realism LoRAs
2. **Realistic Skin LoRA** — Adds pores, imperfections, and natural skin texture
3. **SeedVR2 Upscaler** — AI-powered upscaling that adds real detail (not just interpolation)
4. **4x ClearReality Upscale** — Traditional upscale model for final sharpness
5. **Image Blending** — Combines passes for balanced output
6. **Image Comparer** — Side-by-side before/after comparison

## Required Models

### Diffusion Models
| Model | Path | Source |
|---|---|---|
| `zEpicrealism_turboV1Fp8.safetensors` | `models/diffusion_models/` | [CivitAI](https://civitai.com/models/2305301/z-epicrealism) |
| `ultrarealFineTune_v4.safetensors` | `models/diffusion_models/` | [CivitAI](https://civitai.com/models/978314/ultrareal-fine-tune) |

### Text Encoders
| Model | Path |
|---|---|
| `clip_l.safetensors` | `models/clip/` |
| `t5xxl_fp8_e4m3fn.safetensors` | `models/text_encoders/` |
| `qwen_3_4b.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `ae.safetensors` | `models/vae/` |

### LoRAs
| Model | Path | Source |
|---|---|---|
| `aidmaRealisticSkin-FLUX-v0.1.safetensors` | `models/loras/` | [CivitAI](https://civitai.com/models/1157318/photorealistic-skin-no-plastic-flux) |

### SeedVR2
| Model | Path | Source |
|---|---|---|
| `seedvr2_ema_3b_fp8_e4m3fn.safetensors` | `models/SEEDVR2/` | [HuggingFace](https://huggingface.co/numz/SeedVR2_comfyUI) |
| `ema_vae_fp16.safetensors` | `models/SEEDVR2/` | [HuggingFace](https://huggingface.co/numz/SeedVR2_comfyUI) |

### Upscale Models
| Model | Path |
|---|---|
| 4x ClearReality | `models/upscale_models/` |

## Required Custom Nodes

- SeedVR2 nodes (install via ComfyUI Manager)
- [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) — Image Comparer, Labels
- [ComfyUI-JPS-Nodes](https://github.com/JPS-GER/ComfyUI-JPS-Nodes) — Multiply Int Float
- [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) — Float utilities

## Usage

1. Generate or load an AI image
2. The pipeline automatically applies skin realism, upscales, and blends
3. Compare before/after with the built-in comparer node

## Tips

- Adjust the detail level and smoothness parameters in the workflow notes
- Face mask blur controls how much realism is applied to facial features
- Works best on portrait and character images
