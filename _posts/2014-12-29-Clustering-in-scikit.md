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




#### tags: ml, clustering