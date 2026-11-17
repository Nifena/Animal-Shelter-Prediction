# Animal Shelter Outcome Prediction

Machine learning project analyzing 26,729 animal shelter records to predict the final outcome of an animal's stay at the Austin Animal Center. The project covers exploratory data analysis, feature engineering, preprocessing, and model comparison for a multiclass classification task.

## Project overview

- Dataset: 26,729 records from the [Shelter Animal Outcomes competition on Kaggle](https://www.kaggle.com/c/shelter-animal-outcomes)
- Task: predict one of five outcome categories (`OutcomeType`)
- Approach: exploratory data analysis, feature engineering, preprocessing pipelines, and supervised learning
- Best-performing model: Random Forest with about 69.06% test accuracy, compared with a 40.29% majority-class baseline

## Methods

1. Exploratory data analysis of class balance, missing values, and relationships between animal characteristics and outcomes.
2. Feature engineering based on age, sex/neutering status, date-time attributes, and simple metadata such as whether an animal has a name.
3. Preprocessing with `ColumnTransformer` and `Pipeline` from scikit-learn.
4. Comparison of baseline and several models, including Logistic Regression, Random Forest, and k-NN.
5. Validation using a stratified train/test split and cross-validation.

## Results

| Model | Test accuracy |
| --- | ---: |
| Majority-class baseline | 40.29% |
| Random Forest | 69.06% |

The model performed best among the evaluated classifiers, but it also showed signs of overfitting and struggled with underrepresented classes.

## Technologies

Python, pandas, NumPy, Matplotlib, scikit-learn, Jupyter Notebook.

## Repository structure

```text
animal-shelter-prediction/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── Shelter_Animal_Outcomes.ipynb
├── data/
│   └── train.csv
└── reports/
    └── report.pdf
```

## Getting started

1. Clone the repository and enter its directory.
2. Create and activate a virtual environment.

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

   On Windows:

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\activate
   ```

3. Install the dependencies:

   ```bash
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. Download the dataset from Kaggle and place it in `data/train.csv`.
5. Open the notebook:

   ```bash
   jupyter notebook notebooks/Shelter_Animal_Outcomes.ipynb
   ```

Important note: the notebook expects the dataset file at `data/train.csv` relative to the repository root. If you launch the notebook from another working directory, make sure the notebook points to the correct path.

## Report

The full academic report is available at [`reports/report.pdf`](reports/report.pdf).

## Author

Natalia Jona
