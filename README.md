
# 📌 Image Deblurring using Convex Optimization Techniques

## 🚀 Overview

This project focuses on solving the **image deblurring problem**, a classical ill-posed inverse problem in computer vision. The goal is to recover a sharp image from a blurred and noisy observation using **optimization-based approaches**.

We perform a **comparative analysis of convex and non-convex regularization methods** combined with multiple optimization algorithms to study their effect on reconstruction quality and convergence.

---

## 🧠 Problem Formulation

The degraded image is modeled as:

[
f = Ku + n
]

Where:

* (u): original sharp image (unknown)
* (K): blur operator (convolution kernel)
* (n): noise
* (f): observed blurred image

We solve the optimization problem:

[
\min_u \frac{1}{2}|Ku - f|^2 + \lambda R(u)
]

Where:

* First term → data fidelity
* Second term → regularization

---

## ⚙️ Methods Implemented

### 🔹 Regularization Models

* L2 Regularization (smooth but blurry)
* Total Variation (TV) (edge-preserving)
* Non-convex sparse regularization (ℓp, p < 1)

---

### 🔹 Optimization Algorithms

#### Gradient-based

* Gradient Descent (GD)
* FISTA (Fast Iterative Shrinkage Thresholding Algorithm)

#### Operator Splitting

* ADMM (Alternating Direction Method of Multipliers)
* Split Bregman

#### Primal-Dual

* Chambolle–Pock (Primal-Dual Method)

#### Non-Convex Optimization

* PIRL1-AM
* APIRL1-AM (accelerated)

---

## 🧩 Key Concepts

* **Convex Optimization** → ensures stable convergence and global optimum
* **Total Variation (TV)** → preserves edges while removing noise
* **Alternating Minimization** → solves complex problems in steps
* **Acceleration (FISTA)** → improves convergence speed

---

## 📊 Experimental Setup

### Datasets

* Cameraman
* Camera
* Coins
* Moon
* Synthetic images (Checkerboard, Gradient, Random shapes)

### Degradation

* Gaussian blur
* Additive Gaussian noise

### Evaluation Metrics

* PSNR (Peak Signal-to-Noise Ratio)
* SSIM (Structural Similarity Index)

---

## 📈 Results

| Method             | PSNR      | SSIM       |
| ------------------ | --------- | ---------- |
| L2 + GD            | 29.88     | 0.867      |
| L2 + FISTA         | 30.19     | 0.856      |
| TV + ADMM          | 33.41     | 0.889      |
| TV + FISTA         | **36.50** | **0.9099** |
| TV + Primal-Dual   | 30.61     | 0.872      |
| TV + Split Bregman | 33.41     | 0.889      |

---

## 🔥 Key Findings

* TV regularization significantly outperforms L2
* Edge preservation is critical for image quality
* Solver choice strongly affects performance
* **TV + FISTA gives best results** (quality + speed)
* Acceleration improves convergence
* Split methods provide stable performance

---


