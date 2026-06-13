# TARL-Net: Self-Supervised Transformer-LSTM Network for Explainable Open-Set Intrusion Detection

This repository contains the official implementation of **TARL-Net**, a novel deep learning framework designed for advanced network intrusion detection and cyberattack prediction in critical environments.

## 🚀 Core Contributions
* **Hybrid Architecture:** Seamless integration of Transformers and Bidirectional LSTMs (BiLSTM) for robust sequential feature learning from network logs.
* **Self-Supervised Learning (SSL):** Pre-training strategy to capture deep baseline data representations before supervised tuning.
* **Open-Set Recognition (OSR):** Advanced capability to detect unknown or zero-day attacks, validated using Leave-One-Attack-Family-Out (LOAFO) validation.
* **Explainable AI (XAI):** Integrated Attention Rollout mechanism to provide per-timestep importance and pinpoint critical features.
* **Continual Learning:** Feature drift management using Elastic Weight Consolidation (EWC) and replay mechanisms.

## 📊 Dataset & Framework Configuration
* **Dataset:** UNSW-NB15
* **Target Classes:** Normal, Fuzzers, Analysis, Backdoor, DoS, Exploits, Generic, Reconnaissance, Shellcode, Worms.
* **Input Sequence Shape:** (16, 26) - 16 Timesteps with 26 Selected Features.

## 📈 Experimental Results (Ablation Study)
The importance of each architectural component was rigorously evaluated under the Open-Set Recognition scenario (holding out the 'Reconnaissance' family):

| Model Variant | Accuracy | F1-Macro | OSR AUROC | Unknown Recall |
| :--- | :---: | :---: | :---: | :---: |
| **TARL-Net (Full)** | **0.9974** | **0.5529** | **0.9710** | **0.8404** |
| Without Transformer | 0.9946 | 0.3343 | 0.9683 | 0.7872 |
| Without LSTM | 0.9955 | 0.4281 | 0.9715 | 0.8617 |
| Without Phi Module | 0.9956 | 0.3736 | 0.9735 | 0.9255 |
| Without SSL Pre-training | 0.9962 | 0.4053 | 0.9654 | 0.8404 |
| Scalar Gate Variant | 0.9968 | 0.5104 | 0.9712 | 0.8723 |

### 🛠️ Key Validation Highlights
* **Closed-Set Baseline:** Achieved `99.16%` accuracy when all classes were known.
* **LOAFO (Reconnaissance Held Out):** Successfully recalled `89.36%` of completely unseen reconnaissance attacks with an OSR AUROC of `0.9691`.
* **XAI Fidelity:** Deletion score of `0.1391` and Insertion score of `0.8479` verify the high reliability of the explainability module.

## ⚙️ Requirements & Installation
To run this notebook, ensure you have a CUDA-enabled device and install the required dependencies:
```bash
pip install -r requirements.txt