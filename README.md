# Vikki Video AI — Free/Open Video Generator

This project gives you a Seedance-style web workflow using the open Wan2.2 TI2V-5B model.

## What it includes
- Text → video
- Image + text → video
- 9:16 portrait / 16:9 landscape
- 720p-capable workflow
- MP4 preview and download
- Mobile-friendly UI
- No paid SaaS/API is required by the app itself

## Important
"Free website" does NOT mean free GPU compute. Wan2.2 TI2V-5B can run locally, but it needs a suitable NVIDIA GPU. The official model documentation says 720p inference can run on a single GPU with at least 24 GB VRAM such as an RTX 4090.

## Install

1. Install Python 3.10+ and NVIDIA CUDA/PyTorch suitable for your GPU.
2. Clone Wan2.2 into this project folder:

   git clone https://github.com/Wan-Video/Wan2.2.git

3. Install Wan2.2 requirements:

   cd Wan2.2
   pip install -r requirements.txt

4. Download the model:

   huggingface-cli download Wan-AI/Wan2.2-TI2V-5B --local-dir ../Wan2.2-TI2V-5B

5. Return to this project root and install web dependencies:

   pip install -r requirements.txt

6. Start:

   uvicorn backend.main:app --host 0.0.0.0 --port 7860

7. Open:

   http://localhost:7860

## Environment variables
WAN_REPO=./Wan2.2
WAN_CHECKPOINT=./Wan2.2-TI2V-5B

## Reality check
The UI/workflow is designed to be similar in spirit to modern AI video generators, but it is NOT the proprietary Seedance 2.0 model and cannot honestly be claimed to be 89% equivalent in output quality. Wan2.2 is an independent open model.

For a public website, put the GPU inference server behind authentication, rate limits, a job queue, storage cleanup, and abuse controls.
