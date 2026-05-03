# 👁️ Optix: AI-Powered Retinal Diagnostic Suite
**Bridging the Gap Between Deep Learning and Clinical Interpretation.**

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge.svg)](https://your-app-link-here.streamlit.app/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Note:** This repository contains the **Core Engine**. For the full Clinical Suite (including Grad-CAM XAI and RAG integration), please contact the developer via LinkedIn.

---

## 📌 Project Overview
Optix is a professional-grade medical imaging tool designed to assist ophthalmologists in detecting retinal diseases from OCT (Optical Coherence Tomography) scans. It doesn't just provide a diagnosis; it explains the "why" behind it using Clinical AI.


---

## 🧠 The Diagnostic Workflow
Optix uses a multi-layered approach to move from a raw image to a clinical recommendation:

1. **Classification:** A customized CNN architecture analyzes the OCT scan to identify one of four categories: **CNV, DME, DRUSEN,** or **NORMAL**.
2. **Explainability (XAI):** Gradient-weighted Class Activation Mapping (Grad-CAM) generates a heatmap to highlight exactly where the model detected pathology.
3. **Clinical Interpretation:** A Retrieval-Augmented Generation (RAG) system feeds clinical guidelines into **Gemini 3.1 Flash**, providing an evidence-based assistant for follow-up questions.

---
## 📊 Model Performance
The model was trained on a high-resolution OCT dataset and evaluated based on clinical precision.

<div align="center">


| Metric | Score |
| :--- | :--- |
| **Accuracy** | 94.8% |
| **F1-Score** | 0.95 |
| **Inference Speed** | ~2.026s |

</div>

### 📊 Performance Visualization

<div align="center">

![Confusion Matrix](Images/Confusion_Matrix.png)

</div>


> **Clinical Interpretation:** The confusion matrix demonstrates high sensitivity in identifying **DME** and **CNV** cases. The minimal overlap between classes indicates that the model has successfully learned the distinct morphological features of retinal pathologies, ensuring reliable decision support for practitioners.
