# Xception-MicroNet-MultiScale-CBAM NIR SEM Image EQE Prediction System

## Project Overview

This project adopts an improved **Xception-MicroNet-MultiScale-CBAM** deep learning model to predict the external quantum efficiency (EQE) of perovskite light-emitting diodes (PeLEDs) using near-infrared scanning electron microscope (SEM) images.

The model integrates the following modules:
* Xception-MicroNet backbone network
* Multi-Scale feature extraction module
* CBAM-LIPCA attention enhancement mechanism

## Environment Requirements

### Python

Recommended version:

```text
Python ≥ 3.8
```

### GPU (Recommended)

An NVIDIA GPU with CUDA support is recommended to achieve optimal inference speed.
Recommended hardware examples:

* NVIDIA RTX 3060
* NVIDIA RTX 4060
* NVIDIA RTX 4070

---

## Dependency Installation

Run the following command to install all required libraries in one batch:

```bash
pip install torch>=1.10.0 torchvision>=0.11.0 pandas>=1.3.0 numpy>=1.21.0 matplotlib>=3.4.0 tqdm>=4.62.0 scikit-learn>=1.0.0 pillow>=8.3.0
```
---

## Pre-trained Model Weights Download

Pre-trained Model Weights Download

### Baidu Netdisk Download

Download link:

https://pan.baidu.com/s/1KTnRsP2lPBnBj8ZCsBRwrQ

Extraction code:

```text
yuqa
```

---

## Weight File Configuration

After downloading, place all .pth weight files into the weight directory specified in the inference script.
Directory structure example:

```text
project/
│
├── inference.py
├── model_weights/
│   ├── model_fold1.pth
│   ├── model_fold2.pth
│   └── model_fold3.pth
│
└── test_images/
```

Verify the file path variable in the code matches the folder location:

```python
model_weights_path = "./model_weights"
```

---

## Data Preparation

Place all NIR SEM images to be predicted into the test image directory:

```text
test_images/
├── sample_001.png
├── sample_002.png
├── sample_003.png
└── ...
```
```text
test_image_1 is derived from Nano Letters, 2021, 21 (9): 3993-4001
test_image_2 is derived from Nature Communications, 2021, 12 (1): 644
test_image_3 is derived from Nano-Micro Letters, 2023, 15: 125
test_image_4 is derived from Nature Communications, 2024, 15 (1): 10760
test_image_5 is derived from Matter, 2021, 4 (11): 3710-3724
test_image_6 is derived from Joule, 2024, 8 (4): 1176-1190
```
---

## Precautions
```text
1.Input SEM images should be captured under imaging conditions consistent with or similar to the training dataset;
2.Image resolution must match the resolution used during model training;
3.Double-check the weight file path before running inference;
4.If GPU acceleration is enabled, ensure the CUDA environment is properly configured;
5.It is recommended to run inference on a small subset of test samples first to validate the full environment setup.
```
---

## Contact Information

For inquiries or suggestions, please contact the corresponding author of the related paper or project maintainer.

---

