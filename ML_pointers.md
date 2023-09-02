
Descriptive statistics:
summarize dataset e.g. mean, median, std dev, visualizations

Inferential statistics:
hypothesis testing

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
   - Example use NLP to get semantically similar categories from text columns 

If we are given a distribution of Y given X which is not gaussian say Poisson/Zero inflated etc. we can try:
1. boosted methods/NNs
2. Bayesian methods by giving a **prior** on the target
3. Two step model in zero inflated: where you first classify zero and positive values and then perform regression for the positive values

Outlier Detection:
1. Robust z-score: How far are data points from the median? Calculate median absolute deviation.
2. Isolation Forest: Tree-based algorithm. Partitions data to isolate points. If we need many partitions to isolate a point, it is likely to be an inlier. On the other hand, if we need very few partitions it is likely an outlier.
3. Local outlier factor: Density based. Based on reachability distance.
4. Clustering


Structure:
Feature pipeline
Training pipeline
Inference Pipeline

First always prepare baselines

Clustering algos:
- **Expectation Maximization:**  Data points are grouped based on the probability of belonging to either a normal or a gaussian distribution.

- **K-Means:** Data is organised into clusters based on how close data points are to the centre of clusters also known as centroid.

- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):** Clusters are defined by areas of concentrated density. It searches areas of dense data points and assigns those areas to the same clusters.

- **Hierarchical:** top-down - assume one big cluster and break down into smaller clusters; bottom-up: assume all data points as separate clusters and merge. 

- **Gaussian Mixture Models (GMM):** The Gaussian mixture models is an extension of the k-means clustering algorithm. It is based on the idea that each cluster may be assigned to a different Gaussian distribution. GMM uses soft-assignment of data points to clusters (i.e. probabilistic and therefore better) when contrasting with the K-means approach of hard-assignments of data points to clusters.

1. For clusters with different densities: OPTICS, GMM, Agglomerative (bottom up hierarchical), Spectral
2. For irregularly shaped clusters and outliers: DBSCAN, OPTICS,  GMM, Spectral
3. Homogenous data (no clusters): DBSCAN, OPTICS, Agglomerative

ROC:
 TPR vs FPR

AUC: 
	Probability that the model ranks a random positive example more highly than a random negative example.
	It is:
	**scale-invariant** - It measures how well predictions are ranked, rather than their absolute values. Caveat: doesn't take into account classification probability outputs.
	**classification-threshold-invariant** - It measures the quality of the model's predictions irrespective of what classification threshold is chosen. Caveat: In cases where there are wide disparities in the cost of false negatives vs. false positives, it may be critical to minimize one type of classification error.


Type I error: False positive

Type II error: False negative