# 🧠 Texture Classification of Grayscale Surface Images using PCA and k-NN

This project explores the problem of classifying textured grayscale surface images into three categories — **grass**, **sand**, and **stairs** — using classical machine learning techniques.

---

## 🎯 Objective

The main goal was to apply **dimensionality reduction** and **classification algorithms** to high-dimensional grayscale image data and reflect on:
- How well do traditional methods perform on small, structured datasets
- The interpretability of decisions made by models like k-NN
- The trade-offs between complexity and accuracy in classical ML

---

## 🗂 Dataset Description

Each `.txt` file contains 64×64 grayscale images (4096 features per sample). Datasets:
- `grass.txt` 🌿
- `sand.txt` 🏖️
- `stairs.txt` 🪜

Each pixel value ranges from 0 to 255. The dataset includes multiple samples per class.

---

## 🔧 Project Description

### 1. **Preprocessing & Setup**
- Loaded and parsed raw pixel data from text files
- Normalized input features to range [0, 1]
- Structured the dataset with appropriate labels

### 2. **Dimensionality Reduction with PCA**
- Reduced feature space from 4096 to 50 using Principal Component Analysis (PCA)
- Preserved ~96% of variance
- Reflected on dimensionality: high-dimensional raw data led to poor interpretability and overfitting risk

### 3. **Classifier Design & Evaluation**
- Chose **k-Nearest Neighbors (k-NN)** as a transparent baseline
- Performed grid search for `k` values with cross-validation
- Visualized classification results and decision regions using the top 2 PCA components

### 4. **Results & Observations**
| Classifier | Optimal k | Accuracy | Notes |
|------------|-----------|----------|-------|
| k-NN       | 7         | ~93%     | Strong class separation via PCA made even simple classifiers effective |

- Visualizations showed well-separated clusters in PCA space, validating feature relevance
- Decision boundaries aligned with class intuition
- Sand had a slight overlap with stairs in some projections, suggesting borderline ambiguity

---

## ✨ Key Reflections

- **Simple models can perform well** when paired with smart feature transformation like PCA
- **Dimensionality reduction** not only improved computational efficiency, but also exposed **underlying data structure**, which enhanced interpretability
- **k-NN** served as a good interpretability benchmark — results were easy to explain, especially with visual boundaries
- **Overfitting risk was controlled** through cross-validation and avoiding high-complexity classifiers unnecessarily
- **This small-scale project mirrors real-world constraints** (e.g., limited data, noise, need for clarity), which made classical methods more relevant than expected

> “Model interpretability and input clarity often outperform brute-force complexity — especially in low-resource setups.”

---

## 🧰 Tools & Libraries Used

- Python 3.x
- `NumPy`, `pandas`
- `scikit-learn` (PCA, k-NN, evaluation)
- `Matplotlib` & `seaborn` (visualizations)
- Jupyter Notebook

---

## ✅ Outcome

- Achieved solid classification accuracy (~93%) with PCA + k-NN
- Developed a deeper appreciation for **evaluation via visualization** and **dimension-aware design**
- Learned the value of small, interpretable experiments before scaling complexity

---

