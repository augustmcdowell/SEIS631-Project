# Crunchyroll Anime Popularity and Ratings

## 1. Research Question

This project investigates whether more popular anime on Crunchyroll tend to receive higher user ratings than less popular anime. Popularity is measured using the number of user votes, while ratings reflect overall audience evaluation. This matters because popularity does not always mean quality, and this analysis can help show whether widely watched anime are also rated more favorably by viewers.

## 2. Hypothesis

Null hypothesis: There is no difference in average ratings between highly popular anime and less popular anime.

Alternative hypothesis: Highly popular anime have higher average ratings than less popular anime.

For this project, anime above the median number of votes are classified as highly popular, while anime at or below the median are classified as less popular.

## 3. Data Description

The data comes from a public Kaggle dataset: https://www.kaggle.com/datasets/filipefilardi/crunchyroll-anime-ratings

Each observation represents one anime title on Crunchyroll. The key variables used in this project are `anime`, `votes`, `rate`, and the genre columns. The `votes` column measures popularity, while the `rate` column measures user rating.

The original dataset contains 1,255 anime titles. I cleaned the data by removing rows where votes or ratings were equal to zero, since those values do not provide useful information for comparing popularity and audience rating. After cleaning, the dataset contained 1,235 anime titles.

## 4. Methods

The main test statistic is the difference in mean rating between highly popular anime and less popular anime:

mean rating of high popularity anime - mean rating of low popularity anime

I used a permutation test to test the null hypothesis. Under the null hypothesis, popularity group should not be related to rating, so I shuffled the popularity labels many times and recalculated the difference in means each time.

I also used bootstrapping to estimate uncertainty for two metrics: the mean rating difference and the median rating difference. The CLT does not directly apply to the median difference because the Central Limit Theorem is mainly about sampling distributions of means, not medians.

## 5. Results

After cleaning the data, the median number of votes was 42. Anime with more than 42 votes were labeled high popularity.

The observed mean rating for high popularity anime was about 4.29, while the observed mean rating for low popularity anime was about 4.00. The observed difference in mean rating was about 0.29 rating points.

The permutation test produced a p-value near 0, meaning the observed difference was very unlikely under the null hypothesis. This suggests statistically significant evidence that highly popular anime tend to have higher ratings.

The bootstrap confidence interval for the median rating difference was approximately 0.24 to 0.44. Since this interval is above 0, it supports the same conclusion.

## 6. Uncertainty Estimation

I used 5,000 resamples for both the permutation test and the bootstrap intervals. The permutation distribution was centered near 0, which represents what differences would look like if popularity group and rating were unrelated.

The bootstrap distributions were centered above 0, suggesting that high popularity anime usually had higher ratings in repeated resamples. The confidence intervals did not include 0, so the difference appears meaningful in this dataset.

## 7. Limitations

This analysis is based only on Crunchyroll data, so it may not represent all anime viewers. Vote counts may also be affected by how long an anime has been available, how well-known it already is, or whether it belongs to a popular franchise. Also, this is observational data, so the results show an association between popularity and rating, not proof that popularity causes higher ratings.

## 8. References

Filipe Filardi. Crunchyroll Anime Ratings. Kaggle. https://www.kaggle.com/datasets/filipefilardi/crunchyroll-anime-ratings

Python libraries used: pandas, numpy, matplotlib.