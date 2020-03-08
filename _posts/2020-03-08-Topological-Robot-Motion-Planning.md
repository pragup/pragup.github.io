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

{% include mathjax.html %}

## Introduction ##
Topology is usually discussed in robotics through the notion of configuration spaces. For any mechanical system $R$, configuration space is the variety of all possible states ($X$).
In general, $X$ is determined by real parameters which can be stated as a subset of Euclidian space($\mathbb{R}^k$ )

Examples:

Robot Arm; Latombe, 1991. Robot arm consists of $4$ bars with endpoints as revolving joints as shown in Figure 1. If the bar is only allowed motion in a $2$ dimensional plane. 
Then each bar is allowed to move in a circle ($S^1$) independently and its configuration space is $X =  S^1 \times S^1 \times S^1 \times S^1$ i.e a $4$-dimensional torus. 
If each bar is allowed motion in $3$ dimension then its configuration space is $X =  S^2 \times S^2 \times S^2 \times S^2$. Note: self-intersection of the arm is allowed.

|![Figure 1]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure1.PNG)| 
|:--:| 
| *Figure 1* |

Let $W$ is a topological space and $X = F(W, n)$ denote Cartesian product $W \times ...... \times W$, $n$ times  contains tuple $(w_1,....., w_n)$ such that $w_i \neq w_j$ 
whenever $i \neq j$. $X = F(W, n)$ is usual configuration space for collision free motion of $n$ particles.

## Motion Planning Algorithm ##
For a given mechanical system $R$ motion planning algorithm is a function that assigns to each ordered pair $(A, B)$ where $A$ is the initial state and $B$ is a final state a 
continuous motion of the mechanical system which starts at $A$ and ends at $B$. Let $X$ is the configuration space of the mechanical system and states are represented by points 
in $X$. Continuous motion of the system from state $A$ to $B$ is represented by continuous path $\gamma: [0, 1] \to X$, where $\gamma(0)= A$ and $\gamma(1)= B$. The system is 
path-connected if there exists a $\gamma$ for any arbitrary $A$ and $B$.     
$PX = X^I$ is the space of all continuous paths 
\[\gamma: I=[0, 1] \to X \]
$PX$ is supplied with compact open topology (compact-open topology is a topology defined on the set of continuous maps between two topological spaces). For any space $Y$ let 
$p: Y^I \to Y \times Y$ be the map $p(\gamma) = (\gamma(0), \gamma(1))$ for $\gamma: I\to Y$. Then $p$ is fibration. Let \[\pi : PX \to X \times X\] is a map where any path 
$\gamma \in PX$ is mapped to $(\gamma(0), \gamma(1)) \in X\times X$. Then $\pi$ is a fibration. 



#### Definition 2.1 #####
The motion planning algorithm [3] is a section of a fibration.
Let $s$ motion planning algorithm i.e a map \[s: X \times X \to PX\] where \[\pi \circ s  = 1_{X \times X}\]
Note $ s(A, B) = \gamma \in PX $ where $\gamma $ is a continuous function of $t \in I$ for given points $A, B \in X$.
And $s$ is continuous, if suggested route($s(A, B)$) depends continuously on states $A$ and $B$.
Under what condition $s$ is continuous?. We will talk about it before that few definitions.

Let $f, g: X \to Y$ be continuous maps from topological space $X$ to space $Y$. A homotopy between $f$ and $g$ is another continuous map, $H : X \times [0, 1] \to Y$ such that 
$H(x, 0) = f(x)$ and $H(x, 1) = g(x) \forall x \in X$. This implies $f$ is homotopy equivalent to $g$ i.e $f \simeq g$. Equivalence relation implies reflexive, symmetric, transitive.
Now we extend definition of homotopy to topological spaces.$Y \subseteq X$ is a retract of $X$ if there is a continuous map $r: X \to Y$ with $r(y) = y ~~\forall y \in Y$, then $r$ 
is a retraction. An example is shown in Figure 2.a .$Y$ is a deformation retract of $X$ and $r$ is deformation retraction, if there is a homotopy between the retract $r$ and the 
identity map ${id}_{X}$ on $X$ that is $r \simeq {id}_{X}$.
<!-- i.e  Deformation retraction implies homotopy equivalence between topological space $X \simeq Y$. Some examples are shown in 
Figure 2. $X$ and $Y$ homotopy equivalent or have the same homotopy type, if there exists continuous maps $f: X \to Y$ and $g: Y \to X$ such that $f \circ g \simeq {id}_{Y}$ and 
$g \circ f \simeq {id}_{X}$. Denoted by $X \simeq Y$. Some examples are shown in Figure 3.
-->