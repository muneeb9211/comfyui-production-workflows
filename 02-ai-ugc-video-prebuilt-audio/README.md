# AI UGC Video with Prebuilt Audio

Same pipeline as [01-ai-ugc-video-voice-cloning](../01-ai-ugc-video-voice-cloning/) but uses pre-recorded audio instead of voice cloning.

## What It Does

1. **Qwen Image Edit** — Edits a character image to hold/present a product
2. **Wan 2.1 I2V** — Converts the edited image into a video
3. **Audio Separation** — Cleans the pre-recorded audio (separates vocals)
4. **InfiniTalk (MultiTalk)** — Lip-syncs the character video to the audio

Use this when you already have a voiceover recorded and just need the video.

## Required Models

Same as [01-ai-ugc-video-voice-cloning](../01-ai-ugc-video-voice-cloning/README.md#required-models), minus the VibeVoice models.

## Required Custom Nodes

- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [ComfyUI-MultiTalk](https://github.com/ShmuelRonen/ComfyUI-MultiTalk)
- Qwen Image Edit nodes (install via ComfyUI Manager)

## Usage

1. Load your character image
2. Provide a product image or description
3. Load your pre-recorded audio file
4. Run the workflow

## When to Use This vs. 01

- **Use 01** when you need to clone someone's voice from a sample
- **Use 02 (this)** when you already have the voiceover audio ready
