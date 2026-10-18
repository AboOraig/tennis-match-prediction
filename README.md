# Tennis Match Outcome Prediction 

A machine learning project that predicts ATP tennis match outcomes using historical match data. The project compares Logistic Regression and Random Forest classifiers using matches played between 2000 and 2018.

The objective is to explore how player rankings, ATP points, historical win rates, court surface, and match format relate to match outcomes.

## Project Overview

This project covers the main stages of a machine learning workflow:

Data collection and preprocessing
Exploratory data analysis
Feature engineering
Binary classification
Model evaluation and interpretation

The models are trained on historical matches from 2000–2016 and evaluated on matches played in 2017.

## Dataset

The data comes from Tennis-Data.co.uk, which provides historical tennis match statistics.

Tour: ATP men's singles
Historical period: 2000–2018
Training period: 2000–2016
Test period: 2017

The notebook downloads the yearly datasets and combines them into a single DataFrame.

## Features

The model uses the following match characteristics:

- Player rankings: ATP ranking positions and ranking difference
- ATP points: Player points and points difference
- Historical performance: Win rates calculated from previous matches
- Playing conditions: Court surface
- Match format: Best-of-three or best-of-five sets

Matches are represented consistently by ordering the two players alphabetically. The target variable indicates whether Player 1 wins.

## Models

Two classification algorithms are compared:

- Logistic Regression: A baseline classification model with standardized features.
- Random Forest: An ensemble model capable of learning nonlinear relationships between features.

## Results

The initial experiments produced the following approximate results:

| Model |	Test accuracy (2017) | Training accuracy |
|---|---|---|
| Logistic Regression |~65% |	To be verified |
| Random Forest |	~64%	| 100% |

The Logistic Regression model slightly outperformed the Random Forest on the 2017 test set.

The Random Forest achieved perfect training accuracy but lower test accuracy, suggesting overfitting.

The results also suggest that player rankings and historical performance are useful predictors of match outcomes. These findings should be interpreted alongside the limitations of the feature engineering and evaluation methodology.

Note: These figures are preliminary and should be replaced with the exact results from a clean, reproducible run of the notebook.

## Evaluation

Model performance is assessed using:

- Accuracy
- Precision, recall, and F1-score
- Confusion matrices
- Logistic Regression coefficients
- Random Forest feature importances

A majority-class baseline is also used for comparison.

## Project Structure
```
tennis-match-prediction/
├── notebooks/
│   └── tennis_match_prediction.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Getting Started
1. Clone the repository
git clone https://github.com/YOUR_USERNAME/tennis-match-prediction.git
cd tennis-match-prediction

2. Create a virtual environment
python -m venv .venv

3. Install dependencies
pip install -r requirements.txt

4. Run the notebook
jupyter notebook


Open notebooks/tennis_match_prediction.ipynb and run the cells in order.

The notebook downloads the historical datasets, so an internet connection is required for the initial data collection.

## Limitations
- The experiment evaluates one test season, 2017.
- The historical win-rate features use a relatively simple measure of player performance.
- The models have not yet undergone extensive hyperparameter tuning or cross-validation.
- Bookmaker odds, Elo ratings, surface-specific performance, and head-to-head statistics are not included.
- Predictions depend on the quality and availability of the historical data.

## Future Improvements
- Introduce Elo ratings and surface-specific player statistics.
- Add recent form and head-to-head features.
- Improve the time-aware feature engineering and validation strategy.
- Tune hyperparameters using earlier seasons while keeping the test season untouched.
- Compare additional models and evaluate probability calibration.
Dataset usage and redistribution are subject to the original data provider's terms. Add a project license if you intend to specify how others may reuse your code.
