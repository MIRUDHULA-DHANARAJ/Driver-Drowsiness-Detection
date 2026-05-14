# 🧠 Driver Drowsiness Detection System
### Real-time AI-powered Fatigue Monitoring using Deep Learning & Transfer Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B.svg)](https://streamlit.io/)

## 🚀 Overview
Driver fatigue is a major contributor to road accidents globally due to delayed reaction time and reduced attention. This project presents an end-to-end AI system that detects driver drowsiness using facial cues such as eye closure and yawning.

The system combines **Deep Learning classification**, **Rule-based reasoning**, and **Temporal fatigue analysis** to deliver interpretable and real-time insights.

---

## 🎯 Key Highlights
*   **Dual-model architecture:** Comparison between a Custom CNN and MobileNetV2.
*   **4-Class Detection:** Detects Eye state (Open/Closed) + Yawning state (Yawn/No Yawn).
*   **Rule-based Fatigue Mapping:** A 3-stage logic system (Alert, Mild, Severe).
*   **Temporal Tracking:** Analyzes fatigue progression over time rather than just static frames.
*   **Interactive Dashboard:** Built with Streamlit for real-time visualization and analytics.

---

## 🏗️ System Architecture
1.  **Input Image:** Preprocessing (Resize to $224 \times 224$, Normalization).
2.  **Model Inference:** MobileNetV2 / CNN prediction across 4 classes.
3.  **Rule Engine:** Maps predictions to fatigue levels.
4.  **Temporal Aggregation:** Groups predictions into time windows to create a **Fatigue Progression Curve**.
5.  **Visualization:** Streamlit UI displays current state and historical trends.

---

## 📂 Dataset Description
*   **Source:** Public facial drowsiness dataset.
*   **Classes:** `Closed`, `Open`, `no_yawn`, `yawn`.
*   **Preprocessing:**
    *   Resize: $224 \times 224$
    *   Normalization: $[0, 1]$
    *   Augmentation: Flip, Rotation, Zoom, Brightness.
    *   Split: 70% Train / 15% Val / 15% Test.

---

## 🤖 Model Architecture & Performance

### 1. Custom CNN (Baseline)
*   4 Convolutional Blocks + Batch Normalization.
*   Global Average Pooling & Fully Connected Layer.
*   **Accuracy:** ~25% (Used as a starting point).

### 2. MobileNetV2 (Final Model)
*   Pretrained on ImageNet (Transfer Learning).
*   Frozen base layers for feature extraction; fine-tuned top layers.
*   **Accuracy:** **~91%** (Lightweight and deployment-ready).

| Model | Accuracy | Notes |
| :--- | :--- | :--- |
| Custom CNN | ~25% | Baseline model |
| **MobileNetV2** | **~91%** | **Best performing & optimized** |

---

## ⚙️ Fatigue Decision Logic

| Prediction Class | Fatigue Level | Status |
| :--- | :--- | :--- |
| Open / No_yawn | 0 | 🟢 **Alert** |
| Yawn | 1 | 🟡 **Mild** |
| Closed | 2 | 🔴 **Severe** |

---

## 📷 Dashboard Preview
The **Streamlit Dashboard** consists of:
*   **Home Page:** Project overview and documentation.
*   
  <img width="1356" height="633" alt="home" src="https://github.com/user-attachments/assets/7c7760d0-34c0-4fed-b267-6b43f2893520" />

*   **Prediction Interface:** Upload/capture images for real-time inference.

  <img width="1364" height="632" alt="prediction" src="https://github.com/user-attachments/assets/def75d56-3fb5-497e-aff8-1bdca26d5501" />
   
*   **Analytics Dashboard:** Visualizing fatigue transitions (Alert → Mild → Severe) via Plotly.

  <img width="1357" height="636" alt="analytics" src="https://github.com/user-attachments/assets/2c555ba1-7ce9-4297-8a61-4cee341e73dd" />


---

## 🖥️ Run Locally

1. **Clone Repository**
   ```bash
   git clone [https://github.com/your-username/Driver-Drowsiness-Detection.git](https://github.com/your-username/Driver-Drowsiness-Detection.git)
   cd Driver-Drowsiness-Detection

2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   Run Streamlit App
   
3. **Run Streamlit App**
   ```bash
   streamlit run drowsiness_dashboard.py
---

## 🧩 Tech Stack
*   **Deep Learning:** TensorFlow / Keras
*   **Data Science:** NumPy, Scikit-learn, Pandas
*   **Visualization:** Matplotlib, Plotly, Streamlit
*   **Computer Vision:** OpenCV

---

## 📁 Project Structure
```text
Driver-Drowsiness-Detection/
│
├── drowsiness_detection.ipynb    # Training & Evaluation Notebook
├── drowsiness_dashboard.py      # Streamlit Application
├── assets/                      # UI Images & Icons
│   ├── home.png
│   ├── prediction.png
│   └── analytics.png
├── requirements.txt             # Dependencies
└── README.md                    # Project Documentation
```
---
## 👩‍💻 Author
Mirudhula D
B.Tech Artificial Intelligence & Data Science
---
**Final Note:** This project demonstrates a complete end-to-end AI product pipeline: from dataset processing and model training to a deployment-ready analytical dashboard.
