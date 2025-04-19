# 🧠 SVM Optimization on Multi-Class UCI Dataset

## 📌 Objective

This project focuses on optimizing Support Vector Machine (SVM) classifiers on a multi-class dataset using different randomized train-test splits and hyperparameter combinations. The aim is to:
- Train and evaluate SVM models across 10 random samples.
- Optimize the SVM hyperparameters using 100 random iterations.
- Record the best accuracy and parameters for each sample.
- Plot the convergence graph for the best performing model.

---

## 📚 Dataset Used

- **Source**: UCI Machine Learning Repository
- **Dataset**: Letter Recognition Dataset
- **Samples**: 20,000 records × 16 features
- **Classes**: 26 (A to Z)

---

## ⚙️ Experiment Setup

- **Splits**: 10 randomized 70:30 train-test splits
- **Model**: `sklearn.svm.NuSVC` (Non-linear SVM)
- **Optimization**:
  - Iterations: 100 per sample
  - Parameters optimized:
    - `kernel`: ['rbf', 'poly', 'sigmoid']
    - `nu`: (0.01 to 1)
    - `epsilon`: (0.01 to 1)

---

## 📈 Results

### 🔢 Best Accuracies & Parameters

| Sample | Best Accuracy | Best Parameters         |
|--------|----------------|--------------------------|
| S1     | 96.97%         | rbf, 0.01, 0.56          |
| S2     | 97.17%         | rbf, 0.01, 0.34          |
| S3     | 96.82%         | rbf, 0.01, 0.23          |
| S4     | 96.85%         | rbf, 0.01, 0.45          |
| S5     | 96.78%         | rbf, 0.01, 0.23          |
| S6     | 96.42%         | rbf, 0.01, 0.45          |
| S7     | 95.00%         | poly, 0.01, 0.56         |
| S8     | 97.12%         | rbf, 0.01, 0.45          |
| S9     | 96.57%         | rbf, 0.01, 0.45          |
| S10    | 97.05%         | rbf, 0.01, 0.78          |

---

### 📊 Convergence Graph

The graph below shows the fitness (accuracy) across 100 iterations for the best-performing sample (S2):

![Convergence Graph](convergence_graph.png)

## 🧾 Conclusion

The SVM optimization experiment conducted on the UCI Letter Recognition dataset demonstrates that careful tuning of SVM hyperparameters significantly impacts classification accuracy. Across 10 randomized 70-30 train-test splits and 100 iterations each:

- The highest accuracy achieved was **97.17%** using the **RBF kernel**, with `nu=0.01` and `epsilon=0.34`.
- **RBF kernel** consistently outperformed other kernels (like `poly` and `sigmoid`) in most samples.
- The parameter `nu=0.01` appeared frequently among the best configurations, indicating that a more flexible margin led to better performance on this multi-class task.
- The **accuracy fluctuated greatly during optimization**, as shown in the convergence graph, emphasizing the importance of parameter search in achieving optimal performance.
- Despite high dimensionality and class diversity, the optimized SVM maintained stable and strong performance across samples, with all accuracies above **95%**.

This experiment validates the effectiveness of support vector machines for multi-class classification and highlights the need for systematic hyperparameter optimization to unlock their full potential.



