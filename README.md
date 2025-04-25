# Fair Medical Image Reconstruction and Evaluation

This repository provides an overview and integration of multiple projects focused on **bias evaluation and mitigation in medical image reconstruction**, specifically applied to the **UCSF-PDGM MRI** and **CheXpert chest X-ray** datasets. It includes reconstruction methods (U-Net, GAN, SDE), mitigation strategies (reweighting, adversarial training, Equalized Odds), and a comprehensive evaluation pipeline.

## Introduction

The growing adoption of artificial intelligence in medical imaging has underscored the importance of fairness, ensuring that applied deep learning models do not introduce new or aggravate existing biases. Our research contributes to this space with two core contributions:

1. **Bias Evaluation**: We introduce a framework to assess how reconstruction models affect fairness in downstream tasks. By varying noise levels and applying different reconstruction techniques, we reveal conditions where disparities arise across sensitive attributes such as sex and age.

2. **Bias Mitigation**: We investigate three fairness interventions—sample reweighting, Equalized Odds (EODD), and adversarial training—applied to U-Net, Pix2Pix, and SDE models. Our experiments quantify trade-offs in reconstruction quality and downstream fairness, emphasizing that reconstruction has limited elasticity to significantly reduce bias.

---

## Repositories Overview

This meta-repo connects and documents the following projects:

### 1. [recon_bias](https://github.com/lotterlab/recon_bias.git)

> **Reconstruction & Classification for UCSF and CheXpert**

Contains U-Net-based reconstruction models and classifiers. Includes multiple branches for different datasets and mitigation strategies.

- **Branches**:
  - `ucsf`: UCSF-PDGM reconstruction, classification, segmentation
  - `chexpert`: CheXpert reconstruction and classification
  - `reweighting`, `eodd`, `adversarial`: Bias mitigation strategies

---

### 2. [pix2pix](https://github.com/MatteoWohlrapp/pix2pix.git)

> **Forked GAN Architecture for CheXpert & UCSF**

Pix2Pix GAN modified to support UCSF-PDGM and CheXpert datasets. Includes fairness interventions.

- **Branches**:
  - `master`: Standard reconstruction
  - `reweighting`, `eodd`, `adversarial`: Bias mitigation techniques

---

### 3. [image-restoration-sde](https://github.com/MatteoWohlrapp/image-restoration-sde.git)

> **Diffusion-Based Image Restoration**

Stochastic Differential Equation (SDE) model adapted for medical image reconstruction and fairness experiments.

- **Branches**:
  - `main`: Base version
  - `reweighting`, `eodd`, `adversarial`: Mitigation strategies

---

### 4. [recon_bias_evaluation](https://github.com/MatteoWohlrapp/recon_bias_evaluation.git)

> **Evaluation & Visualization Framework**

Evaluation tools for reconstruction quality, downstream classification/segmentation, and fairness metrics across demographic groups. Also includes visualization and reporting utilities.

- **Modules**:
  - `processing/`: Batch processing of datasets through models
  - `prediction/`: Task-specific inference modules
  - `evaluation/`: Fairness analysis, AUROC/PSNR reporting
  - `visualization/`: Heatmaps, Grad-CAM, segmentation overlays

---

### 5. [torchxrayvision (fork)](https://github.com/mlmed/torchxrayvision)

> **X-Ray Classification Backbone (adapted for CheXpert)**

Used as a downstream model for evaluating reconstruction-induced bias. Our fork includes minor dataset integration adjustments.

---

## How to Use This Project

### 1. Clone Submodules (if using this as a meta-repo)
```bash
git clone --recurse-submodules https://github.com/your-user/meta-repo.git
```
Or clone manually each sub-repository if preferred.

### 2. Explore Individual Repositories

Each repository contains its own instructions and configuration. See the individual README.md files in each repo for branch-specific code usage, dataset preparation, model training, evaluation and visualization pipelines.


## Results
