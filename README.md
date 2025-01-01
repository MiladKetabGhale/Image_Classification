# EMNIST Classification Project

Welcome to the repository for the **EMNIST Classification Project**, part of a larger portfolio showcasing skills in **machine learning engineering**, **data science**, and **data engineering**. This repository focuses on tackling classification challenges on the EMNIST dataset and represents a comprehensive case study that integrates theory, technical practice, and performance optimization.

For an overview of all projects in the portfolio, visit the [Engineering, Analysis, Data Science, and Machine Learning Portfolio](https://github.com/MiladKetabGhale/EngineeringAnalysisData_ML).

The project is divided into **seven chapters**, each presented as a standalone Jupyter notebook. Additionally, a unified notebook combines the entire project for convenience. This structure facilitates accessibility for users with varying needs and preferences.

## Repository Structure

### Unified Notebook
- **000_Unified_Notebook_EMNIST.ipynb**: A consolidated notebook containing all seven chapters of the project in a single file.

### Individual Chapters
Each chapter focuses on specific aspects of the project:

- **001_Table_Of_Contents.ipynb**  
  Contains the structured table of contents for the project, providing an overview of all chapters and their respective sections.

- **01_Introduction.ipynb**  
  - Introduces the EMNIST dataset, its structure, and its variants.  
  - Provides an exploratory data analysis (EDA), uncovering statistical patterns, pixel-level analysis, and visual insights.

- **02_Chapter_2_BaselineModels.ipynb**  
  - Establishes baseline classifiers, including Logistic Regression, SVM, Decision Tree, Random Forest, XGBoost, and AdaBoost.  
  - Evaluates these models using precision, recall, ROC curves, and Brier scores.  
  - Includes detailed error analysis using confusion matrices and visualizations.

- **03_Chapter_3_ModelTuning.ipynb**  
  - Explores hyperparameter tuning with HalvingGridSearchCV, focusing on efficient optimization of the baseline models.  
  - Analyzes tuned models’ performance using precision-recall curves, timing evaluations, and error analysis.

- **04_Chapter_4_Ensembling.ipynb**  
  - Constructs ensemble models using soft/hard voting and stack ensembles.  
  - Benchmarks ensemble performance against standalone classifiers.  
  - Includes error frequency and heatmap analyses for misclassifications.

- **05_Chapter_5_FeatureImportanceSelection.ipynb**  
  - Investigates feature importance using SHAP, Random Forest importance, and Recursive Feature Elimination (RFE).  
  - Demonstrates feature selection pipelines and error analysis informed by feature importance.  
  - Discusses trustworthiness, robustness, and adversarial training as future themes.

- **06_Chapter_6_MulticlassClassification.ipynb**  
  - Trains multiclass classifiers using models such as XGBoost, AdaBoost, and LightGBM.  
  - Benchmarks direct multiclass classifiers against ensemble approaches like soft voting.  
  - Measures generalizability and uncertainty using predictive entropy and Brier scores.

- **07_Chapter_7_Conclusion.ipynb**  
  - Summarizes the findings and contributions of the project.  
  - Highlights limitations and proposes directions for future work, such as tackling class imbalance, unsupervised learning, adversarial robustness, and distributed learning.

## Key Features

- **Statistical Analysis and Visualization**: Uncovering patterns and feature relationships through exploratory data analysis.  
- **Classifier Training and Evaluation**: Establishing performance benchmarks using multiple classifiers and advanced tuning techniques.  
- **Error and Reliability Analysis**: Incorporating tools such as SHAP, calibration curves, and Brier scores to ensure robust error evaluation.  
- **Feature Importance and Selection**: Leveraging feature importance for performance optimization and interpretability.  
- **Generalizability and Uncertainty**: Quantifying model uncertainty with predictive entropy and analyzing performance on unseen data.

## License
This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).  
You are free to use, modify, and distribute the code, provided proper attribution is given. The software is provided "as is," without warranties or guarantees of any kind.

