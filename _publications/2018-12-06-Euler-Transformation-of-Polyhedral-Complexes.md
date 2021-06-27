---
title: "Euler Transformation of Polyhedral Complexes"
collection: publications
permalink: /publication/2018-12-06-Euler-Transformation-of-Polyhedral-Complexes
excerpt: 'We have developed an Euler Transformation algorithm that transforms an arbitrary planar graph $G$(i.e in $R^2$) to a planar graph $\hat{G}=(\hat{V}, \hat{E})$ where every vertex in $\hat{V}$ has even degree. We have shown that this transformation preserve geometry and topology of the domain. Further, we also proved that mesh quality of $\hat{G}$ is at most a constant factor off from the quality of $G$. As an immediate next step, we will extend the Euler transformation algorithm to arbitrary graph in $R^3$.'
date: 2021-06-26
venue: 'International Journal of Computational Geometry & Applications'
paperurl: 'https://www.worldscientific.com/doi/abs/10.1142/S0218195920500090'
citation: 'Prashant Gupta, Bala Krishnamoorthy. (2021). &quot;Euler Transformation of Polyhedral Complexes.&quot; <i>International Journal of Computational Geometry & Applications</i>. 1(1)'
---
![First Figure 1]( https://pragup.github.io/images/Euler_Transformation_Example.PNG )

We propose an Euler transformation that transforms a given $d$-dimensional cell complex $K$ for $d=2,3$ into a new $d$-complex $\hat{K}$ in which every vertex is part of a uniform even number of edges. Hence every vertex in the graph $\hat{G}$ that is the $1$-skeleton of $\hat{K}$ has an even degree, which makes $\hat{G}$ Eulerian, i.e., it is guaranteed to contain an Eulerian tour. Meshes whose edges admit Eulerian tours are crucial in coverage problems arising in several applications including 3D printing and robotics. 
For $2$-complexes in $R^2$ ($d=2$) under mild assumptions (that no two adjacent edges of a $2$-cell in $K$ are boundary edges), we show that the Euler transformed $2$-complex $\hat{K}$ has a geometric realization in $R^2$, and that each vertex in its $1$-skeleton has degree $4$. We bound the numbers of vertices, edges, and $2$-cells in $\hat{K}$ as small scalar multiples of the corresponding numbers in $K$. We prove corresponding results for $3$-complexes in $R^3$ under an additional assumption that the degree of a vertex in 
each $3$-cell containing it is $3$. In this setting, every vertex in $\hat{G}$ is shown to have a degree of $6$. We also presents bounds on parameters measuring geometric quality (aspect ratios, minimum edge length, and maximum angle) of $\hat{K}$ in terms of the corresponding parameters of $K$ (for $d=2,3$). Finally, we illustrate a direct application of the proposed Euler transformation in additive manufacturing.

[Download paper here](https://arxiv.org/pdf/1812.02412.pdf)