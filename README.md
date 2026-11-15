# Animal Shelter Outcome Prediction

Machine learning analysis of animal shelter records to predict the outcome of an animal's stay at the Austin Animal Center. The project explores how animal characteristics relate to outcomes and compares multiclass classification models.

## Project overview

- **Dataset:** 26,729 records from the [Shelter Animal Outcomes competition on Kaggle](https://www.kaggle.com/c/shelter-animal-outcomes)
- **Task:** Predict one of five outcome categories (`OutcomeType`)
- **Approach:** Exploratory data analysis, feature engineering, preprocessing pipelines, and supervised learning
- **Best-performing model:** Random Forest, with **69.06% test accuracy**, compared with a **40.29% majority-class baseline**

## Methods

1. **Exploratory data analysis:** Examined class distribution, missing values, and relationships between animal attributes and outcomes.
2. **Feature engineering:** Derived features from animal age, sex/neutering status, and date-time information. Removed identifiers and outcome-related information that could cause data leakage.
3. **Preprocessing:** Applied missing-value imputation, categorical encoding, and numerical scaling using scikit-learn `Pipeline` and `ColumnTransformer`.
4. **Model comparison:** Evaluated Logistic Regression, Random Forest, and k-Nearest Neighbors against a `DummyClassifier` baseline.
5. **Validation:** Used a stratified 80/20 train-test split and stratified five-fold cross-validation during hyperparameter tuning.
6. **Additional analysis:** Explored PCA for dimensionality reduction and K-Means clustering.

## Results

| Model | Test accuracy |
| --- | ---: |
| Majority-class baseline | 40.29% |
| Random Forest | **69.06%** |

Random Forest performed best among the evaluated classifiers. Its balanced accuracy was **44.64%**, indicating that performance varied substantially across outcome classes. Age and neutering status were among the most influential features, alongside the hour of outcome and animal breed and color.

### Limitations

The Random Forest model showed signs of overfitting (**93.47% training accuracy** versus **69.06% test accuracy**) and struggled with rare classes. Because the dataset comes from one shelter and a historical period, results should not be assumed to generalize to other shelters or time periods. This is an exploratory academic project, not a production-ready decision system.

## Technologies

Python, pandas, NumPy, Matplotlib, scikit-learn, Jupyter Notebook.

## Repository structure

```text
animal-shelter-prediction/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── shelter_animal_outcomes.ipynb
├── data/
│   └── train.csv
└── reports/
    └── report.pdf
```

> The `data/train.csv` entry is optional. If the dataset is not included in the repository, download it from Kaggle and place it in `data/`.

## Getting started

1. Clone the repository and enter its directory.
2. Create and activate a Python virtual environment.
3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Download `train.csv` from the [Kaggle competition](https://www.kaggle.com/c/shelter-animal-outcomes) if it is not already in `data/`.
5. Open `notebooks/shelter_animal_outcomes.ipynb` in Jupyter Notebook and run the cells in order.

**Note:** Check the notebook's CSV file path against the repository layout before running it. The notebook has not yet been independently verified to execute end-to-end in a clean environment.

## Report

The full academic report (in Polish), including figures, methodology, evaluation, and discussion, is available at [`reports/report.pdf`](reports/report.pdf).

## Author

Natalia Jona
