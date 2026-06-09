# Handwriting Recognition — Deep Learning

> Personal Deep Learning project — Comparing MLP and CNN
> architectures on handwritten digit recognition (MNIST)
> using Keras/TensorFlow and PyTorch

![Python](https://img.shields.io/badge/python-3.11-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-red)
![Status](https://img.shields.io/badge/status-completed-brightgreen)

---

## 🎯 Overview

End-to-end Deep Learning project implementing and comparing
**MLP** and **CNN** architectures on the MNIST dataset
(70,000 handwritten digit images, 10 classes).

Key question answered : **Does CNN really outperform MLP
on image classification? By how much?**

---

## 📊 Results

| Model | Framework | Test Accuracy | Parameters |
|-------|-----------|---------------|------------|
| MLP | Keras/TF | 98.52% | 571,018 |
| MLP | PyTorch | 98.59% | 569,226 |
| **CNN** | **Keras/TF** | **99.61%** | **469,098** |
| **CNN** | **PyTorch** | **99.72%** | **468,458** |

> **Key finding** : CNN achieves **+1.2% accuracy** over MLP
> with **100K fewer parameters** — thanks to spatial feature
> extraction via convolutional filters.

---

## 🔍 Why CNN beats MLP on images

MLP : treats 784 pixels independently
-> no spatial awareness
-> 571K parameters
CNN : slides 3x3 filters across the image
-> detects local patterns (edges, curves)
-> weight sharing = fewer params
-> partial translation invariance
-> 469K parameters, better accuracy

---

## 🏗️ Architectures

### MLP

Input (784) → Dense(512) + BN + ReLU + Dropout(0.3)
→ Dense(256) + BN + ReLU + Dropout(0.3)
→ Dense(128) + BN + ReLU + Dropout(0.2)
→ Dense(10, Softmax)

### CNN

Input (28x28x1)
→ [Conv2D(32) + BN + ReLU] x2 + MaxPool + Dropout
→ [Conv2D(64) + BN + ReLU] x2 + MaxPool + Dropout
→ Flatten → Dense(128) + BN + Dropout(0.5)
→ Dense(10, Softmax)

---

## 📁 Project structure

handwriting-recognition-dl/
├── notebooks/
│   ├── 01_mlp_keras.ipynb       # MLP with Keras/TF
│   ├── 02_mlp_pytorch.ipynb     # MLP with PyTorch
│   ├── 03_cnn_keras.ipynb       # CNN with Keras/TF
│   └── 04_cnn_pytorch.ipynb     # CNN with PyTorch
├── models/
│   ├── mlp_keras_mnist.keras
│   ├── mlp_pytorch_mnist.pt
│   ├── cnn_keras_mnist.keras
│   └── cnn_pytorch_mnist.pt
├── assets/
│   ├── mlp_training_curves.png
│   ├── mlp_vs_cnn_comparison.png
│   ├── feature_maps.png
│   └── final_comparison.png
├── requirements.txt
└── README.md

---

## 🚀 Quick start

```bash
git clone https://github.com/adnane-ml/handwriting-recognition-dl.git
cd handwriting-recognition-dl

python -m venv venv
source venv/Scripts/activate  # Windows
pip install -r requirements.txt

# Run notebooks in order
# jupyter notebook notebooks/01_mlp_keras.ipynb
```

---

## 🛠️ Tech stack

| Category | Technology |
|----------|------------|
| Language | Python 3.11 |
| Deep Learning | Keras/TensorFlow 2.x |
| Deep Learning | PyTorch 2.x |
| Data | MNIST (auto-download via Keras/torchvision) |
| Visualization | Matplotlib, Seaborn |

---

## 👤 Author

Software engineer / ML Engineering.
Building end-to-end Deep Learning projects with
Keras/TensorFlow and PyTorch.
Open to AI Backend and MLOps roles

---

## 📄 License

MIT License