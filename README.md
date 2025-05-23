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

## Performance Results

This section gathers all the hard numbers that prove the project’s engineering steps translate into real-world gains. We split the evidence into three focused tracks:

### 8-vs-All Benchmark

A challenging binary scenario (digit ‘8’ vs. the rest) that acts as a bridge between simple binary tasks and full multiclass problems. It lets us highlight how tuning, ensembling, and feature selection push a single model (XGBoost) from a strong baseline to a lean, state-of-the-art classifier.

The table below traces XGBoost’s journey from a strong baseline to a lean, calibrated champion, illustrating how each chapter’s engineering step moves the needle.

### 📈 Performance Trajectory — 8-vs-All Benchmark

> Error Reduction (%) = ((baseline error − tuned error) / baseline error) × 100

| Model                    | Features Used (%) | Accuracy (Δ%)      | Precision (Δ%)      | Recall (Δ%)         | Macro F1 (Δ%)       | ROC AUC (Δ%)        | Error Reduction (%) |
|--------------------------|-------------------|---------------------|----------------------|----------------------|----------------------|----------------------|----------------|
| **XGBoost (baseline)**   | 100%              | 0.987               | 0.971                | 0.894                | 0.931                | 0.997                | —              |
| XGBoost (tuned)          | 100%              | 0.994 (+0.71%)      | 0.986 (+1.54%)       | 0.956 (+6.94%)       | 0.971 (+4.30%)       | 0.999 (+0.20%)       | 53.85%         |
| XGB + RF + Ada (ensemble)| 100%              | 0.995 (+0.81%)      | 0.982 (+1.13%)       | 0.968 (+8.28%)       | 0.975 (+4.73%)       | 0.999 (+0.20%)       | 61.54%         |
| XGBoost (SHAP)           | ~30%              | 0.995 (+0.81%)      | 0.994 (+2.37%)       | 0.960 (+7.38%)       | 0.977 (+4.94%)       | 0.9997 (+0.27%)      | 61.54%         |
| Best AdaBoost            | 100%              | 0.9945 (+0.76%)     | 0.9836 (+1.30%)      | 0.961 (+7.49%)       | 0.9722 (+4.42%)      | 0.9994 (+0.24%)      | 57.69%         |
| SGD Classifier (tuned)   | 100%              | 0.9315 (−5.62%)     | 0.9178 (−5.47%)      | 0.346 (−61.29%)      | 0.5025 (−46.04%)     | 0.9375 (−5.97%)      | −28.08%        |
| Extra Trees (tuned)      | 100%              | 0.9873 (+0.03%)     | 0.9910 (+2.06%)      | 0.881 (−1.45%)       | 0.9328 (+0.19%)      | 0.9983 (+0.13%)      | 2.31%          |
| Random Forest (tuned)    | 100%              | 0.9859 (−0.11%)     | 0.9909 (+2.06%)      | 0.867 (−3.02%)       | 0.9248 (−0.66%)      | 0.9983 (+0.13%)      | −8.46%         |

> **Key takeaways:**  
> • Macro F1 jumped **+4.6 pp** from baseline to SHAP-refined XGBoost while **cutting input dimensionality by two-thirds**.  
> • Precision increased from **0.97 → 0.99** and Recall from **0.89 → 0.96**, showing balanced gains.  
> • Ensembling helped, but the biggest leaps came from **hyper-parameter tuning** and **SHAP-driven feature selection**.  
> • XGBoost remained the top performer throughout, validating each chapter’s engineering effort.

### Multiclass Classification  

We tackle the full 47-class EMNIST task and compare three direct multiclass learners (XGBoost, LightGBM, AdaBoost) against an ensemble built on top of them. The goal is to show how the engineering lessons from the 8-vs-all track generalise to the full-scale problem.

#### Reading the Multiclass Results  

* **Model / Layer** — names follow the pattern `baseMethod[EnsembleFlag]M-L#`

  | Part | Meaning | Examples |
  |------|---------|----------|
  | `baseMethod` | Core algorithm | `xgb`, `ada`, `lgbm` |
  | `[EnsembleFlag]` | *Optional* ensembling tag | `Sv` = soft-voting, `St` = stacking (omitted when none) |
  | `M` | Indicates a multiclass run | Always present in this table |
  | `L#` | Layer index | `L0` = baseline learner, `L1`, `L2`, … = higher-level ensembles |

* **Macro Precision / Recall / F1** — per-digit metrics averaged across all ten digits (0–9), so every class counts equally.  
* **Avg. Accuracy** — mean of per-digit accuracies.  
* Higher layers (e.g. `adaSvM-L1`) reveal how ensembling lifts performance beyond already strong single-model baselines.

#### 📈 Performance Trajectory — Multiclass Benchmark (Digits 0-9)

| Stage              | Model / Layer            | Macro Precision | Macro Recall | Macro F1 | Avg. Accuracy | Notes                                                              |
|--------------------|--------------------------|----------------:|-------------:|---------:|--------------:|--------------------------------------------------------------------|
| **Baseline**       | AdaBoost `adaM-L0`       | 0.967 | 0.964 | 0.961 | 0.961 | Weakest of the three baselines                                      |
|                    | LightGBM `lgbmM-L0`      | 0.982 | 0.981 | 0.981 | 0.981 | Competitive out-of-the-box                                          |
|                    | XGBoost `xgbM-L0`        | 0.982 | 0.982 | **0.984** | 0.983 | Strongest single-model baseline                                     |
| **Ensemble Lift**  | Ada Soft-Voting `adaSvM-L1` | **0.986** | **0.986** | **0.985** | **0.986** | +0.2 pp F1 over XGB; demonstrates the benefit of ensembling |

### Calibration & Reliability

The calibration curves below illustrate the reliability of predicted probabilities for our tuned models. Calibration measures how well the predicted probabilities reflect the actual outcomes, indicating the trustworthiness of the model's confidence estimates.

![Reliability diagram of tuned XGBoost](figures/cal_curve.png)

## License
This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).  
You are free to use, modify, and distribute the code, provided proper attribution is given. The software is provided "as is," without warranties or guarantees of any kind.

