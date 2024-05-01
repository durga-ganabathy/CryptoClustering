# CryptoClustering
CRYPTO CLUSTERING:
Loaded the crypto_market_data.csv into a DataFrame.
Prepare the Data:

Used the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

To find the Best Value for k is identified Using the Original Scaled DataFrame -

Used the elbow method to find the best value for k using the following steps:

Created a list with the number of k values from 1 to 11.
Created an empty list to store the inertia values.
Created a for loop to compute the inertia with each possible value of k.
Created a dictionary with the data to plot the elbow curve.
Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

What is the best value for k?

From the elbow curve, the optimal value for k is 4. Therefore, the number of clusters would be 4.
To be noted: The inertia value for k=4 is 79.022435.

Cluster Cryptocurrencies with K-means Using the Original Scaled Data-

Used the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialized the K-means model with the best value for k.
The K-means model fit done using the original scaled DataFrame.
Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
Created a copy of the original data and add a new column with the predicted clusters.
Created a scatter plot using hvPlot as follows:
X and Y axis was set.
Colored the graph points with the labels found using K-means.
Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Optimized Clusters with Principal Component Analysis
Using the original scaled DataFrame, performed a PCA and reduced the features to three principal components.

What is the total explained variance of the three principal components?

The total explained variance of the three principal components is 89.5% . About 90% (0.3719856+ 0.34700813+ 0.17603793) of the total variance is condensed into the 3 PCA variables.

Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The Best Value for k was identified Using the PCA Data

Used the elbow method on the PCA data to find the best value for k using the following steps:

Created a list with the number of k-values from 1 to 11.
Created an empty list to store the inertia values.
Created a for loop to compute the inertia with each possible value of k.
Created a dictionary with the data to plot the Elbow curve.
Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

What is the best value for k when using the PCA data?
Does it differ from the best k value found using the original data?

4 is the best k value. The k value is the same in both the cases(original and PCA). However, inertia from the original data is high (Datasets with low concentration of elements) when compared to the inertia from the PCA data(low inertia - Datasets with a high concentration of elements). Hence the elements in the scatter plot from the original data is spread out. Whereas in the scatter plot from PCA data, the elements are tightly grouped together.

Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialized the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predicted the clusters to group the cryptocurrencies using the PCA data.
Created a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
Created a scatter plot using hvPlot as follows: X axis and Y axis set.
Colored the graph points with the labels found using K-means.
Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.


What is the impact of using fewer features to cluster the data using K-Means?
In both the cases, whether using original data or using PCA data the k value determined by the elbow method is 4. So, when it comes to clustering both the datasets exhibit similar underlying structures. However the inertia with k=4 for the original data is 79 and for the PCA data is 50 (49.6). Low inertia value reflects tighter and more compact clusters indicating better clustering performance. By using few features, the dimensionality of the data is reduced, making it easier for the K-Means to identify meaningful clusters. Hence using PCA data for dimensionality reduction and feature extraction provides effective clustering results.
