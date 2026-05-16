# Predicting Virality of Online Slang

This project explores what makes an Urban Dictionary entry go viral — specifically, whether simple structural and thematic features can predict how many upvotes a term receives. Built in R with a tidymodels workflow, and presented as a fully styled interactive HTML report.

[View full analysis](https://sarahfeuer.github.io/urban-dictionary-virality-analysis/)

## Overview

Urban Dictionary is a crowdsourced platform where users submit and vote on definitions of slang terms and cultural references. While many entries stay obscure, others break into the mainstream and shape how entire generations talk — about politics, culture, and everything in between. This analysis asks: is there a pattern to what makes a word take off?

## Methodology

The dataset consists of 4,272 Urban Dictionary entries, including the term, definition, tags, and vote counts. Key steps include:

- Cleaning and restructuring the raw dataset
- Engineering three thematic predictors: whether the entry contains political language, explicit language, or tags
- 70/30 train/test split stratified by upvotes, with 10-fold cross-validation
- Training and tuning five regression models: K-Nearest Neighbors, Lasso, Elastic Net, Random Forest, and Boosted Trees
- Evaluating performance using Root Mean Squared Error (RMSE)

## Results

Random Forest achieved the lowest RMSE, followed closely by Elastic Net. K-Nearest Neighbors performed worst by a significant margin. The best Random Forest model used 2 predictors, 542 trees, and a minimum node size of 17 — achieving an RMSE of ~4,608 on cross-validation and ~3,627 on the held-out test set.

## Conclusion

After testing five models, Random Forest came out on top — which makes sense given its flexibility as a nonparametric ensemble method. That said, all models produced relatively high error values, which is honestly not that surprising. The three features used — political content, explicit content, and whether a term was tagged — turned out to have limited predictive power on their own. Of the three, having tags was by far the strongest signal, likely because tags get entries onto more pages and in front of more eyes. Political and explicit content trailed behind. The bigger takeaway is that virality in online language is messy. It's shaped by cultural timing, community dynamics, humor, and context in ways that simple categorical features can't fully capture. If I were to extend this project, I'd explore NLP techniques to extract richer linguistic signals from the definitions themselves — because the words people choose, and how they write them, probably matter a lot more than whether a term technically contains a political keyword.

## Tools

R · tidymodels · ggplot2 · dplyr · HTML/CSS/JS

## Data

[Urban Dictionary Terms](https://www.kaggle.com/datasets/athontz/urban-dictionary-terms/data) via Kaggle
