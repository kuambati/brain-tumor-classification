🧠 Brain Tumor Classification using Naive Bayes

This project builds a machine learning model to classify brain tumor types using gene expression data, applying Gaussian Naive Bayes and evaluating performance with cross-validation.

=> Dataset

Source: GSE50161 gene expression dataset from NCBI GEO
Content: Gene expression profiles for various brain tumor types
Input: Expression levels of various genes (e.g., 1007_s_at, 1294_at, etc.)
Target: Tumor type – normal, ependymoma, glioblastoma


=> Technologies & Libraries

- Python 3.10+
- Jupyter Notebook
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn


=> Models used

->Naive Bayes (Baseline)
- Model: GaussianNB  
- Accuracy: ~76%  
- It is a simple and lightweight algorithm, a good starting point for high-dimensional data. But, it struggles when the number of features is large compared to the number of samples.

->Random Forest (Improved)
- Model: RandomForestClassifier  
- Accuracy: ~92%  
- Handles complexity much better and takes advantage of more features.


=> Workflow Summary

1. Preprocessing  
- Label encoded the tumor types.  
- Imputed missing values using mean strategy.  
- Scaled the features to standardize gene expression levels.  

2. Feature Selection  
Used SelectKBest with ANOVA F-test (`f_classif`) to choose the top 100 genes that matter most for classification.


=> Evaluation

- Accuracy score
- Classification report (precision, recall, F1)
- Confusion matrix heatmap (via Seaborn)
- 5-fold cross-validation to check generalization
- Accuracy curve per fold


=> Results

- Naive Bayes gave a decent baseline with ~76% accuracy, proving useful for quick experimentation but limited by assumptions of feature independence.
- Random Forest significantly boosted performance to ~92% accuracy by capturing complex patterns in the gene expression data.
- Feature selection (SelectKBest) helped reduce noise and focus the model on the most relevant genes.
- The final model generalizes well, as shown by strong cross-validation scores and consistent fold-wise accuracy.
- Visual tools like confusion matrices and accuracy curves supported better understanding of classification behavior.


