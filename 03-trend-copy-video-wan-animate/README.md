# Trend Copy Video (Image-Guided) — Wan 2.2 Animate

Copy any trending video style by providing a reference image. The workflow extracts pose/motion from a source video and applies it to your character.

## What It Does

1. **Flux2 Image Generation** — Generates a character image (or use your own)
2. **SAM2 Segmentation** — Segments the subject from the background
3. **YOLO + ViTPose Detection** — Extracts skeleton/pose from the reference video
4. **Wan 2.2 Animate** — Generates a new video with your character following the reference motion
5. **Relight LoRA** — Adds consistent lighting to the output

This is the most complex workflow in the collection (86 nodes).

## Required Models

### Diffusion Models
| Model | Path |
|---|---|
| `flux-2-klein-9b-fp8.safetensors` | `models/diffusion_models/` |
| `Wan2_2-Animate-14B_fp8_e4m3fn_scaled_KJ.safetensors` | `models/diffusion_models/` |

### Text Encoders
| Model | Path |
|---|---|
| `umt5-xxl-enc-bf16.safetensors` | `models/text_encoders/` |
| `qwen_3_8b_fp8mixed.safetensors` | `models/text_encoders/` |

### VAE & CLIP
| Model | Path |
|---|---|
| `Wan2_1_VAE_bf16.safetensors` | `models/vae/` |
| `flux2-vae.safetensors` | `models/vae/` |
| `clip_vision_h.safetensors` | `models/clip_vision/` |

### LoRAs
| Model | Path |
|---|---|
| `lightx2v_I2V_14B_480p_cfg_step_distill_rank64_bf16.safetensors` | `models/loras/` |
| `WanAnimate_relight_lora_fp16.safetensors` | `models/loras/` |

### Segmentation
| Model | Path |
|---|---|
| `sam2.1_hiera_base_plus.safetensors` | `models/sam2/` |

### Detection (ONNX)
| Model | Path |
|---|---|
| `yolov10m.onnx` | `models/onnx/` |
| `vitpose-l-wholebody.onnx` | `models/onnx/` |

## Required Custom Nodes

- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [ComfyUI-WanAnimatePreprocess](https://github.com/kijai/ComfyUI-WanAnimatePreprocess) — Pose detection (includes YOLO + ViTPose)
- [ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2) — SAM2
- [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) — Video loading/saving

## Usage

1. Provide a reference/trending video (the motion source)
2. Provide or generate a character image
3. Write a prompt describing the desired output
4. Run the workflow

## VRAM

24GB+ required. Multiple large models run in sequence (Flux2 + SAM2 + Wan Animate).
