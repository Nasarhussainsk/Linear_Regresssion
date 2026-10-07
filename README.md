# Car Mileage Prediction

A beginner-friendly machine learning project that uses multiple linear regression to predict a car's mileage (MPG) from its technical specifications. The analysis is documented in a Jupyter Notebook.

## Project overview Created by [Nasar Hussain](https://github.com/Nasarhussainsk).

The notebook explores the `Cars.csv` dataset, checks basic data quality and linear regression assumptions, trains a scikit-learn `LinearRegression` model, and evaluates its predictions on a held-out test set. It also uses `statsmodels` to inspect ordinary least squares regression results.

**Target:** `MPG`  
**Input features:** `HP`, `VOL`, `SP`, and `WT`  
**Dataset size:** 81 rows and 5 columns (as loaded in the notebook)

| Column | Description |
| --- | --- |
| `MPG` | Fuel mileage; prediction target |
| `HP` | Horsepower |
| `VOL` | Engine volume |
| `SP` | Top speed |
| `WT` | Vehicle weight |

The notebook does not state the measurement units for these columns; refer to the dataset's original source for unit details.

## Repository structure

```text
.
├── Cars_Mileage_Prediction.ipynb
├── Cars.csv
└── README.md
```

Keep `Cars.csv` in the same directory as the notebook. The notebook loads it with `pd.read_csv("Cars.csv")`.

## Getting started

### Requirements

- Python 3.10 or later
- Jupyter Notebook or JupyterLab
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- statsmodels

### Install dependencies

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
```

### Run the notebook

1. Clone or download this repository.
2. Place `Cars.csv` beside the notebook.
3. Install the dependencies above.
4. Launch Jupyter and open `Cars_Mileage_Prediction.ipynb`.
5. Run the cells from top to bottom.

```bash
jupyter notebook
```

## Modeling workflow

1. Load and inspect the dataset, including dimensions, data types, missing values, and descriptive statistics.
2. Explore relationships between each feature and `MPG`, and review regression assumptions.
3. Split the data into training and test sets using an 80/20 split (`random_state=22`).
4. Fit a multiple linear regression model using `HP`, `VOL`, `SP`, and `WT`.
5. Evaluate training and test predictions with MAE, MSE, RMSE, and R².
6. Fit OLS models with `statsmodels` and compare R² and adjusted R².

## Results

For the notebook's test split, the recorded model metrics are:

| Metric | Test result |
| --- | ---: |
| Mean Absolute Error (MAE) | 3.3371 |
| Mean Squared Error (MSE) | 18.4625 |
| Root Mean Squared Error (RMSE) | 4.2968 |
| R² | 0.7308 |

The OLS model using all four features reports an R² of **0.7705** and adjusted R² of **0.7585** on the full dataset. These values are from the notebook's saved outputs and may differ if the data or code changes.

## Notes

- The notebook contains exploratory assumption checks and records that some checks, including linearity and homoscedasticity, failed. Interpret the model as a learning exercise rather than a validated production predictor.
- The notebook saves a model artifact named `linear_intelligence_file.pkl` in its working directory. Re-run the relevant notebook cell to generate it.
- Only load pickle files from sources you trust; pickle files can execute code when loaded.

## License

No license is specified. Add a `LICENSE` file before sharing the repository if you want to grant others permission to use, modify, or distribute the project.

