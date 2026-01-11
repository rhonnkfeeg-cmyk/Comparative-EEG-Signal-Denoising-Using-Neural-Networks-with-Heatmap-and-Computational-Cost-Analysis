# Comparative Analysis of EEG Signal Denoising Using Neural Networks:
Heatmap Visualization and Computational Cost Evaluation

This repository contains the official implementation of the experiments reported in the article:

Comparative Analysis of EEG Signal Denoising Using Neural Networks:
Heatmap Visualization and Computational Cost Evaluation

The code is organized exactly according to the experimental protocol described in the paper,
which is divided into two main experimental scenarios: **Test A** and **Test B**.

---

## 1. Project Overview

This work presents a comparative analysis of multiple neural network–based techniques
for EEG signal denoising in Brain–Computer Interface (BCI) applications. The study focuses on:

- EEG signal reconstruction quality
- Spatial behavior across EEG channels using heatmap visualization
- Computational cost and efficiency from a Green AI perspective

A channel-wise processing strategy is adopted, where each EEG channel is treated independently.

---

## 2. Evaluated Algorithms

The following neural network architectures are evaluated:

- Multilayer Perceptron (MLP)
- Recurrent Neural Network (RNN)
- Autoencoder
- Generative Adversarial Network (GAN)
- Transformer
- Recurrent High-Order Neural Network (RHONN)

All models operate independently on each EEG channel of the international 10–20 system.

---

## 3. Dataset Description

The EEG/EOG dataset used in this work follows the database proposed by Klados and Bamidis,
which provides clean EEG signals and synthetically contaminated EEG signals generated
using a realistic biophysical artifact model.

Dataset characteristics:
- 19 EEG channels (10–20 system)
- Original sampling rate: 200 Hz (resampled to 256 Hz)
- Window length: 2 seconds (512 samples)
- Artifact sources: ocular, muscular, cardiac, and environmental noise

Due to size and licensing restrictions, the dataset is not included in this repository.

---

## 4. Experimental Protocol

The experimental methodology strictly follows the protocol described in the article
and is divided into two complementary experimental scenarios:

- **Test A**: Evaluation using pretrained neural network models
- **Test B**: Training and evaluation using K-Fold cross-validation (K = 5)

---
## 5. Citation

If you use this repository, the source code, or any part of the experimental
methodology in your research, please cite the following article:

Martínez-Madrid, E., Medrano-Hermosillo, J. A., Ramírez-Quintana, J. A.,
López-Estrada, F. R., Suárez-Sierra, O. J., and Djilali, L.
**Comparative Analysis of EEG Signal Denoising Using Neural Networks:
Heatmap Visualization and Computational Cost Evaluation**.
Manuscript under review.

---
## 6. Repository Structure (Actual Implementation)

The repository is structured exactly as follows:

```text
Files/
│
├── Database/                         # EEG/EOG dataset (not included)
│
├── npy-matlab-master/                # MATLAB–Python interface
│
├── Test_A/                           # Test A: Pretrained model evaluation
│   └── PRETRAINED_TEST/
│       ├── TRAINING/
│       │   └── MODELS/               # Pretrained models
│       │
│       └── TEST/
│           ├── Sujeto_1/
│           ├── Sujeto_2/
│           ├── ...
│           ├── Sujeto_54/
│           │
│           ├── results/              # Metrics and heatmap outputs
│           │
│           ├── P1_Run_EEG_Models_all_tests.py
│           └── P2_Run_EEG_Models_results_and_heatmaps.py
│
├── Test_B/                           # Test B: K-Fold training and evaluation
│   ├── K1/
│   │   ├── TRAINING/
│   │   │   ├── MODELS/
│   │   │   ├── data_training_con.mat
│   │   │   ├── data_training_con.npy
│   │   │   ├── data_training_limp.mat
│   │   │   └── data_training_limp.npy
│   │   │
│   │   └── TEST/
│   │       ├── Sujeto_41/
│   │       ├── Sujeto_42/
│   │       ├── ...
│   │       ├── Sujeto_50/
│   │       │
│   │       ├── results/              # Metrics and heatmap outputs
│   │       │
│   │       ├── P1_Run_EEG_Models_all_tests.py
│   │       └── P2_Run_EEG_Models_results_and_heatmaps.py
│   │
│   ├── K2/
│   ├── K3/
│   ├── K4/
│   └── K5/
│
├── REQUIREMENTS.txt                  # Required software and libraries
├── RUN_INSTRUCTIONS.txt              # Instructions to run Test A and Test B
│
└── README.md




