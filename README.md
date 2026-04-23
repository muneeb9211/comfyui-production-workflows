# ComfyUI Production Workflows

12 production-tested ComfyUI workflows for AI content creation — characters, product videos, music, voice cloning, and more.

Built for a real client project. Battle-tested in production. Now open-source.

## Workflows

### AI Video & UGC

| # | Workflow | Description |
|---|---|---|
| 01 | [AI UGC Video + Voice Cloning](./01-ai-ugc-video-voice-cloning/) | Generate product videos with AI characters and cloned voice (InfiniTalk + VibeVoice) |
| 02 | [AI UGC Video + Prebuilt Audio](./02-ai-ugc-video-prebuilt-audio/) | Same pipeline but with pre-recorded audio instead of cloning |
| 03 | [Trend Copy Video (Image-Guided)](./03-trend-copy-video-wan-animate/) | Copy any trending video style using a reference image (Wan 2.2 Animate) |
| 04 | [Trend Copy Video (Text-Only)](./04-text-to-trend-video-wan-animate/) | Generate trend-style videos from text prompts without a reference image |

### Character & Image Generation

| # | Workflow | Description |
|---|---|---|
| 05 | [Multi-Character Group (Qwen 2511)](./05-multi-character-group-qwen/) | Generate 5 consistent characters with individual LoRAs in a single pipeline |
| 06 | [Multi-Character Regional Prompting](./06-multi-character-regional-prompting/) | Place multiple characters in one image using regional attention control |
| 07 | [Image Realism Enhancer](./07-image-realism-enhancer/) | Add photorealistic skin, lighting, and detail to AI-generated images |
| 08 | [Product Placement (Qwen 2511)](./08-product-placement-qwen/) | Edit AI characters to hold or interact with real products |

### Audio & Music

| # | Workflow | Description |
|---|---|---|
| 09 | [Talking Avatar (InfiniTalk)](./09-talking-avatar-infinitetalk/) | Generate lip-synced talking character videos from image + audio |
| 10 | [AI Music Generation (AceStep)](./10-ai-music-generation-acestep/) | Create original songs with lyrics, genre, and instrument control |

### Training & Datasets

| # | Workflow | Description |
|---|---|---|
| 11 | [Flux2 Dataset + Auto Captions](./11-flux2-dataset-with-captions/) | Generate training images with automatic Florence2 captioning |
| 12 | [Flux2 Batch Dataset (Prompt Queue)](./12-flux2-batch-dataset-prompt-queue/) | Batch-generate dataset images using prompt queue automation |

### Bonus Utilities

Small single-purpose workflows in the [bonus-utilities](./bonus-utilities/) folder:

- **Audio Separator** — Split vocals from instrumentals
- **Caption Generator** — Auto-caption image datasets (WD14 Tagger)
- **Voice Design (Qwen TTS)** — Design custom voices with text-to-speech
- **Video Combine** — Merge multiple video clips with audio
- **Singing Audio Merge** — Combine and amplify audio tracks

## How to Use

1. Open ComfyUI
2. Drag and drop any `workflow.json` into the canvas
3. Install missing custom nodes (ComfyUI Manager recommended)
4. Download required models (listed in each workflow's README)
5. Run

## Requirements

- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) (latest)
- [ComfyUI Manager](https://github.com/ltdrdata/ComfyUI-Manager) (for auto-installing custom nodes)
- GPU with 12GB+ VRAM (24GB+ recommended for video workflows)

## License

MIT License — use these however you want.

## Star This Repo

If any of these workflows save you time, drop a star. It helps others find them.
