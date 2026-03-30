# 🧬 Breast Cancer Classification — ML Assignment 3

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-orange?logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

> Applying and comparing five supervised machine learning classification algorithms on the **Breast Cancer Wisconsin (Diagnostic) Dataset** from `sklearn`.

---

## 📌 Objective

Evaluate and compare the performance of five classification algorithms to predict whether a breast tumor is **Malignant (cancerous)** or **Benign (non-cancerous)** using 30 numeric features extracted from cell nucleus images.

---

## 📂 Project Structure

```
├── ML_Assignment_3_Classification.ipynb   # Main Jupyter Notebook
├── README.md                              # Project documentation
```

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| **Source** | `sklearn.datasets.load_breast_cancer()` |
| **Samples** | 569 |
| **Features** | 30 numeric (mean, SE, worst of 10 cell nucleus measurements) |
| **Target** | Binary — `0: Malignant`, `1: Benign` |
| **Class Split** | 212 Malignant · 357 Benign |
| **Missing Values** | None |

---

## ⚙️ Preprocessing Steps

| Step | Description |
|------|-------------|
| **Missing Value Check** | Confirmed no missing values in the dataset |
| **Train-Test Split** | 80% training / 20% testing with `stratify=y` |
| **Feature Scaling** | `StandardScaler` applied — zero mean, unit variance |

> **Why scale?** SVM and k-NN are distance-based; Logistic Regression converges faster. Scaling ensures no single feature dominates due to its magnitude.

---

## 🤖 Classification Algorithms

### 1. 📈 Logistic Regression
- Models class probability using the **sigmoid function**
- Fast, interpretable, works well when data is linearly separable
- Requires feature scaling

### 2. 🌳 Decision Tree Classifier
- Builds a flowchart-like tree using **Gini impurity** splits
- Highly interpretable — decision path is visible
- No scaling required; `max_depth=5` used to prevent overfitting

### 3. 🌲 Random Forest Classifier
- Ensemble of 100 Decision Trees using **bagging + feature randomness**
- Reduces overfitting, robust to noise and correlated features
- Provides reliable feature importances

### 4. 🔷 Support Vector Machine (SVM)
- Finds the optimal **maximum-margin hyperplane** between classes
- Uses **RBF kernel** to handle non-linear boundaries
- Highly effective in high-dimensional spaces; requires scaling

### 5. 📍 k-Nearest Neighbors (k-NN)
- Lazy learner — classifies based on **majority vote of k=5 neighbors**
- Simple and intuitive; no explicit training phase
- Requires scaling; optimal k explored from 1–20

---

## 📈 Results

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| **SVM** | **~97%** | ~97% | ~98% | ~97% |
| **Random Forest** | **~97%** | ~96% | ~98% | ~97% |
| Logistic Regression | ~96% | ~96% | ~97% | ~96% |
| k-NN | ~95% | ~95% | ~96% | ~95% |
| Decision Tree | ~94% | ~93% | ~96% | ~94% |

> ✅ **Best Model:** SVM / Random Forest
> ⚠️ **Worst Model:** Decision Tree

*Note: Exact values may vary slightly due to random state — run the notebook to see your results.*

---

## 📉 Visualizations Included

- Class distribution (bar + pie charts)
- Confusion matrices for all 5 models
- Feature importance charts (Logistic Regression, Decision Tree, Random Forest)
- k-NN accuracy vs. k plot
- Grouped bar chart — all metrics side by side
- Performance heatmap
- Radar / spider chart comparison

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### Run the Notebook
```bash
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Launch Jupyter
jupyter notebook ML_Assignment_3_Classification.ipynb
```

Or open directly in **Google Colab**:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/your-repo-name/blob/main/ML_Assignment_3_Classification.ipynb)

---

## 🛠️ Libraries Used

| Library | Purpose |
|---------|---------|
| `scikit-learn` | Dataset, classifiers, preprocessing, metrics |
| `numpy` | Numerical computations |
| `pandas` | Data manipulation |
| `matplotlib` | Plotting and visualizations |
| `seaborn` | Statistical heatmaps and styling |

---

## 📝 Key Takeaways

1. **Feature scaling** is critical for SVM and k-NN — improves accuracy significantly
2. **SVM with RBF kernel** and **Random Forest** are the top performers
3. **Recall** is the most important metric in medical diagnosis — minimizing false negatives (missing a malignant tumor) is the priority
4. **Logistic Regression** is an excellent interpretable baseline for medical use cases
5. **Decision Trees** are the most human-readable but prone to overfitting without constraints

---

## 👤 Author

**Your Name**
- GitHub: [@muhsinasafeeth](https://github.com/muhsinasafeeth)

---

## 📄 License

This project is for academic purposes under the [MIT License](LICENSE).
