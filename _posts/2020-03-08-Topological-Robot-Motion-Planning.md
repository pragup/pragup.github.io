---
title: 'Topological Robot Motion Planning'
date: 2020-03-08
permalink: /posts/2020/03/Topological-Robot-Motion-Planning/
tags:
  - Topological Complexity
  - Robotics
  - Robot Motion Planning
  - Applied Algebraic Topology
  - Computational Topology
---

## Introduction ##
Topology is usually discussed in robotics through the notion of configuration spaces. For any mechanical system $R$, configuration space is the variety of all possible states ($X$).
In general, $X$ is determined by real parameters which can be stated as a subset of Euclidian space($\mathbb{R}^k$ )

Examples:

Robot Arm; Latombe, 1991. Robot arm consists of $4$ bars with endpoints as revolving joints as shown in Figure 1. If the bar is only allowed motion in a $2$ dimensional plane. 
Then each bar is allowed to move in a circle ($S^1$) independently and its configuration space is $X =  S^1 \times S^1 \times S^1 \times S^1$ i.e a $4$-dimensional torus. 
If each bar is allowed motion in $3$ dimension then its configuration space is $X =  S^2 \times S^2 \times S^2 \times S^2$. Note: self-intersection of the arm is allowed.
.center[
![Figure 1]( https://pragup.github.io/images/Sentence-Classification-Figure_1.png )
.caption[
**Fig. 1:** Image caption
]
]


Let $W$ is a topological space and $X = F(W, n)$ denote Cartesian product $W \times ...... \times W$, $n$ times  contains tuple $(w_1,....., w_n)$ such that $w_i \neq w_j$ whenever $i \neq j$. $X = F(W, n)$ is usual configuration space for collision free motion of $n$ particles.

