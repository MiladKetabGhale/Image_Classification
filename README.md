# Image Classification Project

This project outlines a principled philosophy: effective machine learning systems need not rely on deep learning or brute force. Through interpretability, benchmarking, and error analysis—rooted in exploratory data analysis (EDA)—we demonstrate how classical models can remain both viable and robust in data-rich yet resource-constrained environments.

We advocate for a holistic and context-aware approach, where choices around model architecture, training methodology, evaluation metrics, and even the depth of optimization are all informed by business objectives.

## Core Techniques & Tools

| **Aspect**              | **Key Methods & Tools**                                                                                   |
|-------------------------|------------------------------------------------------------------------------------------------------------|
| **Data**                | EMNIST Balanced subset — 280,000 grayscale images across 10 balanced classes                               |
| **EDA**                 | Pixel intensity, non-zero proportion, center of mass, digit-wise mean/variance images                     |
| **Models**              | Logistic Regression, SVM, Decision Tree, Random Forest, Extra Trees, XGBoost, **LightGBM**, AdaBoost       |
| **Model Explainability**| SHAP (Shapley values) for feature attribution and interpretability                                         |
| **Feature Selection**   | Variance thresholding, mutual information, recursive feature elimination (RFE)                            |
| **Evaluation**          | Accuracy, Precision, Recall, F1, ROC AUC, PR AUC, **F1 vs Threshold**, **Reliability Diagrams**           |
| **Uncertainty Estimation** | Confidence distributions, error vs. confidence plots, reliability curves, Brier score                    |
| **Advanced Topics**     | **Ensembling**, **Multiclass Classification**, **Error Analysis**, **Calibration Assessment**             |

## Repository Structure

The project is structured as a continuous narrative, with each chapter building on the results and insights of the preceding ones. It is divided into seven chapters, each presented in a separate Jupyter notebook. A unified notebook is also included which combines the entire project into one for a holistic view.

### Unified Notebook
- **[Unified Notebook](https://github.com/MiladKetabGhale/Image_Classification/blob/main/000_Unified_Notebook_EMNIST.ipynb)**: A consolidated notebook containing all seven chapters of the project in a single file.

### Individual Chapters
Each chapter focuses on specific aspects of the project:

- **[Table Of Contents](https://github.com/MiladKetabGhale/Image_Classification/blob/main/001_Table_Of_Contents.ipynb)**  
  Contains the structured table of contents for the project, providing an overview of all chapters and their respective sections.

- **[Introduction](https://github.com/MiladKetabGhale/Image_Classification/blob/main/01_Chapter_1_Introduction.ipynb)**
  
  We lay the foundation for an interpretable, resource-efficient machine learning workflow. Rather than rushing into model training, we begin with disciplined exploratory data analysis. By examining quantitative signals like class-wise pixel density, spatial geometry, and center of mass, we gain early insights that shape our later choices in model architecture and feature design. This grounding in data allows us to approach the problem both analytically and systematically.
  
- **[Baseline Models](https://github.com/MiladKetabGhale/Image_Classification/blob/main/02_Chapter_2_BaselineModels.ipynb)**  
  - Establishes baseline classifiers, including Logistic Regression, SVM, Decision Tree, Random Forest, XGBoost, and AdaBoost.  
  - Evaluates these models using precision, recall, ROC curves, and Brier scores.  
  - Includes detailed error analysis using confusion matrices and visualizations.

- **[Model Tuning](https://github.com/MiladKetabGhale/Image_Classification/blob/main/03_Chapter_3_ModelTuning.ipynb)**  
  - Explores hyperparameter tuning with HalvingGridSearchCV, focusing on efficient optimization of the baseline models.  
  - Analyzes tuned models’ performance using precision-recall curves, timing evaluations, and error analysis.

- **[Ensembling](https://github.com/MiladKetabGhale/Image_Classification/blob/main/04_Chapter_4_Ensembling.ipynb)**  
  - Constructs ensemble models using soft/hard voting and stack ensembles.  
  - Benchmarks ensemble performance against standalone classifiers.  
  - Includes error frequency and heatmap analyses for misclassifications.

- **[Feature Importance And Feature Selection](https://github.com/MiladKetabGhale/Image_Classification/blob/main/05_Chapter_5_FeatureImportanceSelection.ipynb)**  
  - Investigates feature importance using SHAP, Random Forest importance, and Recursive Feature Elimination (RFE).  
  - Demonstrates feature selection pipelines and error analysis informed by feature importance.  
  - Discusses trustworthiness, robustness, and adversarial training as future themes.

- **[Multiclass Classification](https://github.com/MiladKetabGhale/Image_Classification/blob/main/06_Chapter_6_MulticlassClassification.ipynb)**  
  - Trains multiclass classifiers using models such as XGBoost, AdaBoost, and LightGBM.  
  - Benchmarks direct multiclass classifiers against ensemble approaches like soft voting.  
  - Measures generalizability and uncertainty using predictive entropy and Brier scores.

- **[Conclusion](https://github.com/MiladKetabGhale/Image_Classification/blob/main/07_Chapter_7_Conclusion.ipynb)**  
  - Summarizes the findings and contributions of the project.  
  - Highlights limitations and proposes directions for future work, such as tackling class imbalance, unsupervised learning, adversarial robustness, and distributed learning.


## License
This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).  
You are free to use, modify, and distribute the code, provided proper attribution is given. The software is provided "as is," without warranties or guarantees of any kind.

