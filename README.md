# Transfer Learning with Tensorflow
# 🐶🐱 Cats vs Dogs Classification using Transfer Learning (MobileNetV2)

## 📌 Project Overview

This project demonstrates how to build an image classification model to distinguish between cats and dogs using **transfer learning**. A pre-trained convolutional neural network (MobileNetV2) trained on ImageNet is used as a **feature extractor**, and custom layers are added for binary classification.

The project compares:

* A **baseline CNN model built from scratch**
* A **transfer learning model using MobileNetV2**

The results clearly show the advantage of transfer learning, especially when working with **small datasets**.

---

## 🎯 Objectives

* Build a benchmark CNN model using the Functional API
* Implement transfer learning using a pre-trained model
* Freeze pretrained layers and train a custom classifier head
* Evaluate and compare both models
* Visualize performance using learning curves and confusion matrices

---

## 📂 Dataset

* Subset of the **Dogs vs Cats dataset (Kaggle 2013)**
* Originally part of the **Asirra CAPTCHA dataset**
* Total samples used:

  * Training: 600 images
  * Validation: 300 images
  * Test: 300 images

### 📊 Preprocessing

* Images resized to **(160 × 160 × 3)**
* Pixel values normalized to **[0, 1]**

---

## 🧠 Models Implemented

### 1️⃣ Benchmark CNN Model

A custom convolutional neural network built from scratch with:

* 3 convolutional blocks (32 → 64 → 128 filters)
* Max pooling layers
* Fully connected dense layer (128 units)
* Output layer with sigmoid activation

**Total parameters:** ~6.8M

---

### 2️⃣ Transfer Learning Model (MobileNetV2)

* Pretrained MobileNetV2 used as a **feature extractor**
* Added layers:

  * Dense (32 units, ReLU)
  * Dropout (0.5)
  * Dense (1 unit, Sigmoid)
* Base model weights **frozen**

**Trainable parameters:** ~41K
**Non-trainable parameters:** ~2.25M

---

## ⚙️ Training Configuration

* Optimizer: RMSprop (learning rate = 0.001)
* Loss: Binary Crossentropy
* Metric: Accuracy
* Callback: EarlyStopping (patience = 2)
* Batch size: 32
* Epochs: up to 10

---

## 📈 Results

| Metric              | Benchmark CNN | Transfer Learning CNN |
| ------------------- | ------------- | --------------------- |
| Training Accuracy   | 64.5%         | 91.0%                 |
| Validation Accuracy | 51.7%         | 84.0%                 |
| Test Accuracy       | 52.0%         | **85.3%**             |
| Test Loss           | 0.700         | **0.372**             |

---

## 📊 Key Observations

* The benchmark model **struggles to generalize** due to limited data
* Transfer learning significantly improves:

  * Accuracy
  * Convergence speed
  * Generalization performance
* Pretrained features from ImageNet are highly effective even for small datasets

---

## 🔍 Visualizations

* Training vs validation accuracy and loss curves
* Confusion matrices for both models

  * Transfer learning model shows **fewer misclassifications**

---

## 🚀 Why This Project Matters

This project demonstrates:

* Practical application of **transfer learning**
* Efficient model building with **limited data**
* Understanding of **deep learning architectures**
* Ability to compare and evaluate models rigorously

---

## 🛠️ Tech Stack

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib & Seaborn
* Scikit-learn

---

## 📌 Future Improvements

* Fine-tuning deeper layers of MobileNetV2
* Data augmentation to improve robustness
* Hyperparameter tuning
* Using more advanced architectures (EfficientNet, ResNet)
* Expanding dataset size

---

## 📎 How to Run

1. Clone the repository
2. Ensure dataset `.npy` files are in the `/data` directory
3. Ensure pretrained model is in `/models/MobileNetV2.h5`
4. Run the notebook

---

## ⭐ Key Takeaway

> Transfer learning allows you to build powerful models with minimal data by leveraging knowledge from large-scale pretrained networks.
