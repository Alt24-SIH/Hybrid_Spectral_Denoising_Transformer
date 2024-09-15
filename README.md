# Hybrid Spectral Denoising Transformer (HSDT)

## Overview

This repository provides the implementation of the Hybrid Spectral Denoising Transformer (HSDT) method, designed for denoising hyperspectral images. The model leverages attention mechanisms to effectively remove noise while preserving the essential spectral and spatial features of hyperspectral data.

## Features

- **Transformer-based Architecture**: Utilizes attention layers to capture long-range dependencies in both spatial and spectral domains.
- **Spectral Decomposition**: Improves feature extraction and denoising by separating spectral and spatial information.
- **Application-specific**: Optimized for hyperspectral images, commonly used in remote sensing, anomaly detection, and target detection.

## File Structure

1. **`__init__.py`**  
   This file initializes the HSDT module, defining key components such as model configurations and parameter settings.

2. **`attention.py`**  
   This file implements the Attention Mechanism used in the transformer architecture. The attention layers are responsible for learning the relationship between different spectral bands and spatial regions, which is crucial for hyperspectral denoising.

3. **`sepconv.py`**  
   The Separable Convolution module is implemented here, which is used to process the spatial and spectral dimensions separately. This reduces computational complexity and enhances the model's ability to handle high-dimensional hyperspectral data.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/Alt24-SIH/HSDT.git
## Usage

### Data Preparation

Prepare your hyperspectral data in the required format. The model expects input data in the form of a 3D array with dimensions corresponding to spatial height, spatial width, and the number of spectral bands.

### Training the Model

To train the model on your dataset:

```bash
python train.py --data <path_to_data> --epochs 50 --batch_size 16
```

## Results

The HSDT method demonstrates significant improvements in the signal-to-noise ratio (SNR) of hyperspectral images, preserving both spectral signatures and spatial textures more effectively than traditional denoising techniques.

### PSNR Performance:
- Achieved a Peak Signal-to-Noise Ratio (PSNR) of **39.5** after just 1 epoch on the ICVL dataset with Gaussian noise of sigma 50.
- Within 3 epochs, HSDT surpasses QRNN3D trained with 30 epochs, offering superior denoising quality.

### Efficiency:
- **HSDT** requires far fewer parameters while achieving faster convergence.
- **HSDT-S** achieves state-of-the-art results with only **0.13M** parameters.
- **HSDT-M**, with **0.52M** parameters, outperforms other methods by a significant margin.

### Denoising Quality:
- The method preserves important **spectral details**, with minimal loss of information and less color distortion.
- **Spatial structures** remain clear and well-defined in the denoised images.

You can evaluate the denoised results further using the provided evaluation scripts and compare them with other methods in terms of **SNR**, **PSNR**, and **visual quality**.
