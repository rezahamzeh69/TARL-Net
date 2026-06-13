# TARL-Net: Self-Supervised Transformer-LSTM Network for Explainable Open-Set Intrusion Detection

This repository contains the official implementation of **TARL-Net**, developed as part of a PhD dissertation for advanced cyberattack prediction and intrusion detection in network security.

## 🚀 Key Features
* **Hybrid Architecture:** Combines Transformers and BiLSTMs for deep sequential feature extraction.
* **Open-Set Recognition (OSR):** Capable of identifying unknown attack types (e.g., holding out 'Reconnaissance').
* **Self-Supervised Learning (SSL):** Pre-training strategy to capture robust network log representations.
* **Explainable AI (XAI):** Built-in attention rollout to interpret per-timestep importance and highlight top critical features.
* **Continual Learning:** Integrated with EWC (Elastic Weight Consolidation) and replay mechanisms.

## 📊 Dataset
Tested on the **UNSW-NB15** dataset with multi-class attack categories.

## 📈 Ablation Results Summary
Our comprehensive evaluation demonstrates the significance of each module:
* **Full TARL-Net:** Accuracy: `99.74%`, F1-Macro: `0.5529`, OSR AUROC: `0.9710`
* **Without Transformer:** F1-Macro drops significantly to `0.3343`
* **Without LSTM:** Accuracy: `99.55%`, F1-Macro: `0.4281`
