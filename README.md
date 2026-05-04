# 👁️ Optix AI: AI-Powered Retinal Diagnostic Suite
**Bridging the Gap Between Deep Learning and Clinical Interpretation.**

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://optix-ai.streamlit.app/)

## 📌 Project Overview
Optix is a professional-grade **Clinical Decision Support System (CDSS)** designed to assist ophthalmologists in interpreting OCT scans. It bridges the gap between AI predictions and clinical trust by combining Deep Learning with **Explainable AI (XAI)** and **Medical RAG**.

> **🚀 Try it yourself:** Don't have an OCT scan? We've provided a **[Sample Dataset Folder](./Sample_Scans)** in this repo. Download an image from there and upload it to the web app to see the diagnostic engine in action!

---

## 📸 System Preview
| 🖼️ AI Diagnosis & Heatmap | 💬 Clinical Assistant (RAG) |
| :--- | :--- |
| ![App Screenshot](Images/App_Main_View.png) | ![Chatbot Screenshot](Images/Chatbot_View.png) |


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


<div align="center">
  
### 📊 Performance Visualization

![Confusion Matrix](Images/Confusion_Matrix.png)

</div>


> **Clinical Interpretation:** The confusion matrix demonstrates high sensitivity in identifying **DME** and **CNV** cases. The minimal overlap between classes indicates that the model has successfully learned the distinct morphological features of retinal pathologies, ensuring reliable decision support for practitioners.


---

## 🛠️ Technology Stack
Optix was built using an industry-standard stack to ensure scalability and clinical accuracy.

<div align="center">

| Layer | Technologies |
| :--- | :--- |
| **Deep Learning** | `TensorFlow` `Keras` `OpenCV` |
| **Explainable AI** | `Grad-CAM` `Matplotlib` `NumPy` |
| **LLM & RAG** | `Google Gemini 3.1 Flash` `Clinical RAG` |
| **Frontend/UI** | `Streamlit` `HTML5/CSS3` |
| **Environment** | `Python 3.10+` `GitHub` |

</div>

---


## 🔬 Architecture & Training
The classification engine is built on a transfer learning backbone, optimized for medical feature extraction.

*   **Backbone:** `MobileNetV3Large` (Pre-trained on ImageNet for efficient feature detection).
*   **Custom Head:** Global Average Pooling followed by a `Dense` layer with `Softmax` activation for 4-class classification.
*   **Training Specs:** 
    *   **Hardware:** Trained on an `NVIDIA GTX 1660 Ti`.
    *   **Duration:** ~2 hours and 44 minutes for 15 epochs.
    *   **Optimization:** Adam optimizer with categorical cross-entropy loss.

<div align="center">

### 📈 Training Progress
![Training Loss & Accuracy](Images/Loss_Plot.png)

*Visualizing the convergence of training and validation loss over 15 epochs.*

</div>

---


## 📁 Dataset & Citations
The model was trained and validated using the [**Labeled Optical Coherence Tomography (OCT)**](https://www.kaggle.com/datasets/anirudhcv/labeled-optical-coherence-tomography-oct) dataset. 

### 📊 Data Distribution
To ensure robust generalization and prevent overfitting, the **109,309 high-resolution images** were partitioned using a strict split:

*   **Training Set (70%):** ~76,516 images used for weight optimization.
*   **Validation Set (20%):** ~21,862 images used for hyperparameter tuning and early stopping.
*   **Test Set (10%):** ~10,931 images reserved for final unbiased performance evaluation.

> **Primary Citation:** 
> Kermany D, Goldbaum M, Cai W et al. *Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning.* **Cell.** 2018; 172(5):1122-1131. [doi:10.1016/j.cell.2018.02.010](https://doi.org/10.1016/j.cell.2018.02.010).
---

## 🛡️ Clinical Trust & Explainability (XAI)
Optix is not a "black box." It provides visual and textual evidence for every diagnostic decision.

### 🔍 Neural Focus Mapping (Grad-CAM)
The system highlights the specific morphological features (subretinal fluid, drusen, etc.) that triggered the AI's classification.

| 🏥 Original OCT Scan | 🔥 Neural Attention Heatmap |
| :--- | :--- |
| ![Original Scan](Images/Sample_Scan.png) | ![Heatmap View](Images/Sample_Heatmap.png) |

### 📚 Evidence-Based Consultation (RAG)
By grounding **Gemini 3.1 Flash** in clinical guidelines, the assistant provides management suggestions directly linked to the detected pathology.
*   **Context-Aware:** The chatbot knows it is looking at a "CNV" or "DME" result.
*   **Hallucination-Proof:** Answers are strictly synthesized from validated clinical context.

---

## 🚀 Features at a Glance
*   **One-Click Screening:** Instant classification into 4 clinical categories.
*   **Visual Evidence:** Automated Grad-CAM generation for every scan.
*   **Dynamic RAG Chat:** Ask follow-up questions grounded in medical literature.
*   **Cloud-Optimized:** Fully deployed and responsive on Streamlit Cloud.


---

## 💻 Local Setup (Optional)
If you'd like to run OptixAI locally:
1. **Clone the repo:** `git clone https://github.com/Yazdan-Ghanavati/OptixAI.git`
2. **Install requirements:** `pip install -r requirements.txt`
3. **Add API Key:** Create a `.env` file with your `GOOGLE_API_KEY`.
4. **Run:** `streamlit run Web_Application.py`

---

## 🤝 Connect & Collaborate
I am a Data Scientist and AI Developer specializing in Healthcare & Computer Vision. I am open to job opportunities, research collaborations, and discussions regarding the future of AI in Ophthalmology.

<div align="center">

### 📩 Request Full Access
The **Clinical Suite** (including the Grad-CAM XAI engine and the Gemini-powered RAG assistant) is available for demonstration and review by hiring managers and clinical researchers.

**[Click here to contact me on LinkedIn](https://www.linkedin.com/in/yazdan-ghanavati/)**

</div>

---

## 📜 How to Cite this Project
If you use this project's architecture or methodology, please use the following reference:

> **[Yazdan Ghanavati]. (2026). Optix: AI-Powered Retinal Diagnostic Suite.** Available at: `https://github.com/Yazdan-Ghanavati/OptixAI`

---




<div align="center">
  
**Developed with ❤️ for the future of Retinal Health.**

</div>
