---
title: "SFCDecomp: Multicriteria Optimized Tool Path Planning in 3D Printing using Space-Filling Curve Based Domain Decomposition"
collection: publications
permalink: /publication/2022-06-05-SFCDecomp
excerpt: 'Space Filling Curve Based Graph Partitioning Approach for Non-Metric Lawn Mowing And 3D Printing Problems'
date: 2022-06-05
venue: 'International Journal of Computational Geometry & Applications'
paperurl: 'https://doi.org/10.1142/S0218195921500096'
citation: 'Prashant Gupta, Yiran Guo, Narasimha Boddeti, Bala Krishnamoorthy. (2022). &quot;SFCDecomp: Multicriteria Optimized Tool Path Planning in 3D Printing using Space-Filling Curve Based Domain Decomposition.&quot; <i>International Journal of Computational Geometry & Applications</i>. 1(1)'
---
![First Figure 1]( https://pragup.github.io/images/SFCDecomp_Figure_6.png )
![First Figure 2]( https://pragup.github.io/images/SFCDecomp_Figure_7.png )

We explore efficient optimization of toolpaths based on multiple criteria for large instances of 3d printing problems.
We first show that the minimum turn cost 3d printing problem is NP-hard, even when the region is a simple polygon.  
We develop SFCDecomp, a space filling curve based decomposition framework to solve large instances of 3d printing problems efficiently by solving these optimization subproblems independently.
For the Buddha, our framework builds toolpaths over a total of 799,716 nodes across 169 layers, and for the Bunny it builds toolpaths over 812,733 nodes across 360 layers.
We demonstrate the utility of our framework by maximizing or minimizing tool path edge overlap between adjacent layers, while jointly minimizing turn costs. Strength testing of a tensile test specimen 
printed with tool paths that maximize or minimize adjacent layer edge overlaps reveal significant differences in tensile strength between the two classes of prints.

[Download paper here](https://arxiv.org/abs/2109.01769)