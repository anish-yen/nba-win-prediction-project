# nba-win-prediction-project
NBA Team Win Percentage Prediction (2000–2023)
Overview

This project builds an end-to-end data engineering and machine learning pipeline to model and predict NBA team win percentage using 24 seasons of historical team statistics (2000–2023).

The system ingests raw CSV data, transforms it into a normalized relational database (SQLite), performs feature engineering, and trains predictive models to estimate team win percentage based on shooting efficiency and advanced metrics.

Architecture

Pipeline Flow:

CSV → Pandas ETL → SQLite Relational Schema → Feature Engineering → Model Training → Evaluation → Visualization

Database Schema

Four normalized tables:

teams

seasons

team_season_stats

predictions

Primary/foreign keys enforce relational integrity.

716 total team-season records across 24 seasons.

Feature Engineering

Engineered features include:

Field Goal Percentage

Three-Point Percentage

Rebounds

Assists

Turnovers

Points

Plus/Minus

Target variable:

Win Percentage (win_pct)

Modeling Approach

Time-aware data split:

Train: ≤ 2017

Validation: 2018–2019

Test: ≥ 2020

Models implemented:

Linear Regression

Random Forest Regressor (400 trees)

Results
Model	R²	MAE
Linear Regression	~0.90	~0.034
Random Forest	~0.90	~0.036

Both models demonstrate strong predictive performance on held-out test seasons.

Key Insights

Shooting efficiency strongly correlates with win percentage.

Turnovers negatively correlate with team performance.

League-wide shooting trends show long-term increase in 3P%.

Technologies Used

Python

Pandas

SQLite

Scikit-Learn

Matplotlib / Seaborn

How To Run

Install dependencies:

pip install pandas scikit-learn matplotlib seaborn


Run notebook top to bottom after kernel restart.

Dataset included in /data.
