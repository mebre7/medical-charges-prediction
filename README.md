# Medical Charges Prediction

A machine learning project that predicts individual medical insurance charges using Linear Regression, based on patient demographics and lifestyle factors.

## Dataset

**1,338 records** with 7 features.

The dataset is not included in this repository. Download it from:

[Machine-Learning-with-R-datasets](https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv)

After downloading, place the CSV file at:

```
data/medical_charges.csv
```

| Feature | Type | Description |
|---|---|---|
| `age` | int | Age of the beneficiary |
| `sex` | categorical | male / female |
| `bmi` | float | Body Mass Index |
| `children` | int | Number of dependents |
| `smoker` | categorical | yes / no |
| `region` | categorical | northeast / northwest / southeast / southwest |
| `charges` | float | **Target** — annual medical insurance cost ($) |

No missing values in the dataset.

## Project Structure

```
Medical_Charges/
├── data/              # place medical_charges.csv here (not tracked by git)
├── models/
├── notebook/
│   └── linear_regression.ipynb
└── README.md
```

## Setup

```bash
python -m venv .mc_ve
source .mc_ve/bin/activate
pip install pandas numpy matplotlib plotly scikit-learn jupyter seaborn
```

## Running the Notebook

```bash
jupyter notebook notebook/linear_regression.ipynb
```

Run all cells top-to-bottom. The notebook covers:

1. **EDA** — distribution analysis, correlation checks
2. **Feature Engineering** — encoding categorical variables (sex → 0/1, smoker, region)
3. **Modeling** — Linear Regression (scikit-learn `LinearRegression` and `SGDRegressor`)
4. **Evaluation** — regression metrics (R², MAE, RMSE)

## Google Colab

1. Open the notebook directly: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mebre7/medical-charges-prediction/blob/colab_branch/notebook/medical_charges_model.ipynb)

2. Download the dataset from [Machine-Learning-with-R-datasets](https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv) and upload it to Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
medical_df = pd.read_csv('/content/drive/MyDrive/path_to_your_file/<file_name>.csv')
```

All required libraries (`pandas`, `numpy`, `matplotlib`, `plotly`, `scikit-learn`, `seaborn`) are pre-installed in Colab.

## Key Insights

- Smoking status is the strongest predictor of high medical charges
- Age and BMI show positive correlation with charges
- Non-smokers cluster at significantly lower charge amounts
