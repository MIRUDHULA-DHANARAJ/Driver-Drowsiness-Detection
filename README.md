# 🧠 Driver Drowsiness Detection using Deep Learning

## 📌 Overview

Driver fatigue is a major cause of road accidents due to reduced alertness, slower reaction time, and impaired decision-making.
This project implements a **vision-based, non-intrusive driver monitoring system** that detects drowsiness using facial cues such as **eye closure and yawning**.

---

## 🎯 Problem Statement

Traditional fatigue detection systems rely on vehicle behavior or wearable sensors, which are often unreliable or intrusive.
This project aims to build a **deep learning-based solution** that can identify early signs of fatigue using image data.

---

## 🛠️ Approach

### 🔹 Data Processing

* Dataset contains 4 classes:

  * `Closed`
  * `Open`
  * `no_yawn`
  * `yawn`
* Images resized to **224×224**
* Normalization applied (0–1 scaling)
* Data augmentation:

  * Horizontal flip
  * Rotation
  * Zoom
  * Brightness variation

---

### 🔹 Model Development

#### 1. Custom CNN

* Multiple convolutional layers with batch normalization
* Feature extraction from scratch
* Fully connected classification head

#### 2. MobileNetV2 (Transfer Learning)

* Pretrained on ImageNet
* Base model frozen initially
* Fine-tuned with low learning rate

---

### 🔹 Decision Fusion Logic

Model predictions (4 classes) are mapped into **3 fatigue levels**:

| Prediction     | Fatigue Level         |
| -------------- | --------------------- |
| Open / no_yawn | 🟢 Alert (0)          |
| yawn           | 🟡 Mild Fatigue (1)   |
| Closed         | 🔴 Severe Fatigue (2) |

---

### 🔹 Fatigue Progression Analysis

* Predictions are grouped into **time intervals**
* Majority voting used to determine fatigue level per interval
* A **fatigue progression curve** is generated to track changes over time
* Transition points (Alert → Mild → Severe) are identified

---

## 📊 Results

* MobileNetV2 outperformed Custom CNN
* Better generalization due to pretrained features
* Reliable detection of eye closure (Severe fatigue)
* Minor confusion observed between `yawn` and `no_yawn`

---

## 📈 Key Features

* ✅ Non-intrusive fatigue detection system
* ✅ Deep learning-based image classification
* ✅ Rule-based fatigue level mapping
* ✅ Time-based fatigue progression tracking
* ✅ Transition detection for early warnings

---


## 🚀 Future Improvements

* Integrate real-time webcam detection using OpenCV
* Use temporal models (LSTM/GRU) for sequence learning
* Deploy as a real-time driver monitoring system

---

## 🧰 Tech Stack

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Scikit-learn

---

## 📂 Project Structure

```
Driver-Drowsiness-Detection/
│
├── drowsiness_detection.ipynb
├── README.md
└── requirements.txt
```

---

## ▶️ How to Run

1. Open the notebook in **Google Colab**
2. Install required libraries:

   ```
   pip install -r requirements.txt
   ```
3. Run all cells step-by-step

---

## 📌 Conclusion

This project demonstrates how deep learning can be applied to build a **practical driver safety system**.
By combining image classification with temporal analysis, it provides a **more reliable and interpretable fatigue detection mechanism**.

---

## 👩‍💻 Author

**Mirudhula D**
