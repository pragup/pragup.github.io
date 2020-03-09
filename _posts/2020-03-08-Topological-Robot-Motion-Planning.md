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
$\[\gamma: I=[0, 1] \to X \]$
$PX$ is supplied with compact open topology (compact-open topology is a topology defined on the set of continuous maps between two topological spaces). For any space $Y$ let 
$p: Y^I \to Y \times Y$ be the map $p(\gamma) = (\gamma(0), \gamma(1))$ for $\gamma: I\to Y$. Then $p$ is fibration. Let $\[\pi : PX \to X \times X\]$ is a map where any path 
$\gamma \in PX$ is mapped to $(\gamma(0), \gamma(1)) \in X\times X$. Then $\pi$ is a fibration. 



### Definition 2.1 ###
The motion planning algorithm [^Mi2014] is a section of a fibration.
Let $s$ motion planning algorithm i.e a map $\[s: X \times X \to PX\]$ where $\[\pi \circ s  = 1_{X \times X}\]$
Note $ s(A, B) = \gamma \in PX $ where $\gamma $ is a continuous function of $t \in I$ for given points $A, B \in X$.
And $s$ is continuous, if suggested route($s(A, B)$) depends continuously on states $A$ and $B$.
Under what condition $s$ is continuous?. We will talk about it before that few definitions.

Let $f, g: X \to Y$ be continuous maps from topological space $X$ to space $Y$. A homotopy between $f$ and $g$ is another continuous map, $H : X \times [0, 1] \to Y$ such that 
$H(x, 0) = f(x)$ and $H(x, 1) = g(x) \forall x \in X$. This implies $f$ is homotopy equivalent to $g$ i.e $f \simeq g$. Equivalence relation implies reflexive, symmetric, transitive.
Now we extend definition of homotopy to topological spaces.$Y \subseteq X$ is a retract of $X$ if there is a continuous map $r: X \to Y$ with $r(y) = y ~~\forall y \in Y$, then $r$ 
is a retraction. An example is shown in Figure 2.a .$Y$ is a deformation retract of $X$ and $r$ is deformation retraction, if there is a homotopy between the retract $r$ and the 
identity map ${id}_{X}$ on $X$ i.e $$r \simeq {id}_{X}$$. Deformation retraction implies homotopy equivalence between topological space $X \simeq Y$. Some examples are shown in 
Figure 2. $X$ and $Y$ homotopy equivalent or have the same homotopy type, if there exists continuous maps $f: X \to Y$ and $g: Y \to X$ such that $$f \circ g \simeq {id}_{Y}$$ and 
$$g \circ f \simeq {id}_{X}$$. Denoted by $X \simeq Y$. Some examples are shown in Figure 3.

|![Figure 2a]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure2a.PNG)| 
|:--:| 
| *Figure 2.a* |
|![Figure 2b]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure2b.PNG)| 
|:--:| 
| *Figure 2.b* |
|![Figure 2c]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure2c.PNG)| 
|:--:| 
| *Figure 2.c* |
|![Figure 2d]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure2d.PNG)| 
|:--:| 
| *Figure 2.d* |
| Figure 2 : $Y$ is not a deformation retraction of $X$ but just a retraction, whereas $Y_i$ $\forall i \in {1, 2, 3, 4}$  is deformation retraction of $X$. Hence $$X \simeq Y_i ~~\forall i$$  [^Ba2018]|

|![Figure 3]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure3.PNG)| 
|:--:| 
| Figure 3: $X \simeq Y$(homotopy equivalent) but $Y$ is not a retract of $X$ in the figure on right implies deformation retract is not a necessary condition for homotopy equivalence. [^Ba2018] |


### Definition 2.2 ###

If $Y$ is a single point and $X \simeq Y$, then $X$ is contractible. Some examples are shown in figure 4.[^Ba2018]

