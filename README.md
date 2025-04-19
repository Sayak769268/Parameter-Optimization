# Parameter-Optimization

## 🧠 Overview:
This project explores the effectiveness of Nu-Support Vector Machines (NuSVC) on a synthetic multi-class dataset. Through randomized hyperparameter tuning across 10 different shuffled samples, we aim to identify optimal configurations for achieving high classification accuracy.

Each trial evaluates 100 random combinations of kernel, nu, and gamma, logging the best performing configuration for each sample. The convergence of accuracy over iterations is also visualized for the top sample.

---

## 📚 Dataset Overview

A synthetic dataset was generated using make_classification() from scikit-learn with the following properties:

Samples: 1000

Features: 20 (10 informative, 5 redundant)

Classes: 3

Class Separation: Moderate (class_sep = 1.2)

---

## 🔍 Class Distribution:
Class 2: 335 samples

Class 1: 334 samples

Class 0: 331 samples

The dataset is balanced, ensuring fairness in evaluation across all classes.

---

## 🔧 Methodology:
Shuffling & Sampling: 10 unique datasets (S1 to S10) were created by shuffling with different random seeds.

Train/Test Split: Each sample was split 70:30 for training and testing respectively.

Model: NuSVC from scikit-learn was used.

Hyperparameters Tuned Randomly:

Kernel: linear, poly, rbf, sigmoid

Nu: Random value in [0.01, 0.5]

Gamma: Random value in [0.001, 1] or 'scale' for linear

Each sample ran for 100 iterations, recording the best accuracy and parameters achieved.

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

## 📦 Requirements

- Python 3.x
- scikit-learn
- numpy
- pandas
- matplotlib

Install dependencies using:

```bash
pip install scikit-learn numpy pandas matplotlib

