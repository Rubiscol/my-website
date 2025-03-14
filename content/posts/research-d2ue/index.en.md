---
weight: 5
title: "D2UE: Revisiting Deep Ensemble Uncertainty"
date: 2025-03-01T10:00:00+00:00
lastmod: 2025-03-01T10:00:00+00:00
draft: false
author: "Yi"
description: "Official PyTorch implementation for our MICCAI 2024 paper: 'Revisiting Deep Ensemble Uncertainty for Enhanced Medical Anomaly Detection'."
images: ["featured-image.jpg"]
resources:
- name: "featured-image"
  src: "overview.png"
tags: ["deep learning", "Anomaly detection"]
categories: ["Research", "Implementation"]
twemoji: false
lightgallery: true
---
This repository hosts the official PyTorch implementation of our MICCAI 2024 early accepted paper, "Revisiting Deep Ensemble Uncertainty for Enhanced Medical Anomaly Detection".
<!--more-->

**Key Concepts: Redundancy-Aware Repulsion & Dual-Space Uncertainty**

{{< figure src="./intro.png" title="D2UE" >}}


- **(a) Redundancy-Aware Repulsion (RAR):** Enhances the disagreement among learners in feature space for anomalous inputs, while normal samples converge to similar reconstructions during training.
- **(b) Feature Visualization:** A t-SNE plot shows how RAR pushes apart feature representations from three different learners when anomalies are present.
- **(c) Dual-Space Uncertainty (DSU):** In a 1D regression setting, DSU leverages the gradient discrepancy $\nabla_{X}{f}$ to better identify anomalies compared to solely using output space uncertainty.

**Overview of D2UE**

{{< figure src="./overview.png" title="Overview of D2UE" >}}

During training, the redundancy-aware repulsion module enforces diversity by incorporating both isotropic and scaling invariance. In the inference phase, dual-space uncertainty is computed using the model outputs $f(X)$ and the gradient information $\nabla_{X}\mathcal{L}$, offering a robust metric for anomaly detection.

**Visualization of Results**

{{< figure src="./visualizations.png" title="Visualization of Results" >}}

## Data Preparation

Manually organize the Med-AD benchmarks by following the detailed [data preparation guidelines](https://github.com/caiyu6666/DDAD-ASR/tree/main/data).

## Environment Setup

Ensure your system meets the following requirements:
- **GPU:** NVIDIA GeForce RTX 3090
- **Python:** 3.8.16
- **CUDA:** 11.7

Set up your Python environment with:

```bash
conda create --name d2ue python=3.8.16
conda activate d2ue
pip install torch==2.0.0+cu117 --index-url https://download.pytorch.org/whl/cu117
```

### Required Packages

Install all dependencies via:

```bash
pip install -r requirements.txt
```

## Train and Evaluate

All training scripts are located in the `scripts/` directory with configuration files in `cfgs/`. For instance, to train and evaluate the model on the RSNA dataset using an AE backbone, run:

```bash
./scripts/RSNA_AE.sh
```

Pre-trained models and detailed results can be found on our [release page](https://github.com/Rubiscol/D2UE/releases/tag/publish).

## Acknowledgements

We gratefully acknowledge the following open-source projects and datasets that supported our research:

### Code Repositories

1. [DDAD-ASR](https://github.com/caiyu6666/DDAD-ASR)
2. [CKA-similarity](https://github.com/jayroxis/CKA-similarity)

### Datasets

1. [RSNA Pneumonia Detection Challenge](https://www.kaggle.com/c/rsna-pneumonia-detection-challenge)
2. [Vin-BigData Chest X-ray Abnormalities Detection (VinDr-CXR)](https://www.kaggle.com/c/vinbigdata-chest-xray-abnormalities-detection)
3. [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)
4. [Large-scale Attention-based Glaucoma (LAG) Dataset](https://github.com/smilell/AG-CNN)

## Citation

If our work proves helpful, please cite our paper:

```bibtex
@misc{gu2024revisitingdeepensembleuncertainty,
      title={Revisiting Deep Ensemble Uncertainty for Enhanced Medical Anomaly Detection}, 
      author={Yi Gu and Yi Lin and Kwang-Ting Cheng and Hao Chen},
      year={2024},
      eprint={2409.17485},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2409.17485}, 
}
```
