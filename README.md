Fluid Dynamics Field Reconstruction from Microphone Data Using U-Net

This repository contains the code for a deep learning project aimed at reconstructing fluid dynamics fields from high-frequency microphone data. The workflow includes:

Advanced Preprocessing:

Loading and normalizing the data (.mat files) into float16.
Downsampling the data from 204.8 kHz to 50 kHz using a low-pass filter.
Extracting the first 5 seconds of data to reduce computational load.
Interpolating the data onto a 2D grid (e.g., 64×64) to create a multi-time-step image dataset.
2D U-Net Model:

A deep architecture with BatchNormalization and Dropout.
A combined loss (MSE + α(1 - SSIM)) to preserve both numerical fidelity and spatial structure.
Advanced Training:

Use of callbacks (EarlyStopping, ReduceLROnPlateau, ModelCheckpoint).
Data augmentation to increase the robustness of the model.
The code is organized into modules, allowing for easy modifications of parameters (duration, number of channels, interpolation step, grid size, etc.) to adapt to different configurations and hardware resources.