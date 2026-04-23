# Multi-Character Group Generation (Qwen 2511)

Generate 5 consistent AI characters in a single pipeline run, each with their own LoRA for identity persistence.

## What It Does

1. **Z Image Turbo** — Fast base image generation for each character
2. **Multiple LoRA Loaders** — Applies character-specific LoRAs for consistent identity
3. **Qwen Image Edit 2511** — Refines and edits generated characters (embedded component node)
4. **ImageStitch** — Combines all characters into a group composition
5. **Individual + Group Outputs** — Saves each character separately and as a group

> **Note:** This workflow uses a ComfyUI Core component node (subgraph). Requires ComfyUI 0.9.2+.

Built for K-Pop groups, brand ambassador teams, or any project needing multiple consistent characters.

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `z_image_turbo_bf16.safetensors` | `models/diffusion_models/` |
| `qwen_image_edit_2511_bf16.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `qwen_3_4b.safetensors` | `models/text_encoders/` |
| `qwen_2.5_vl_7b_fp8_scaled.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `ae.safetensors` | `models/vae/` |
| `qwen_image_vae.safetensors` | `models/vae/` |

### LoRAs
| Model | Path |
|---|---|
| `Qwen-Image-Edit-2511-Lightning-4steps-V1.0-bf16.safetensors` | `models/loras/` |
| Your custom character LoRAs (e.g., `Minho_rank16_bf16.safetensors`) | `models/loras/` |

## Required Custom Nodes

- Z Image Turbo nodes (install via ComfyUI Manager)
- ImageStitch node

## Usage

1. Load your character LoRAs (train them first using workflows 11-12 + Flux training)
2. Write prompts for each character
3. Run — get 5 individual images + stitched group image

## Tips

- Train character LoRAs first using the [Flux2 Dataset](../11-flux2-dataset-with-captions/) + training workflow
- Keep prompts consistent for group cohesion (same background, lighting, style)
- The Lightning LoRA speeds up generation (4-step inference)
