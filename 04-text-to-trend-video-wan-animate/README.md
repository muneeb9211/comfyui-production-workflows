# Trend Copy Video (Text-Only) — Wan 2.2 Animate

Generate trend-style videos from a reference video and text prompt — no input image needed.

## What It Does

1. **YOLO + ViTPose Detection** — Extracts pose/skeleton from the reference video
2. **SAM2 Segmentation** — Segments subjects in the reference
3. **Wan 2.2 Animate** — Generates a new video following the reference motion, guided by text
4. **Relight LoRA** — Consistent lighting

Same core pipeline as [03-trend-copy-video](../03-trend-copy-video-wan-animate/) but without the Flux2 image generation stage. The character is described entirely through the text prompt.

## Required Models

Same as [03-trend-copy-video-wan-animate](../03-trend-copy-video-wan-animate/README.md#required-models), minus the Flux2 models (`flux-2-klein-9b-fp8.safetensors`, `qwen_3_8b_fp8mixed.safetensors`, `flux2-vae.safetensors`).

## Required Custom Nodes

- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [ComfyUI-WanAnimatePreprocess](https://github.com/kijai/ComfyUI-WanAnimatePreprocess)
- [ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2)
- [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) — Video loading/saving

## When to Use This vs. 03

- **Use 03** when you have a specific character image you want to animate
- **Use 04 (this)** when you want to describe the character via text and let the model generate it

## VRAM

24GB+ recommended.
