# Voxel World Model

> Real time world model that turns game engine data like camera pose, motion, depth, lighting, and entity state into photorealistic video using neural rendering. Focused on low latency, temporal stability, and using AI as the rendering layer for interactive environments.

---

A real world sensor event, such as opening a physical door, can update an entity state inside the voxel world. That structured state change can then be rendered through a real time AI pipeline using neural rendering, Gaussian splatting, temporal caching, and frame conditioning.

---

### Example Visual: Voxel Game → Real-Time Photorealism

A real voxel world model uses an open-source voxel game as the structured simulation layer, then replaces or overlays the native renderer with an AI-driven photorealistic rendering pipeline.



<p align="center">
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/3.png" width="49%"/>
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/4.png" width="49%"/>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/2.png" width="49%"/>
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/1.png" width="49%"/>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/6.png" width="49%"/>
  <img src="https://raw.githubusercontent.com/voxelworldmodel/.github/refs/heads/main/5.png" width="49%"/>
</p>

---

# Pipeline

- an opensource voxel game
- Custom rendering (framebuffer capture + injection)
- Shader pack (depth, normals, lighting buffers)
- GPU pipeline (RTX / raster + shader outputs)

- Frame extraction (RGB frames)
- Depth buffer extraction
- Normal map extraction (optional)
- Motion vectors / camera delta (optional)
- Player input capture (keyboard, mouse, actions)

- Data bridge (game → AI pipeline)
- Conditioning encoder (format inputs for model)

- world_engine (core world model inference)
- Prompt system (scene style control)
- Temporal frame buffer (history for consistency)
- Latent / diffusion model (frame generation)

- Gaussian Splatting (optional 3D stability layer)
- Depth reconstruction / scene representation
- Real-time splat renderer

- Frame post-processing (denoise, color correction)
- Upscaling (DLSS / AI upscaler)
- Frame interpolation (optional)

- Output renderer (replace or overlay Minecraft frame)
- Sync system (match generation timing to gameplay)
- Async batching (handle multi-frame outputs)

- GPU acceleration (CUDA / TensorRT / quantization)
- Memory management (VRAM buffering, caching)

- Training / fine-tuning pipeline (optional)
- Paired dataset (Minecraft ↔ real-world scenes)
- LoRA / adapter tuning

- UI / debug overlay (latency, buffers, toggles)
- Recording / playback system (testing + dataset generation)
