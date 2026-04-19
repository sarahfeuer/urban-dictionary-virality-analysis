# Predicting Virality of Online Slang

This project analyzes what drives the popularity of Urban Dictionary entries by modeling upvotes using a combination of feature engineering and machine learning techniques. The goal is to understand which characteristics of language and content are associated with higher levels of engagement.
The complete project, including exploratory data analysis, modeling workflow, and visualizations, is available here:

[View full analysis](urban_dictionary_virality_report.pdf)


---

## Overview

Urban Dictionary is a crowdsourced platform where users submit and vote on definitions of slang terms and cultural references. While many entries remain obscure, others gain significant traction and shape broader online language.

This analysis explores whether simple structural and thematic features can help predict which terms are more likely to become widely upvoted.

---

## Methodology

The dataset consists of 4,272 Urban Dictionary entries, including the term, definition, tags, and vote counts.

Key steps in the analysis include:

- Cleaning and restructuring the dataset  
- Engineering features to capture thematic signals:
  - Whether the entry contains political language  
  - Whether the entry contains explicit language  
  - Whether the entry includes tags  
- Splitting the data into training and testing sets (70/30 split, stratified by upvotes)  
- Applying 10-fold cross-validation to ensure robust model evaluation  
- Training and tuning five regression models:
  - K-Nearest Neighbors  
  - Lasso Regression  
  - Elastic Net  
  - Random Forest  
  - Boosted Trees  
- Evaluating model performance using Root Mean Squared Error (RMSE)

---

## Results

Among the models tested, Random Forest achieved the lowest RMSE, followed closely by Elastic Net.

Despite differences in performance, all models produced relatively high error values, suggesting that the selected features capture only a portion of what drives virality.

---

## Key Insight

The results indicate that simple categorical features, such as whether a term is political, explicit, or tagged, have limited predictive power on their own. While ensemble methods improve performance, the overall error suggests that virality in online language is influenced by more complex linguistic, cultural, and contextual factors that are not captured in this feature set.

This highlights a broader challenge in modeling user-generated content: popularity is not solely determined by structure, but by evolving social dynamics and context.

---

## Tools and Technologies

- R  
- tidymodels  
- ggplot2  
- dplyr  

---

## Data

Urban Dictionary Terms dataset (Kaggle)
