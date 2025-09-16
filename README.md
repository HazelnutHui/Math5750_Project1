# Math 5750/6880 – Project 1

This repository contains my solutions and analysis for **Project 1** of *Mathematics of Data Science (Math 5750/6880)*.  
The project consists of three main components:  

1. **Project Euler Problem** (Python / Google Colab)  
2. **Regression Analysis** (California Housing dataset)  
3. **Classification Analysis** (Breast Cancer Wisconsin dataset)  

All code is implemented in Jupyter Notebook (`Project1.ipynb`) and can be viewed in this repository.  
The final report was prepared in LaTeX and submitted as PDF on Gradescope.  

---

## Part 3: Project Euler Problem

**Problem 2 – Even Fibonacci numbers**  
- *Task*: Find the sum of even-valued Fibonacci numbers ≤ 4,000,000.  
- *Result*:  
Sum of even Fibonacci numbers ≤ 4,000,000 = 4,613,732


---

## Part 4: Regression Analysis – California Housing

**Dataset**  
- 20,640 samples, 8 numerical features.  
- Features: `MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude`.  
- Train/Test split:  
- Train: 16,512 samples  
- Test: 4,128 samples  

**Model Performance**

| Model             | R²     | MAE    | RMSE   |
|-------------------|--------|--------|--------|
| Linear Regression | 0.5758 | 0.5332 | 0.7456 |
| Ridge (α=0.7)     | 0.5758 | 0.5332 | 0.7456 |
| Lasso (α=0.001)   | 0.5769 | 0.5331 | 0.7446 |

**Coefficient Analysis**

- **Linear**: AveBedrms (+0.7831), MedInc (+0.4487), Longitude (−0.4337), Latitude (−0.4198)  
- **Ridge**: Latitude (−0.8964), Longitude (−0.8693), MedInc (+0.8543)  
- **Lasso**: Latitude (−0.8858), Longitude (−0.8581), MedInc (+0.8491)  

**Best Model**: Lasso (α=0.001)  

**Figures**
- Predicted vs Actual (Linear, Ridge, Lasso)  
- ![Linear Pred vs Actual](figures/linear_pred.png)  
- ![Ridge Pred vs Actual](figures/ridge_pred.png)  
- ![Lasso Pred vs Actual](figures/lasso_pred.png)  

- Residuals Histogram (Linear, Ridge, Lasso)  
- ![Linear Residuals](figures/linear_resid.png)  
- ![Ridge Residuals](figures/ridge_resid.png)  
- ![Lasso Residuals](figures/lasso_resid.png)  

- Permutation Importance (Lasso)  
- ![Feature Importance – Lasso](figures/lasso_importance.png)  

---

## Part 5: Classification Analysis – Breast Cancer Dataset

**Dataset**  
- 569 samples, 30 features.  
- Train/Test split:  
- Train: 455 samples  
- Test: 114 samples  

**Model Performance**

| Model          | Accuracy | ROC-AUC | Avg Precision |
|----------------|----------|---------|---------------|
| SVM (Linear)   | 0.9737   | 0.9964  | 0.9977        |
| Random Forest  | 0.9474   | 0.9937  | 0.9964        |

**Top Features**

- **SVM (|coef| top 10)**: worst texture, worst smoothness, area error, mean compactness, worst area, radius error, worst concavity, worst perimeter, perimeter error, worst radius  
- **Random Forest (top 10 importances)**: worst perimeter, worst area, worst concave points, mean concave points, worst radius, mean radius, mean perimeter, mean concavity, mean area, worst concavity  

**Figures**
- SVM  
- ![SVM Confusion Matrix](figures/svm_confusion.png)  
- ![SVM ROC Curve](figures/svm_roc.png)  
- ![SVM PR Curve](figures/svm_pr.png)  

- Random Forest  
- ![RF Confusion Matrix](figures/rf_confusion.png)  
- ![RF ROC Curve](figures/rf_roc.png)  
- ![RF PR Curve](figures/rf_pr.png)  

---

## How to Run

Clone the repository and open the notebook:  
```bash
