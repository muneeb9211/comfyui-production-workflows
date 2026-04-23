# Product Placement (Qwen Image Edit 2511)

Edit AI characters to hold, wear, or interact with real products using Qwen Image Edit with multi-reference support.

## What It Does

1. **Load References** — Character image + product image
2. **FluxKontextMultiReferenceLatentMethod** — Fuses multiple reference images into the edit
3. **Qwen Image Edit 2511** — Intelligently edits the character to incorporate the product
4. **Lightning LoRA** — 4-step fast inference

The model understands spatial relationships — it can place a product in a character's hand, on a table, or as a worn item.

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `qwen_image_edit_2511_bf16.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `qwen_2.5_vl_7b_fp8_scaled.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `qwen_image_vae.safetensors` | `models/vae/` |

### LoRAs
| Model | Path |
|---|---|
| `Qwen-Image-Edit-2511-Lightning-4steps-V1.0-bf16.safetensors` | `models/loras/` |

## Required Custom Nodes

- Qwen Image Edit nodes (install via ComfyUI Manager)
- FluxKontext nodes for multi-reference editing

## Usage

1. Load your character image
2. Load your product image
3. Write an edit prompt (e.g., "person holding the product in their right hand")
4. Run — get edited image with product naturally integrated

## Use Cases

- E-commerce product ads with AI models
- Brand ambassador content
- Social media product showcases
- Combine with [01-ai-ugc-video](../01-ai-ugc-video-voice-cloning/) to turn the edited image into a video ad
