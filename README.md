# Amazon Sales Data Analysis & Dimensionality Reduction using MATLAB PCA 📊

> [!NOTE]
> **Repository Name Clarification:** This project focuses on **Amazon Sales/E-Commerce Transaction Data Analysis** in MATLAB. It utilizes Principal Component Analysis (PCA) for dimensionality reduction and is not related to Amazon Web Services (AWS) cloud services. We recommend renaming this repository to `Amazon-Sales-Data-Analysis-PCA-MATLAB` for professional clarity.

---

## 🌟 Overview of the Project

This project demonstrates how to import, preprocess, and analyze e-commerce transaction data using **MATLAB**, focusing on **Principal Component Analysis (PCA)** to perform dimensionality reduction and find the primary drivers of sales performance.

The dataset includes transaction records containing numeric variables (sales, quantity, discount, and profit) and categorical identifiers (order ID, country, etc.). The script automates data cleaning, normalization, and eigenvector/eigenvalue decomposition.

---

## 🧠 Mathematics & Methodology

The pipeline follows these core data science steps:

### 1. Data Import & Preprocessing
Data is imported from an Excel spreadsheet (`Book2.xlsx`).
- **Normalization:** Since sales (high range) and discount (decimal range) have different scales, numeric variables are normalized to a range of `[0, 1]` using min-max scaling to prevent feature scale bias:
  $$x_{\text{norm}} = \frac{x - x_{\text{min}}}{x_{\text{max}} - x_{\text{min}}}$$
- **Categorization:** Columns representing Order ID and Country are converted to MATLAB's `categorical` data type to optimize memory usage.

### 2. Covariance Matrix Computation
The covariance matrix $C$ is computed to measure how the numeric variables vary together:
$$C = \frac{1}{N-1} \sum_{i=1}^{N} (x_i - \bar{x})(x_i - \bar{x})^T$$

### 3. Principal Component Analysis (PCA)
We perform eigendecomposition on the covariance matrix to find the eigenvalues $\lambda$ and eigenvectors $V$:
$$C V = V \Lambda$$
- **Eigenvectors (Principal Components):** Represent the directions of maximum variance in the data.
- **Eigenvalues:** Represent the magnitude of variance explained by each principal component.
- **Dimensionality Reduction:** Sorting the eigenvalues in descending order allows us to project the dataset onto the top principal components, capturing $\ge 90\%$ of the information in fewer dimensions.

---

## 🚀 How to Run in MATLAB

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ThanujMaligi/Amazon-Web-Services-AWS-Using-PCA.git
   cd Amazon-Web-Services-AWS-Using-PCA
   ```

2. **Place the Excel File:**
   Ensure your sales transaction Excel sheet is saved as `Book2.xlsx` in the same root directory.

3. **Run the Script:**
   Open MATLAB and run:
   ```matlab
   run('final_aws.mlx')
   ```

4. **Outputs:**
   - Preprocessed data tables.
   - Screen plot showing explained variance per Principal Component.
   - 2D/3D Scatter plots of the projected data points.
