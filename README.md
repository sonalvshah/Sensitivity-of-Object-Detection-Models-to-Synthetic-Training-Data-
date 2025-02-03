# Sensitivity-of-Object-Detection-Models-to-Synthetic-Training-Data

# Working with RarePlanes Dataset

## Overview
This project explores the **RarePlanes Dataset**, a unique dataset designed for aerial object detection and synthetic data evaluation. Our work will focus on two potential directions: **Object Detection** and **Synthetic Image Generation**.

### Reference Paper
For a detailed overview of the development of the RarePlanes dataset, refer to the original paper:
[Development of RarePlanes Dataset](https://arxiv.org/pdf/2006.02963)

### Dataset Access
Instructions on how to download and use the RarePlanes dataset can be found here:
[Download RarePlanes Dataset](https://www.iqt.org/library/the-rareplanes-dataset)

### 1. Object Detection
We used **Detectron2**, a powerful object detection framework by Facebook AI, for performing object detection on the RarePlanes dataset.

#### Why Detectron2?
- Supports multiple object detection models
- Allows customization of models by using different **feature extraction methods** (backbones):
  - **Swin Transformer Backbone**
  - **ViT (Vision Transformer) Backbone**
- Enables comparison of different object detection models

**Resources:**
- Detectron2 Repository: [Detectron2 GitHub](https://github.com/facebookresearch/detectron2)

### 2. Synthetic Image Generation
Since the RarePlanes dataset contains both **real** and **synthetic** training images, we aim to train a generative model on the **real** images to generate **synthetic** aerial images.

#### Approaches:
- **Generative Adversarial Networks (GANs)**
- **Variational Autoencoders (VAEs)**
- **Diffusion Models**

## Experimental Results
### Bounding Box AP after 45000 iterations
| Model | Trainable Params | 98% Synth | 100% Synth |
|--------|----------------|------------|------------|
| Cascade RCNN | 140,746,466 | 62.480 | 35.48 |
| Mask RCNN | 110,319,318 | 66.5275 | 41.3719 |
| YOLO11m | 20,114,688 | 54.3933 | 30.4704 |
| Faster RCNN | - | - | - |
| DiffusionDet (swin backbone) | 173,350,102 | 70.68 | 31.188 |

### Divergence between training set with synthetic data and test set with just real images
| Comparison | KL Divergence | EMD |
|------------|--------------|------|
| 98% Synth vs 100% Real | 1.0052136995935088 | 0.09065017912436187 |
| 100% Synth vs 100% Real | 0.402425560132678 | 0.09254298376939471 |





