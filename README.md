# DevSpore
AI-Enabled Digital Holographic Microscopy for Blood Disease Classification

DevSpore is an end-to-end research project that integrates Digital Holographic Microscopy (DHM) with Artificial Intelligence to enable automated blood disease classification. The system transforms holographic phase information into quantitative biological features and applies a MindSpore-based neural network to perform classification.

This project demonstrates how physics-based imaging and machine learning can be combined to build scalable, low-cost biomedical diagnostic tools.

## Overview

The DevSpore pipeline consists of multiple stages:

1. Holographic Image Acquisition
Interferometric imaging captures phase-encoded holograms of blood samples.

2. Holographic Reconstruction
Fourier-based processing generates quantitative phase maps.

3. Segmentation
Blood cells are isolated using the Segment Anything Model (SAM).

4. Feature Extraction
Physics-based equations convert phase data into morphological features such as:

- Thickness statistics

- Geometric descriptors

- Volume estimates

- Shape metrics

5. AI Classification (MindSpore)
A custom Multilayer Perceptron (MLP) classifier predicts disease labels from extracted features.

## AI Module (MindSpore)

The AI module is implemented using MindSpore, providing:

- Dataset preparation

- Neural network training

- Evaluation and inference

- Model Architecture

    - Input: 19 extracted DHM features

    - Hidden Layers: Fully connected layers with ReLU activation

    - Output: 2-class Softmax classifier

- Loss Function:

    - SoftmaxCrossEntropyWithLogits

- Optimizer:

    - Adam
## Dataset

Total Samples: 417

Task: Binary classification

Labels:

0 → Healthy

1 → Malaria

Each sample represents features extracted from reconstructed DHM phase images.
```bash
📁 Repository Structure (Suggested)
DevSpore/
│
├── ai/
│   ├── mindspore_classifier.py
│   └── training_pipeline.ipynb
│
├── dhm/
│   ├── feature_extractor.py
│   ├── phase_processing.py
│   └── segmentation/
│
├── data/
│   └── merged_blood_dataset.xlsx
│
└── README.md
```
## Installation
1️. Create Environment
```bash 
python -m venv devspore_env
devspore_env\Scripts\activate
```
2️ Install Dependencies
```bash
pip install mindspore numpy pandas scikit-learn openpyxl
```
## Running the AI Classifier

Open:
```bash
MindSpore.ipynb
```

## Feature Extraction

Features are computed from phase maps using quantitative DHM equations
Extracted features include:

mean_thick

std_thick

volume

sphericity

skewness & kurtosis

geometric descriptors

## Results

The classification module achieved strong performance on the test dataset, with 97% recall, demonstrating the feasibility of integrating DHM with AI for automated diagnostics. 

## Motivation

Diagnosing blood diseases often requires specialized laboratory infrastructure. DevSpore explores how low-cost DHM imaging combined with AI can improve accessibility to diagnostic tools, particularly in resource-limited settings.

