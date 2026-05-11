# Crunchyroll Anime Popularity and Ratings

## Research Question

This project investigates whether highly popular anime on Crunchyroll tend to receive higher user ratings than less popular anime. Popularity is measured using the number of user votes, while ratings reflect overall audience evaluation.

## Hypothesis

Null Hypothesis:
There is no difference in average ratings between highly popular anime and less popular anime.

Alternative Hypothesis:
Highly popular anime have higher average ratings than less popular anime.

Anime above the median number of votes were classified as highly popular, while anime at or below the median were classified as less popular.

## Data Source

The data for this project comes from a public Kaggle dataset containing Crunchyroll anime ratings, vote counts, and genre information:

https://www.kaggle.com/datasets/filipefilardi/crunchyroll-anime-ratings

Each row in the dataset represents one anime title on Crunchyroll.

## Main Findings

The analysis found that highly popular anime generally received higher ratings than less popular anime. A permutation test produced an extremely small p-value, suggesting that the observed difference in ratings was unlikely to occur by random chance alone.

Bootstrap confidence intervals for both the mean and median rating differences also supported this conclusion, as the intervals remained above zero.