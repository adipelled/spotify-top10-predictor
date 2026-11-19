# Will It hit the Top 10?

Can we predict whether a song reaches the Top 10 on Spotify in a country, using only what the song sounds like and basic facts about it?

AI Collective @ UC Davis, Beginner Project Cycle, Fall 2026 (Group 5)

## Data
[Top Spotify Songs in 73 Countries (Daily Updated)](https://www.kaggle.com/datasets/asaniczka/top-spotify-songs-in-73-countries-daily-updated) on Kaggle.
The dataset updates daily; we used a single snapshot downloaded on Oct 11, 2026.

## Approach
- Collapsed daily chart data to one row per song per country
- Target: did the song ever reach rank 10 or better in that country?
- Features: audio features, explicitness, length, days since release, country
- Split by song so no song appears in both training and testing
- Compared logistic regression and a tuned random forest

## Results
| Model | Test F1 | Test ROC-AUC |
|---|---|---|
| Logistic regression | 0.440 | 0.599 |
| Random forest (tuned) | 0.454 | 0.647 |

Days since release was the most important feature.

## How to run
1. Download the dataset from Kaggle and put it in your Google Drive.
2. Open the notebook in Google Colab and update the file path in the first cell.
3. Run all cells. The saved model (`top10_model.joblib`) is included in this repo.
