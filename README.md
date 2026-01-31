# Early-Game Advantage: Predicting League of Legends Match Outcomes

## Project Overview
This project utilizes machine learning to predict the outcome of League of Legends matches based solely on performance data from the first ten minutes of gameplay. By analyzing early-game indicators such as gold difference, KDA (Kills, Deaths, Assists), and objective control, the model identifies which factors are most predictive of eventual victory.

The project was developed for the Introduction to Data Science course at the University of Helsinki.

## Data Collection and Features
Data was programmatically collected from the Riot Games API using the `riotwatcher` library. The dataset consists of match statistics extracted at the 10-minute mark to capture the "snowball" effect often seen in competitive play.

### Key Features Analyzed:
- **Gold Difference**: Total team gold vs. enemy team gold at 10 minutes.
- **KDA Ratio**: Combined kills, deaths, and assists for the team.
- **Objectives**: Capture of early Dragons and Voidgrubs.
- **Timeline Events**: Precise extraction of champion kills and elite monster kills from the match timeline.

## Methodology
The analysis follows a standard data science pipeline:
1. **Extraction**: Using PUUIDs to fetch match histories and detailed timelines.
2. **Preprocessing**: Transforming raw JSON API responses into a structured CSV format.
3. **Modeling**: Implementing a GradientBoosting classifier to determine win probabilities.
4. **Evaluation**: Assessing performance using Accuracy and ROC AUC metrics.

## Results
The model established that early gold leads and objective control are the strongest predictors of a win.
- **Model Accuracy**: 0.703
- **ROC AUC Score**: 0.780

These results demonstrate that while the first ten minutes are not entirely deterministic, they provide a statistically significant foundation for predicting match results.
