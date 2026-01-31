# Crop & Weed Seedling Detection
# (Research Pipeline)

![Status](https://img.shields.io/badge/Status-Research_Complete-green)
![License](https://img.shields.io/badge/License-AGPL_3.0-blue)
![Tech](https://img.shields.io/badge/Stack-PyTorch_%7C_YOLOv8_%7C_Jupyter-orange)

**Author:** Igor Khozhanov
**Contact:** khozhanov@gmail.com

---

## 📖 Introduction

This repository contains the complete research and training pipeline for detecting and classifying **crop and weed seedlings** in agricultural environments. 

The entire workflow—from data acquisition to model export—is encapsulated in a single, reproducible **Jupyter Notebook** (`CropAndWeedDetection.ipynb`). This allows researchers and developers to step through the data analysis, training process, and validation metrics interactively.

> **Looking for Production Inference?**
> This repository is for *training and research*. For high-performance deployment (100+ FPS), see C++/CUDA TensorRT engine: 
> [**ZeroHostCopyInference**](https://github.com/Igkho/ZeroHostCopyInference)

---

## 🎯 Features

The notebook covers the full lifecycle of the machine learning project:

1.  **Dataset Preparation:** Automatically clones the `CropAndWeed` dataset and converts the "Fine24" subset (24 seedling classes) into standard YOLO format (1024x1024).
2.  **Model Training:** Fine-tunes a **YOLOv8** CNN to detect small seedlings with high precision.
3.  **Video Annotation:** Runs inference on sample video footage (`Moving.mp4`) to generate visualized results.
4.  **Object Tracking:** Implements **ByteTrack** with custom velocity filtering to maintain consistent IDs for seedlings despite occlusion or camera movement.
5.  **Export:** Generates the `.onnx` weights required for the C++ inference engine.

---

## 📊 Quantitative Metrics

Performance on the "Fine24" seedling subset (24 classes):

| Metric | Score | Notes |
| :--- | :--- | :--- |
| **Precision** | **0.80** | High confidence in positive detections. |
| **Recall** | **0.75** | Effectively finds most seedlings in the frame. |
| **mAP@50** | **0.81** | Strong performance at standard IoU threshold. |
| **mAP@50-95** | **0.60** | robust localization accuracy. |

*Model Latency (RTX 3060 Ti, PyTorch backend): ~28ms (approx. 35 FPS theoretical).*

---

## 🎬 Visual Results

The notebook produces annotated video samples to verify tracking stability.

| Original Footage | Detected Seedlings (YOLOv8 + Tracking) |
| :---: | :---: |
| ![Original](video/Moving.gif) | ![Annotated](video/Moving_annotated.gif) |

---

## 🛠️ Installation & Usage

Since this project is contained within a Jupyter Notebook, setup is straightforward.

### 1. Prerequisites
* Python 3.10 - 3.13
* NVIDIA GPU (Recommended for training)

### 2. Setup Environment
Clone the repository and install dependencies:

```bash
git clone [https://github.com/Igkho/CropAndWeedDetection.git](https://github.com/Igkho/CropAndWeedDetection.git)
cd CropAndWeedDetection

# Create a virtual environment (Optional but recommended)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install libraries
pip install -r requirements.txt
```
