# Flux2 Batch Dataset Generation (Prompt Queue)

Batch-generate dataset images using prompt queue automation — define multiple prompts and generate them all in sequence.

## What It Does

1. **PromptQueue Node** — Feeds multiple prompts sequentially into the pipeline
2. **Flux2 Generation** — Generates images for each prompt
3. **Batch Output** — Saves all images with organized naming

Use this when you need many variations of a subject across different poses, outfits, backgrounds, and lighting conditions.

## Required Models

Same as [11-flux2-dataset-with-captions](../11-flux2-dataset-with-captions/README.md#required-models) (Flux2 Dev fp8mixed + Mistral 3 Small text encoder + flux2-vae).

## Required Custom Nodes

- PromptQueue node (install via ComfyUI Manager)

## Usage

1. Define your prompt list (one per line or via the PromptQueue node)
2. Set batch size per prompt
3. Run — all prompts are processed sequentially
4. Use output as training data

## When to Use This vs. 11

| Feature | 11 (Dataset + Captions) | 12 (Batch Prompt Queue) |
|---|---|---|
| Captioning | Auto-captioned (Florence2) | No auto-captioning |
| Prompt Input | Single prompt | Multiple prompts queued |
| Best For | Quick dataset with captions | Large varied datasets |
| Workflow | Generate → Caption → Save | Queue → Generate → Save |

Use both together: generate with this workflow, then run captions separately.
