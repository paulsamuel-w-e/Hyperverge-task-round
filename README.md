# Hyperverge-task-round
colab link: (https://colab.research.google.com/drive/1IEu-CWIthKMRRt8kfVZIaG13-iSPgC4_?usp=sharing)

# 🔍 Hyperverge Deep Learning Task (Placement Exam - 2025)

This repository contains my submission for the **Hyperverge Placement Task Round**, where I was required to build a deep learning image classification model in **two phases**:

- 📌 **Phase 1**: Supervised Learning using **only labeled data**
- 🔄 **Phase 2**: Semi-Supervised Learning using both **labeled** and **unlabeled** data

---

## 📁 Repository Structure

Hyperverge-task-round/
├── phase1/
│   ├── phase1_final_model.pth
│   ├── phase1_label_encoder.pkl
│   ├── phase1_prediction.csv
│
├── phase2/
│   ├── phase2_final_model.pth
│   ├── phase2_label_encoder.pkl
│   ├── phase2_prediction.csv
│   └── Trial Benchmarks/
│       ├── previous_label_encoder.pkl
│       └── previous_model.pts


---

## ✅ Phase 1: Supervised Learning

In this phase, I trained a **ResNet-18** model on the labeled dataset.

### 🔧 Techniques Used

- ✅ **Transfer Learning** with pretrained ResNet-18
- 🧮 **CrossEntropy Loss** with **Class Weightage Counts**
- 🧼 **Image Preprocessing**:
  - Resize to `224x224`
  - Normalization (ImageNet stats)
  - Rotation handling based on data analysis
- 🔁 **Early Stopping** for regularization

### 📉 Result

- **Best Accuracy Achieved (Lost Model)**: 19%
- **Final Available Accuracy**: 17%
- Model saved as: `phase1_final_model.pth`

---

## 🔁 Phase 2: Semi-Supervised Learning

In this phase, I used both labeled and unlabeled data with a semi-supervised learning pipeline based on the **FixMatch algorithm**.

### 🛠️ Final Components (After Optimization)

- 📌 **FixMatch Algorithm**:
  - Pseudo-labeling with confidence threshold
  - Consistency regularization with strong and weak augmentations
- ⚖️ **Class Weightage Counts** in CrossEntropy Loss
- 🔄 **Rotation Correction**:
  - Unlabeled dataset was rotated **180°**
  - Test dataset was rotated **90°**
  - Handled via appropriate augmentations
- 🔁 **Weak + Strong Augmentation** design to match FixMatch expectations

### 🚫 Removed Techniques (Due to Accuracy Drop)

The following were experimented with but **not used in the final model**:
- ❌ Focal Loss
- ❌ EMA (Exponential Moving Average)
- ❌ L2 Regularization
- ❌ Weighted Loss via frequency balancing

### 📈 Final Result

- **Final Accuracy**: **71.72%**
- Model saved as: `phase2_final_model.pth`

---

## 📄 Files Overview

| File Name                  | Description                                 |
|---------------------------|---------------------------------------------|
| `phase1_prediction.csv`   | Predictions for test data in Phase 1        |
| `phase1_label_encoder.pkl`| Label encoder used in Phase 1               |
| `phase1_final_model.pth`  | Final ResNet-18 model after Phase 1         |
| `phase2_prediction.csv`   | Predictions for test data in Phase 2        |
| `phase2_label_encoder.pkl`| Label encoder used in Phase 2               |
| `phase2_final_model.pth`  | Final model with semi-supervised learning   |

---

## 📊 Summary Table

| Phase  | Methodology                        | Accuracy  |
|--------|-------------------------------------|-----------|
| 1️⃣     | Supervised (ResNet-18 + Class Weight) | 17%       |
| 2️⃣     | FixMatch + Class Weight + Rotation Correction | **71.72%** |

---

## ✨ Highlights

- Detected and corrected **rotational inconsistencies** in unlabeled and test datasets
- Efficient usage of **FixMatch** for unlabeled data exploitation
- Achieved a **4x accuracy improvement** using semi-supervised methods
- Minimalistic yet powerful design with **no over-regularization**

---

## 🧠 Insights

- Simplicity beats complexity: removing Focal Loss and EMA improved final results
- Data orientation can drastically affect model performance if not corrected
- Class imbalance should be addressed even in semi-supervised settings

---

## 📫 Contact

Feel free to reach out if you'd like to collaborate or discuss this work!

**Paul Samuel**  
📧 [work.paulsamuel@gmail.com]  
🏫 [Kumaraguru College of Technology]