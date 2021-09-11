---
title: 'Space Filling Curve Based Graph Partitioning Approach for Non-Metric Lawn Mowing And 3D Printing Problems'
date: 2021-04-20
permalink: /posts/2021/04/SFCDecomp/
tags:
  - Geometric Traveling Salesman Problem
  - Coverage Problem
  - Computational Complexity
  - Mixed Integer Programming
  - Discrete Optimization
  - CPLEX
  - Robot Motion Planning
---

{% include mathjax.html %}

## Overview ##

We formulated the 3d printing problem. The 3D printing problem is the same as the lawn mowing problem. We showed **minimum turn** lawn mowing / 3D printing  problem is NP-hard. It is known
**minimum length** lawn mowing / 3D printing  problem is NP-hard [^Ar2000]. Suppose we are solving the lawn mowing problem on space $X$. It is difficult to design an approximation algorithm,
if 
1. Turn cost is involved. Since the turn cost problem does not form a metric.
2. Edge weight in the dual graph of $X$ is not a metric.


 
## Our Work ##

We may want to solve the exact problem using MIP. But MIPs are hard to solve for large instances of the problem. This motivated the development of our work.
1. Find integral orthogonal polygon (IOP) for a given polygon.
2. Partition the dual graph of the IOP into multiple dual graphs using a space-filling curve. Each dual graph has its enter and exit vertices. Further, we guarantee there exists a 
Hamiltonian path for each dual graph between entry and exit vertices.  
3. We used MTZ formulation with turn cost to solve the Hamiltonian path problem for each dual graph.
4. Connect these Hamiltonian paths between dual graphs based on the space-filling curve sequence. 
We were able to solve problems with total $812,733$ nodes of a bunny over $360$ layers and $799,716$ nodes of buddha over $169$ layers. 
For more details check out our work (https://arxiv.org/pdf/1908.07452.pdf)

An illustration for a general polygon is shown below.
 
|![Figure 1]( https://pragup.github.io/images/SFCDecomp_Figure_1.png)|
 
|:--:| 

|![Figure 2]( https://pragup.github.io/images/SFCDecomp_Figure_2.png)| 

|:--:|

|![Figure 3]( https://pragup.github.io/images/SFCDecomp_Figure_3.png)| 

|:--:|

|![Figure 4]( https://pragup.github.io/images/SFCDecomp_Figure_4.png)| 

|:--:|

|![Figure 5]( https://pragup.github.io/images/SFCDecomp_Figure_5.png)| 

|:--:|

|![Figure 6]( https://pragup.github.io/images/SFCDecomp_Figure_6.png)| 

|:--:|

Images of some 3d printed layers of the bunny.
|![Figure 7]( https://pragup.github.io/images/SFCDecomp_Figure_7.png)| 
|:--:| 
|![Figure 8]( https://pragup.github.io/images/SFCDecomp_Figure_9.png)| 
|:--:|
|![Figure 9]( https://pragup.github.io/images/SFCDecomp_Figure_10.png)| 
|:--:|

Images of tool path of some layers of the bunny. 
|![Figure 10]( https://pragup.github.io/images/SFCDecomp_Figure_8.png)| 
|:--:|
|![Figure 11]( https://pragup.github.io/images/SFCDecomp_Figure_12.png)| 
|:--:|  


## References ##

[^Ar2000]: E. M. Arkin, S. P. Fekete, J. S. B. Mitchell, Approximation algorithms for lawn mowing and milling, Computational Geometry 17 (1-2) (2000) 25–50.
