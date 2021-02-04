---
title: "Continuous Toolpath Planning in a Graphical Framework for Sparse Infill Additive Manufacturing"
collection: publications
permalink: /publication/2019-08-22-Continuous-Toolpath-Planning-in-Additive-Manufacturing
excerpt: 'In this paper we have developed a framework for layer by layer 3d printing, based on euler transformation approach, we developed in our previous work.'
date: 2020-10-01
venue: 'Computer-Aided Design'
paperurl: 'https://doi.org/10.1016/j.cad.2020.102880'
citation: 'Prashant Gupta, Bala Krishnamoorthy. (2020). &quot;Continuous Toolpath Planning in a Graphical Framework for Sparse Infill Additive Manufacturing.&quot; <i>Computer-Aided Design</i>. 1(1)'
---

![First Figure 1]( https://pragup.github.io/images/PyramidPlan.png )

![First Figure 2]( https://pragup.github.io/images/PrintedPyramid.jpg )

We develop a framework that creates a new polygonal mesh representation of the 3D domain of a layer-by-layer 3D printing job on which we identify single, continuous tool paths covering each connected piece of the domain in every layer.
We present a tool path algorithm that traverses each such continuous tool path with no crossovers. The key construction at the heart of our framework is a novel Euler transformation that we introduced recently in a separate manuscript. 
Our Euler transformation converts a $2$-dimensional cell complex K into a new $2$-complex $\hat{K}$ such that every vertex in the $1$-skeleton $\hat{G}$ of $\hat{K}$ has degree $4$. Hence $\hat{G}$ is Eulerian, and an Eulerian tour can
be followed to print all edges in a continuous fashion without stops. We start with a mesh K of the union of polygons obtained by projecting all layers to the plane. First we compute its Euler transformation $\hat{K}$. In the slicing step,
we clip $\hat{K}$ at each layer using its polygon to obtain $\tilde{K}$. We then patch $\tilde{K}$ by adding edges such that any odd-degree nodes created by slicing are transformed to have even degrees again. We print extra support
edges in place of any segments left out to ensure there are no edges without support in the next layer above. These support edges maintain the Euler nature of $\tilde{K}$. Finally, we describe
a tree-based search algorithm that builds the continuous tool path by traversing “concentric” cycles in the Euler complex. Our algorithm produces a tool path that avoids material collisions
and crossovers, and can be printed in a continuous fashion irrespective of complex geometry or topology of the domain (e.g., holes).
We presented this work in **Symposium on Solid and Physical Modeling, 2020**.  
[Download paper here](https://arxiv.org/pdf/1908.07452.pdf)
