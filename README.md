# Comparative-EEG-Signal-Denoising-Using-Neural-Networks-with-Heatmap-and-Computational-Cost-Analysis

This repository contains the official implementation of the experimental framework
presented in the article:

**Comparative Analysis of EEG Signal Denoising Techniques in Brain–Computer Interfaces
Using Neural Networks and Deep Learning: Heatmap Visualization and Computational Cost Evaluation**

The purpose of this repository is to provide a **reproducible and transparent implementation**
of the algorithms, experimental protocol, and evaluation metrics used to compare
different neural network architectures for EEG signal denoising in Brain–Computer
Interface (BCI) applications.

---

## 1. Problem Statement

Electroencephalographic (EEG) signals are highly susceptible to artifacts such as
ocular (EOG), muscular (EMG), cardiac (ECG), and environmental noise. These artifacts
severely affect the performance of BCI systems, particularly in real-time and
resource-constrained environments.

Recent deep learning–based denoising methods have demonstrated high reconstruction
accuracy; however, they often involve significant computational complexity,
which limits their applicability in real-time BCIs and embedded systems.

This work investigates whether **lighter neural architectures**, particularly the
**Recurrent High-Order Neural Network (RHONN)**, can achieve denoising performance
comparable to deep learning models while significantly reducing computational cost.

---

## 2. Evaluated Algorithms

The following neural network–based denoising algorithms are implemented and evaluated:

- Multilayer Perceptron (MLP)
- Recurrent Neural Network (RNN)
- Autoencoder
- Generative Adversarial Network (GAN)
- Transformer
- Recurrent High-Order Neural Network (RHONN)

All algorithms operate under a **channel-wise denoising strategy**, where each EEG
channel from the international 10–20 system is processed independently. This approach
preserves spatial information and enables channel-level performance analysis.

---

## 3. Dataset Description

The experiments are conducted using the EEG/EOG dataset proposed by **Klados and Bamidis**,
which provides clean EEG signals and synthetically contaminated EEG signals generated
using a realistic biophysical artifact model.

**Dataset characteristics:**
- 19 EEG channels following the international 10–20 system
- Original sampling rate: 200 Hz (resampled to 256 Hz)
- Window length: 2 seconds (512 samples)
- Artifact sources: ocular, muscular, cardiac, and environmental noise

Due to size and licensing restrictions, the dataset is **not included** in this repository.
Users must obtain the dataset directly from the original authors.

---

## 4. Experimental Protocol

The experimental methodology strictly follows the protocol described in the article
and is divided into **two main experiments: Test A and Test B**.

---

## 4.1 Test A: Inference with Pretrained Models

**Test A** evaluates the denoising capability of **pretrained neural network models**
without performing any additional training.

### Description
- Pretrained models reported in the literature are used.
- EEG signals are resampled, segmented, and normalized.
- Each EEG channel is processed independently.
- Models are applied directly to previously unseen contaminated EEG signals.

### Objective
- Evaluate the **generalization capability** of each algorithm.
- Compare reconstruction accuracy across EEG channels.
- Analyze spatial performance using channel-wise metrics and heatmap visualizations.

This test reflects realistic deployment conditions, where pretrained models are
used in real-time BCI systems.

---

## 4.2 Test B: Training and Cross-Validation from Raw Data

**Test B** evaluates the performance of the algorithms when trained directly from
the available EEG data.

### Description
- EEG signals are segmented into 2-second windows.
- A **5-fold cross-validation** strategy is applied.
- Training and validation are performed independently for each EEG channel.
- Performance metrics are averaged across folds.

### Objective
- Analyze training stability and robustness.
- Compare learning behavior among different architectures.
- Evaluate performance under controlled and reproducible training conditions.

---

## 5. Evaluation Metrics

The denoising performance is assessed using time-domain, frequency-domain, and
statistical similarity metrics:

- Mean Squared Error (MSE)
- Relative Root Mean Square Error (RRMSE)
- Pearson Correlation Coefficient
- Spearman Rank Correlation
- Signal-to-Noise Ratio (SNR)
- Structural Similarity Index (SSIM)
- Mutual Information (MI)

Spatial performance is evaluated using **channel-wise heatmaps** mapped onto the
EEG 10–20 electrode layout.

---

## 6. Computational Cost Analysis

In addition to reconstruction accuracy, the computational cost of each algorithm
is evaluated, considering:

- Training time
- Inference time
- Model complexity
- Suitability for real-time and low-power BCI applications

This analysis supports a **Green AI perspective**, emphasizing efficiency alongside
performance.

---

## 7. Repository Structure

The repository is organized to reflect the experimental workflow described above:
