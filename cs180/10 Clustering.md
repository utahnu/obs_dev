Daily Note: [[2023-03-16]] -- [*created*:: 2023-03-16] #cs180 

# K-Means

Points should be closer to the center of their cluster than any other cluster

**Two key ingredients:**
- Distance measurement
- Centroid location

# DBSCAN

Finds clusters of different shapes

Starts with a point, clusters every point within it's neighborhood. 
- all points within range of are clustered
- A point must have a minimum amount of neighbors to become a new center

# Probabilistic Clustering

Cluster by probability through 3D Gaussian models

There is a builtin function in scikit learn