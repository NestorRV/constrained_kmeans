# constrained_kmeans

This project is a version of the original work by Stanislaw Adaszewski. Here you can find the [original]. Stanislaw Adaszewski's implementation is only compatible with Python 2.x, this one works with Python 3.x.

The algorithm consists of regular K-Means implementation where cluster assignment is done by solving Minimum Cost Flow (MCF) problem. 

How to use it:

```python
from constrained_kmeans import constrained_kmeans
(centroids, assignment, f) = constrained_kmeans(data, demand, maxiter=None, fixedprec=1e9)
```

where data is a vector of N-dimensional points (e.g. [[0, 0, 0], [1, 1, 1], [2,2,2]]), demand is a vector of minimum number of points for each cluster (implicitly it defines also the number of clusters), maxiter specifies the number of iterations after which to stop even if the algorithm didn’t converge, fixedprec allows to modify the distance multiplier. The return values are: C – cluster centers, M – assignments of point to clusters, f – last minimum cost flow solution. To further information see the [original] article.

[original]: <http://adared.ch/constrained-k-means-implementation-in-python/>