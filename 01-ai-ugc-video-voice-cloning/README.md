# AI UGC Video with Voice Cloning

Full AI UGC (User Generated Content) video pipeline — generates a character holding a product, clones a voice, and creates a lip-synced talking video.

## What It Does

1. **Qwen Image Edit** — Takes a character image and edits it to hold/present a product
2. **Wan 2.1 I2V** — Converts the edited image into a video with natural movement
3. **VibeVoice** — Clones a reference voice from a short audio sample
4. **InfiniTalk (MultiTalk)** — Lip-syncs the character video to the cloned voice

The result is a complete AI-generated product advertisement video with a custom character and cloned voice.

## Required Models

### Diffusion Models
| Model | Path | Source |
|---|---|---|
| `qwen_image_edit_2509_fp8_e4m3fn.safetensors` | `models/diffusion_models/` | [HuggingFace](https://huggingface.co/Comfy-Org/Qwen_Image_Edit_2509/blob/main/qwen_image_edit_2509_fp8_e4m3fn.safetensors) |
| `wan2.1_i2v_480p_14B_fp16.safetensors` | `models/diffusion_models/` | [HuggingFace](https://huggingface.co/Kijai/WanVideo_comfy/tree/main) |

### Text Encoders
| Model | Path |
|---|---|
| `qwen_2.5_vl_7b_fp8_scaled.safetensors` | `models/text_encoders/` |
| `umt5-xxl-enc-bf16.safetensors` | `models/text_encoders/` |

### VAE
| Model | Path |
|---|---|
| `qwen_image_vae.safetensors` | `models/vae/` |
| `Wan2_1_VAE_bf16.safetensors` | `models/vae/` |

### LoRAs
| Model | Path |
|---|---|
| `Qwen-Image-Edit-2509-Lightning-4steps-V1.0-bf16.safetensors` | `models/loras/` |
| `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors` | `models/loras/` |

### Other
| Model | Path |
|---|---|
| `clip_vision_h.safetensors` | `models/clip_vision/` |
| `Wan2_1-InfiniTetalk-Single_fp16.safetensors` | `models/diffusion_models/` |

### VibeVoice
Follow the VibeVoice-ComfyUI node installation guide for voice cloning model setup.

## Required Custom Nodes

- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper) — Wan video generation
- [ComfyUI-MultiTalk](https://github.com/ShmuelRonen/ComfyUI-MultiTalk) — InfiniTalk lip-sync
- [VibeVoice-ComfyUI](https://github.com/ShmuelRonen/VibeVoice-ComfyUI) — Voice cloning
- Qwen Image Edit nodes (install via ComfyUI Manager)

## Usage

1. Load your character image
2. Provide a product image or description
3. Provide a short voice reference audio (5-10 seconds)
4. Enter the script/text for the character to speak
5. Run the workflow

## VRAM

24GB+ recommended. The pipeline runs multiple models sequentially.
