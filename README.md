# Wasserstein distance

This repository is about Wasserstein Distance or Earth Mover's Distance explanations and its applications.

# What is Wasserstein distance

Wasserstein distance is the distance between two distributions. In computer science, it is called the Earth Mover's Distance(EMD). EMD can be found by solving a transportation problem.

## Transportation problem

Transportation problem was formalized by French mathematician [Gaspard Monge](https://en.wikipedia.org/wiki/Gaspard_Monge) in 1781. In general, it is about moving units of resources/soldiers from source to destination with minimum cost. For example, we have three suppliers $a$,$b$, and $c$ at different places and providing one same product with total amounts of $S_a$, $S_b$, and $S_c$. There are four stores $d$, $e$, $f$, $g$ with different locations demanding on the product with total amounts of $D_d$, $D_e$, $D_f$ and $D_g$. Transporting the product from suppliers to stores cost money. The transportation problem is to find the delivery plan with minimum cost under the assumption that the supply of the product equal to the demand of the product.

The more mathematical formulation would be using matrices and constraints. Let's say we have a cost matrix $C$. Element $c_{ij}$ in the matrix $C$ means the cost of moving one unit of product from supplier $i$ to store $j$. 

 $$C = \begin{bmatrix} c_{ad}, c_{ae}, c_{af}, c_{ag} \\ c_{bd}, c_{be}, c_{bf}, c_{bg} \\ c_{cd}, c_{ce}, c_{cf}, c_{cg} \end{bmatrix}$$

Considering we have a transportation matrix $T$, element $t_{ij}$ means the amount of product from supplier $i$ to store $j$.

$$T = \begin{bmatrix} t_{ad}, t_{ae}, t_{af}, t_{ag} \\ t_{bd}, t_{be}, t_{bf}, t_{bg} \\ t_{cd}, t_{ce}, t_{cf}, t_{cg} \end{bmatrix}$$

And accordingly, we have constraints for matrix $T$. For each row, the sum should equal to the amount that the supplier $i$  can provide. For each column, the sum should equal to the amount that the store demands.

$\forall i \in \{a, b, c\}$, $\sum_{j \in \{ d, e, f, g \}} t_{ij}= S_i$

$\forall j \in \{d, e, f, g\}$, $\sum_{i \in \{ a,b,c \}} t_{ij}= D_i$

The overall cost $P = \sum c_{ij}t_{ij}$, where $i \in \{ a, b, c\}$ and $j \in \{ d, e, f, g\}$. The goal is to minimize $P$, which is $\min(P) = \min(\sum c_{ij}t_{ij})$.

## Solution of transportation problem

The method for solving this problem that I learned during my bachelor in operations research course is called [Vogel's method / Vogel's approximation method](https://businessjargons.com/vogels-approximation-method.html).

More about vogel's method will be added … 

# Applications of Wasserstein distance

## Using EMD to exhibit the structure of color-distribution

In this application, the images are clustered according to pixels. In [3], the images are clustered by kd-tree. In my example, I used kmeans. I chose 20 as the number of clusters for image one, 10 as the number of clusters for image two. Each $m$ in the signature is each center of the cluster, which is a 3-dimensional data point(RGB). $w$ is the number of points that belongs to the corresponding cluster. Signatures in image one are considered as suppliers. Signatures in image two are consumers.

...

*A complete implementation will be given in the near future.*

## Using EMD in GAN

# References

[1] https://en.wikipedia.org/wiki/Wasserstein_metric

[2] https://en.wikipedia.org/wiki/Earth_mover%27s_distance

[3] http://www.cs.jhu.edu/~misha/Papers/Rubner98.pdf

[4] https://www.alexirpan.com/2017/02/22/wasserstein-gan.html