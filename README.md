# Predicting customer purchase behaviour

I'm comparing Logistic Regression, Decision Tree, KNN and Random Forest to predict whether a user's online session ends in a purchase, using the UCI Online Shoppers Purchasing Intention dataset.

## running the project

```bash
conda env create -f environment.yml
conda activate purchase-intention
python -m ipykernel install --user --name purchase-intention --display-name "Purchase intention"
jupyter notebook
```

Open purchase_analysis.ipynb, choose the Purchase intention kernel and run from the first cell. The notebook downloads the CSV into data if it isn't
already there. Tables and plots go into results.

## in the notebook

- Data types, missing values, and duplicate checks
- Stratified 80/20 development and test split
- Training-data plots and purchase rates by category
- Encoding categorical features and scaling numeric features
- Five-fold cross-validation for a majority baseline and four classifiers
- A comparison with and without PageValues


## Notes

I keep the original CSV unchanged. Exact duplicate rows are removed before splitting, although separate visits could have identical values. Missing value
handling and scaling are fitted inside the training folds.

The test set stays separate until model selection is finished. I compared results without PageValues because its availability before a purchase needs checking.
Full-session totals also limit how early in a visit these predictions could be used.

## References

- Kim, S. Y., Shin, W., & Kim, H.-W. (2023). Predicting online customer purchase: The integration of customer characteristics and browsing patterns. Decision Support Systems, 177, 114105–114105. https://doi.org/10.1016/j.dss.2023.114105
- Hou, Y. Bin. (2025). Predicting Purchase Intentions from E-Commerce User Behavior: A Hybrid Modeling Approach for Data-Driven Marketing. Proceedings of the 2025 2Nd International Conference on Digital Economy, Blockchain and Artificial Intelligence, 192–196. https://doi.org/10.1145/3762249.3762281
- Sakar, C. & Kastro, Y. (2018). Online Shoppers Purchasing Intention Dataset [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5F88Q. 