|![Figure 4]( https://pragup.github.io/images/topologyrobotmotionplanning_Figure4.PNG)| 
|:--:| 
| *Figure 4* |

### Lemma 2.3 ###
A continuous motion planning algorithm in $X$ exists if and only if space $X$ is contractible. For a system with a non-contractible configuration space, any motion planning algorithm 
must be discontinuous .[^Mi2014]


## Topological Complexity TC(X) ##
Polyhedral is a subset $X \subset \mathbb{R}^n$, homeomorphic to underline space of some finite-dimensional simplicial complex. 

### Definition 3.1 ###
Let $X$ be a polyhedron. A motion planning algorithm $s: X \times X \to PX$ is called tame if $X \times X$ can be split into finitely many sets [^Mi2014]
$\[X \times X = F_1 \cup F_2 \cup ..... \cup F_k\]$ such that
1. The restriction $$s|F_i : F_i \to PX$$ is continuous, $i \in \{1, ..... , k\}$
2. $F_i \cap F_j = \emptyset$, where $i \neq j$
3. Each $F_i$ is a Euclidean Neighborhood Retract (ENR), defined below. 

Let $A \subset X$. Then A is a neighborhood retract (in $X$), if $A$ has a neighborhood($N_A$) in $X$ and $N_A$ is a retract of $X$. Every retract is also a neighborhood retract 
but every neighborhood retract not necessarily a retract. For example: $X = [0 ,1]$ and $A = \{0\} \cup \{1\}$ then A is a neighborhood retract but not a retract. Since map 
$r$(retract) is not continuous. If $X = \mathbb{R}^n$, then $A$ is euclidean neighborhood retract [^AD1995].

The topological complexity of the tame motion planning algorithm($s$) is the minimum number of domains($k$) such that $s$ is continuous for each domain. Topological complexity ($TC(X)$)
of finite-dimensional polyhedron $X$ is minimal topological complexity of tame motion planning algorithms in $X$.[^Mi2014]

__**Some of the topological complexity $TC(X)$ examples**__:

If X is contractible then by lemma 2.3 there exists a continuous tame motion planning algorithm. Hence $TC(X) = 1$
Given topological space $X = S^n$, where $n$ is odd. Consider $F_1 = \{(A, B)\mid A \neq -B\}$. Then $s_1: F_1 \to PX$ where $s_1(A, B)$ is a shortest geodesic arc along the
surface of $S^n$. Consider $F_2 = \{(A, -A)\}$ i.e pair of all antipodal points. We will find $s_2: F_2 \to PX$. Construct non vanishing vector field $v$ on $S^n$. Then 
$s_2(A, -A)$ move along the semi circle tangent to vector $v(A)$ from $A$ to $-A$ . And $X \times X = F_1 \cup F_2$, $TC(X) = 2$. Note: $v$ is non vanishing since n is odd.  
Given topological space $X = S^n$, where $n$ is even. Since $n$ is even any vector field $v$ has at least one zero. We may construct a vector field $v$ with one zero at 
$A_0$ i.e $v(A_0) = 0$. Then $F_1$ remains same as in second and $F_2 = \{(A, -A) \mid A \neq A_0\}$. Consider $F_3 = \{(A_0, -A_0)\}$ and $s_3: F_3 \to PX$ is defined 
by an arbitrary path from $A_0$ to $-A_0$. And $X \times X = F_1 \cup F_2 \cup F_3$, $TC(X) = 3$. Note: $v$ has one zero since n is even based on __**Hairy Ball Theorem**__. 

## References ##

[^Ra2018]: Ralph L. Cohen, , 2018. Algebraic topological aspects of morse theory. [http://virtualmath1.stanford.edu/~ralph/morsecourse/biglectures.pdf](http://virtualmath1.stanford.edu/~ralph/morsecourse/biglectures.pdf)

[^AD1995]: A. Dold., 1995. Lectures on Algebraic Topology. Classics in Mathematics. Springer Berlin Heidelberg, 1995.

[^Mi2014]: Michael Farber, 2014. Invitation to topological robotics.

[^Mi2017]: Michael Farber, 2017. Configuration spaces and robot motion planning algorithms (Lecture Notes).

[^Ba2018]: Bala Krishnamoorthy, 2018. Computational topology. [http://www.math.wsu.edu/math/faculty/bkrishna/FilesMath574/S18/LecNotes/Lec9_Math574_02062018.pdf](http://www.math.wsu.edu/math/faculty/bkrishna/FilesMath574/S18/LecNotes/Lec9_Math574_02062018.pdf)

[^EH1966]: E. H. Spanier, 1966. Algebraic topology. McGraw Hill.

[^Wi2019]: Wikipedia contributors, accessed 8-December-2019. Morse theory — Wikipedia, the free encyclopedia. [https://en.wikipedia.org/w/index.php?title=Morse_theory&oldid=925851127](https://en.wikipedia.org/w/index.php?title=Morse_theory&oldid=925851127)

