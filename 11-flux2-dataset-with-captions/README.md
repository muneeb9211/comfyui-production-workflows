# Flux2 Dataset Creation with Auto Captions

Generate training images and automatically caption them using Florence2 — ready for LoRA training.

## What It Does

1. **Flux2 Image Generation** — Generates character/subject images from prompts
2. **Florence2 Captioning** — Automatically describes each generated image
3. **SaveImageExtended** — Saves images with metadata and caption text files

Output is a ready-to-train dataset: images paired with `.txt` caption files.

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `flux2_dev_fp8mixed.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `mistral_3_small_flux2_bf16.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `flux2-vae.safetensors` | `models/vae/` |

### Captioning
| Model | Path |
|---|---|
| Florence2 (`Florence-2-base`) | Auto-downloaded by node |

## Required Custom Nodes

- Florence2 captioning nodes (install via ComfyUI Manager)
- SaveImageExtended node
- ComfyUI-Custom-Scripts or WAS Node Suite — Text utilities (Save Text File, Text Find and Replace)

## Usage

1. Write prompts describing your character/subject in various poses and settings
2. Run the workflow — images are generated and captioned automatically
3. Use the output folder directly as training data for LoRA training

## Pipeline

This workflow is step 1 of the LoRA training pipeline:

```
[11 - Dataset Creation] → [LoRA Training] → [05 - Group Generation]
```

Generate your dataset here, then train a LoRA, then use it in the character generation workflows.
