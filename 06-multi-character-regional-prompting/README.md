# Multi-Character Regional Prompting

Place multiple distinct characters in a single image using regional attention control — each character gets its own prompt region.

## What It Does

1. **Binary Pattern Masks** — Defines spatial regions for each of 5 characters
2. **AttentionCouple** — Routes different prompts to different image regions
3. **ADE LoRA Hooks** — Applies character-specific LoRAs to specific regions only
4. **Single Generation Pass** — All characters rendered in one image, one inference

Unlike generating characters separately and compositing, this workflow generates them together with natural interaction and consistent lighting.

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `z_image_turbo_bf16.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `qwen_3_4b.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `ae.safetensors` | `models/vae/` |

### LoRAs
- Character-specific LoRAs for each region (replace placeholder names in the workflow)
- Applied via ADE LoRA hooks (region-locked)

## Required Custom Nodes

- [ComfyUI-Advanced-ControlNet](https://github.com/Kosinkadink/ComfyUI-Advanced-ControlNet) — ADE LoRA hooks
- [ComfyUI-AttentionCouple](https://github.com/laksjdjf/ComfyUI-AttentionCouple) — Regional prompting
- [ComfyRoll](https://github.com/Suzie1/ComfyUI_Comfyroll_CustomNodes) — Binary pattern masks, image sizing
- [cg-use-everywhere](https://github.com/chrisgoringe/cg-use-everywhere) — Anything Everywhere node

## Usage

1. Define mask regions for each character position
2. Write individual prompts per character
3. Load character LoRAs and assign to regions
4. Run — single image with all characters

## How It Differs from 05

| Feature | 05 (Group Qwen) | 06 (Regional) |
|---|---|---|
| Method | Separate images, stitched | Single image, all at once |
| Interaction | Characters don't interact | Natural interaction possible |
| Control | Full control per character | Regional control |
| Output | Individual + stitched | Single composed image |
| Complexity | Moderate (29 nodes) | Complex (53 nodes) |
