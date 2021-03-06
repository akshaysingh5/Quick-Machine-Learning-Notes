## K-Means Clustering

![K-Means](https://github.com/pradeepsinngh/Machine-Learning-Notes/blob/master/17%20Clustering/data/k-means.gif)

- To begin, we first select a number of classes/groups to use and randomly initialize their respective center points. 
- The center points are vectors of the same length as each data point vector.
- Each data point is classified by computing the distance between that point and each group center, and then classifying the point to be in the group whose center is closest to it.
- Based on these classified points, we recompute the group center by taking the mean of all the vectors in the group.
- Repeat these steps for a set number of iterations or until the group centers don’t change much between iterations.

#### Advantage:
- K-Means is pretty fast, as all we’re really doing is computing the distances between points and group centers; very few computations! It thus has a linear complexity O(n).

#### Disadvantage:
- You have to select how many groups/classes there are. 
- K-means also starts with a random choice of cluster centers and therefore it may yield different clustering results on different runs of the algorithm. Thus, the results may not be repeatable and lack consistency. 
- Its naive use of the mean value for the cluster center. We can see why this isn’t the best way of doing things by looking at the image below. On the left hand side it looks quite obvious to the human eye that there are two circular clusters with different radius’ centered at the same mean. K-Means can’t handle this because the mean values of the clusters are a very close together. 

![K-Means Demerits](https://github.com/pradeepsinngh/Machine-Learning-Notes/blob/master/17%20Clustering/data/failure%20cases%20for%20K-Means.png)
- K-Means also fails in cases where the clusters are not circular, again as a result of using the mean as cluster center.


Other cluster methods are more consistent.

K-Medians is another clustering algorithm related to K-Means, except instead of recomputing the group center points using the mean we use the median vector of the group. This method is less sensitive to outliers (because of using the Median) but is much slower for larger datasets as sorting is required on each iteration when computing the Median vector.
