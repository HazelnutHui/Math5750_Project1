
---

## Part 4: Regression Analysis – California Housing

**Dataset**  
- 20,640 samples, 8 numerical features.  
- Features: `MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude`.  
- Train/Test split: 16,512 / 4,128 samples.  

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

- Predicted vs Actual  
- ![Linear Pred vs Actual](figures/part4/linear_pred.png)  
- ![Ridge Pred vs Actual](figures/part4/ridge_pred.png)  
- ![Lasso Pred vs Actual](figures/part4/lasso_pred.png)  

- Residuals Histogram  
- ![Linear Residuals](figures/part4/linear_resid.png)  
- ![Ridge Residuals](figures/part4/ridge_resid.png)  
- ![Lasso Residuals](figures/part4/lasso_resid.png)  

- Feature Importance (Permutation, Lasso)  
- ![Feature Importance – Lasso](figures/part4/lasso_importance.png)  

---

## Part 5: Classification Analysis – Breast Cancer Dataset

**Dataset**  
- 569 samples, 30 numerical features.  
- Train/Test split: 455 / 114 samples.  

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
- ![SVM Confusion Matrix](figures/part5/svm_confusion.png)  
- ![SVM ROC Curve](figures/part5/svm_roc.png)  
- ![SVM PR Curve](figures/part5/svm_pr.png)  

- Random Forest  
- ![RF Confusion Matrix](figures/part5/rf_confusion.png)  
- ![RF ROC Curve](figures/part5/rf_roc.png)  
- ![RF PR Curve](figures/part5/rf_pr.png)  

---

