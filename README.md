## ## PENDING, in progress!

# Unsupervised Machine Learning - Cryptocurrency Clusters

## Background

* One of my clients was interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, was lost in the vast universe of cryptocurrencies. They’ve asked me to create a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system for this new investment.

* I took raw data and processed it to fit the machine learning models. Unsupervised machine learning was used since there was no known classification system. I  used several clustering algorithms to explore whether the cryptocurrencies could be grouped together with other similar cryptocurrencies. I used data visualization to share my findings with client.

## Instructions

### Data Preparation

* Read `crypto_data.csv` into Pandas. The dataset was obtained from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).

* Discarded all cryptocurrencies that are not being traded. Filtered for currencies that are currently being traded. Dropped the `IsTrading` column from the dataframe.

* Removed all rows that have at least one null value.

* Filtered for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.

* In order for the dataset to be comprehensible to a machine learning algorithm, its data should be numeric. Since the coin names do not contribute to the analysis of the data, I deleted the `CoinName` from the original dataframe.

* Next I converted the remaining features with text values, `Algorithm` and `ProofType`, into numerical data. I used Pandas to create dummy variables. 

* Last I standardize the dataset so that columns that contain larger values do not unduly influence the outcome.

### Dimensionality Reduction

* I created a dummy variables above which dramatically increased the number of features in the dataset. I performed dimensionality reduction with PCA. Rather than specify the number of principal components when I instantiated the PCA model, it is possible to state the desired **explained variance**. I preserveed 90% of the explained variance in dimensionality reduction. 

* I further reduced the dataset dimensions with t-SNE and visually inspected the results. I ran t-SNE on the principal components: the output of the PCA transformation. Then created a scatter plot of the t-SNE output. 

### Cluster Analysis with k-Means

* I used an elbow plot to identify the best number of clusters. A a for-loop was used to determine the inertia for each `k` between 1 through 10. The elbow plow appears at which value of `k` it appears.

### Recommendation

* Based on my findings, recommendations where provide to my clients as to if the cryptocurrencies could be clustered together? 

