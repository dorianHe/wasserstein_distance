# wasserstein_distance
Wasserstein Distance or Earth Mover's Distance explanation and its application.

# What is Wasserstein distance
Wasserstein distance is distance between two distributions. In computer science, it is called the Earth Mover's Distance(EMD). EMD can be found by solving a transportation problem.

...

** A more mathematical explanation will be given in the near future. **

# Applications of Wasserstein distance
## Using EMD to exhibit the structure of color-distribution
In this application, the images are clustered according to pixels. In [3], the images are clustered by kd-tree. In my example, I used kmeans. I chose 20 as the number of clusters for image one, 10 as the number of clusters for image two. Each $m$ in signatrue is each center of the cluster, which is a 3-dimensional data point(RGB). $w$ is the number of points that belongs to the corresponding cluster. Signatures in image one are considered as suppliers. Signatures in image two are consumers.

...

** A complete implementation will be given in the near future. **

## Using EMD in GAN

# References
[1] https://en.wikipedia.org/wiki/Wasserstein_metric
[2] https://en.wikipedia.org/wiki/Earth_mover%27s_distance
[3] http://www.cs.jhu.edu/~misha/Papers/Rubner98.pdf
[4] https://www.alexirpan.com/2017/02/22/wasserstein-gan.html
