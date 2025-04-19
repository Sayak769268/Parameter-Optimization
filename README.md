# Parameter-Optimization
# 🔍 SVM Hyperparameter Optimization using NuSVC

This project focuses on optimizing hyperparameters for the *Nu-Support Vector Classification (NuSVC)* algorithm using the scikit-learn library. The goal is to evaluate the effect of various SVM kernel types and tuning parameters (Nu, Gamma) on classification performance using a synthetic multi-class dataset.

---

## 🧠 Problem Statement

The Support Vector Machine (SVM) is a powerful supervised learning algorithm. This experiment uses *NuSVC*, a variant that allows controlling the number of support vectors and margin errors via the nu parameter. The challenge lies in finding the right combination of kernel, nu, and gamma values that yield the best accuracy.

---

## 🛠 Dataset Overview

A synthetic dataset was generated using make_classification with the following characteristics:

- *Samples:* 1000  
- *Features:* 20 (10 informative, 5 redundant)  
- *Classes:* 3  
- *Class separation:* Moderate (1.2)  
- *Split:* 70% training / 30% testing  
- *Shuffling:* Random seed varied for 10 samples

---

## ⚙ Experiment Setup

- *Classifier:* NuSVC (from sklearn.svm)
- *Kernel types tested:* linear, poly, rbf, sigmoid
- *Hyperparameters:*
  - nu: Randomly chosen from [0.01, 0.5]
  - gamma: Randomly chosen from [0.001, 1] (except for linear kernel where it's set to 'scale')
- *Iterations:* 100 per sample
- *Evaluation metric:* Accuracy on test set

---

## 📊 Results Summary

| Sample | Accuracy (%) | Best SVM Parameters                          |
|--------|--------------|-----------------------------------------------|
| S1     | 85.67        | Kernel: rbf, Nu: 0.06, Gamma: 0.032          |
| S2     | 83.33        | Kernel: poly, Nu: 0.24, Gamma: 0.176         |
| S3     | 87.33        | Kernel: rbf, Nu: 0.24, Gamma: 0.058          |
| S4     | 89.33        | Kernel: rbf, Nu: 0.28, Gamma: 0.017          |
| S5     | 89.67        | Kernel: rbf, Nu: 0.1, Gamma: 0.058           |
| S6     | 90.00        | Kernel: rbf, Nu: 0.39, Gamma: 0.046          |
| S7     | 84.33        | Kernel: rbf, Nu: 0.08, Gamma: 0.057          |
| S8     | 86.33        | Kernel: poly, Nu: 0.33, Gamma: 0.008         |
| S9     | 87.00        | Kernel: poly, Nu: 0.41, Gamma: 0.868         |
| S10    | 89.33        | Kernel: rbf, Nu: 0.46, Gamma: 0.066          |

---

## 🥇 Best Performing Sample

- *Sample:* S6  
- *Accuracy:* 90.00%  
- *Best Parameters:*  
  - Kernel: rbf  
  - Nu: 0.39  
  - Gamma: 0.046

---

## 📈 Convergence Plot

A convergence plot showing accuracy progression over 100 iterations was created for the best sample (S6). This helps visualize how the algorithm improved during the search process.

- File saved as: convergence_plot.png

---

## 📦 Requirements

- Python 3.x
- scikit-learn
- numpy
- pandas
- matplotlib

Install dependencies using:

```bash
pip install scikit-learn numpy pandas matplotlib
