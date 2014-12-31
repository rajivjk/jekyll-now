---
layout: post
title: Clustering Algorithms in SciKit Learn.
---

1. The main module to use is *sklearn.cluster* ..duh!
2. There are several clustering algorithms that have been implemented. 
3. Each algorithm comes in two variants:
	1. A *class* - that implements the *fit* method, it takes in the features and the labels and returns an estimator (probably). 
    	1. The labels for the training data can be found in the labels_ attribute.
	2. A *function* - that given a training data, returns an array of integer labels corresponding to the different clusters.
4. **Concept**: the main idea is to minimize the 'within cluster' *inertia* - the sum-of-square distances from the cluster centroid. Surprisingly, this approach has some drawbacks:
	1. It makes the assumption that clusters are convex (that is a line drawn through the cluster intersects the boundry only twice.)
	2. In very high dimensional spaces (that is, when the *curse of dimensionality* is in effect), this may lead to suboptimal cluster allocations (since Euclidean distances are large in such a case). 
5. **Algorithm**: The algorithm is very simple
	1. Randomly nominate *k* data points to be the cluster centroid
	2. Now calculate the distance of remaining points from each of the *k* centroids.
	3. Form clusters by assigning data points for which the distance from the centroid is mininum.
	4. Now for each of the k clusters, calculate the new centroid.
	5. Repeat steps 2, 3, 4 till the centroid doesn't move significantly. 
6. Given enough time, K-means will always converge, however the clusters may not be optimal. The final result is highly dependent on the initialization of the centroids. So the computation is often done several times, with different initializations of the centroids. One method to help address this issue is the k-means++ initialization scheme, which has been implemented in scikit-learn (use the init='kmeans++' parameter). This initializes the centroids to be (generally) distant from each other, leading to provably better results than random initialization.

#### tags: ml, clustering