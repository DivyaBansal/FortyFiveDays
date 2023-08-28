Tabular Data:
1. Feature Engineering
2. Tree based models
3. Look at skrub


Missing data:
Fuzzy matching records
Data imputation

For smooth predictors:
sklearn.preprocessing.QuantileTransformer
IterativeImputer(add_indicator=True) -> make columns more Gaussian/Uniform
HistGradientBoosting caters for missing values

Feature Engineering:
1. Use domain knowledge
2. Augment table with relevant outside info
3. Make existing columns into more useful than existing info
   - Example use NLP to get categories from text columns 
    
Feature pipeline
Training pipeline
Inference Pipeline

First always prepare baselines

Clustering algos:
PCA
UMAP
K-Means
DBSCAN
