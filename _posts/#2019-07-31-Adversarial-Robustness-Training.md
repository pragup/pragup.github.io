---
title: 'Adversarial Robust Training(Neural Network)'
date: 2019-07-31
permalink: /posts/2019/07/Adversarial-Robustness-Training/
tags:
  - Machine Learning
  - Deep Neural Network
  - Theoretical
---
Neural network consistently misbehave on adversarial examples (input examples formed by little perturbation of input examples from the dataset such that perturbed examples output incorrect answers with high confidence)
as shown in Figure below. 

![Art_Fig_0](https://pragup.github.io/images/ART_Figure_0.PNG)

Szegedy et al[^SzZaSuBrErGoFe2014] discovered that various machine learning algorithm including neural network misbehave with adversarial examples. It was observed that various type of models with different 
architecture misclassify same set of adversarial examples. Neural network in general can achieve high performance in supervised learning through back propagation making it hard to interpretate and can have
counter intuitive properties. Two of these counter intuitive properties are discussed in this paper[^SzZaSuBrErGoFe2014].
  
First property is related to semantic meaning of each unit. An example of semantic meaning is shown in Figure below. 

![Art_Fig_1](https://pragup.github.io/images/ART_Figure_1.PNG)

In past work has been done by Ross et al[^GiDoDaMA2013], Goodfellow et al[^GoLeeLeSaNg2009]
, Matthew et al[^ZeFe2013] to show semantic meaning of any unit by finding an input that maximally activate a given unit. It is based on an underlying implicit assumption that units from last layer form 
distinguished basis for extracting semantics information. But Szegedy et al[^SzZaSuBrErGoFe2014] showed that random projection of activation function($\phi(x)$) can produce results semantically indistinguishable from 
coordinates of ($\phi(x)$) as shown in Figure below.

![Art_Fig_2](https://pragup.github.io/images/ART_Figure_2.PNG)

It give rise to a conjecture that neural network disentangle variation factor across coordinates. Typically it can be seen as space of activations functions rather than individual units, that contains 
semantic information. *A similar and important result was shown by Mikolov et al[^MiChCoDe2013] where words are represented in vector space and it preserve semantic relation and analogies. At the same* 
*time each unit of vector (word) do not contain any semantic information.* 

The second property stability of neural network with respect to small perturbation to their input. Consider a task of recognizing objects by deep neural network. We would expect small perturbation do not 
change class of the image. But this not true, these examples are called adversarial examples. We can generate adversarial examples by applying perturbation to maximize the prediction error. *It has been*
*observed that adversarial examples are robust and are shared by neural network with varied number of layers, activation or trained on different subset of training data. If an example is hard for one neural*
*network then probabilistically it is still hard for other neural network.*  This suggest deep neural network learned by back propagation have *counter intuitive characteristics and intrinsic blind spots*, whose
structure is connected data distribution in non obvious way. Adversarial phenomenon is not specific to deep neural network but affects other machine learning models including linear classification such as
support vector machine(SVM). May be adversarial examples exists not due to nonlinearity of the neural network. There are many problems exist that behaves accordingly in two or three dimension but shows unexpected
behavior in higher dimension also know as curse of dimension. According to this interpretation[^GoShSz2015] infinitesimal perturbation in input leads to large change in higher dimension dot product. This 
interpretation can again be misleading since it is not necessary for this phenomenon to occur as shown in the Figure below.

![Art_Fig_3](https://pragup.github.io/images/ART_Figure_3.PNG)
 
*At first glance we can think of reducing adversarial attack by restricting access to internal parameters and gradients. Even with limited access it is been shown by Andrew et al[^IlEnAtLi2017] that adversarial*
*attack is still feasible.* 
Recently some theoretical work has been done explaining existence of adversarial examples and adversarial robust learning [^ScSaTsTaMa2018] [^TsSaEnTuMa2019]. Schmidt et al[^ScSaTsTaMa2018] shown that sample complexity for 
adversarial robustness learning is significantly large as compared to standard learning even for simple natural data model(Gaussian data model) as shown in Figure below. They suggest CIFAR10 is not able to attain higher 
accuracy as compared with MNIST because dataset may not be large enough to train convolution neural network robustly.  

![Art_Fig_4](https://pragup.github.io/images/ART_Schmidt_Figure_1.PNG)

They showed sample complexity of adversarially robust generalization compared to standard generalization, independently of any learning algorithm.


### STANDARD GENERALIZATION ###
Let $f_{\hat{w}}(x) = sgn(<\hat{w}, x>)$ is a linear classifier where $f_{\hat{w}}: R^d \to \{1, -1 \}$. They studied a situation where good standard classification error can be achieved by a single sample as shown
in Theorm $4$.
![ArtSchmidt_Fig_1](https://pragup.github.io/images/ART_Schmidt_Theorm_4.PNG)
### ROBUST GENERALIZATION ###
$l_{\infty}^{\epsilon}$ are $l_{\infty}$ perturbation of input $x$ within $B_{\infty}^{\epsilon}(x)$ = {$ x' \in R^d $ $ \mid $ $\mid{x - x'}\mid_{\infty}$   $\leq \epsilon $}  ball. For $l_{\infty}^{\epsilon}$
robust classification error requires significantly more samples shown by Theorm $5, 6$[^ScSaTsTaMa2018].      
![ArtSchmidt_Fig_1](https://pragup.github.io/images/ART_Schmidt_Theorm_5.PNG)
![ArtSchmidt_Fig_2](https://pragup.github.io/images/ART_Schmidt_Theorm_6.PNG)
By theorm $5, 6$ sample complexity $n$ is bounded as $\frac{c}{log(d)} \leq \frac{n}{\epsilon^2 \sqrt{d}}\leq  c'$. 
When perturbation has $l_{\infty}$, then sample complexity of robust generalization is larger than that of standard generalization by $\sqrt{d}$ i.e polynomial in dimension. This shows that high dimensionality problem require
significantly large amount of samples for adversarial robustness. Moreover they[^ScSaTsTaMa2018] also showed using Theorm $11$ that given $n$ samples there is a single adversarial perturbation that *can be applied to all learning*
*algorithms and have constant number of samples being misclassified*.  
![ArtSchmidt_Fig_3](https://pragup.github.io/images/ART_Schmidt_Theorm_11.PNG)

In general adversarial training is computationally expensive (more training time) and according to Schmidt et al [^ScSaTsTaMa2018] require more data points. According to Dimitris et al[^TsSaEnTuMa2019] standard classification training 
and adversarial robust training are fundamentally at odds. Even though standard training model are benefited from adversarial robustness in limited training data but in general there is a trade off between standard accuracy 
and adversarially robust accuracy of the model as shown in Figures below. 
![ArtDimitris_Fig_3](https://pragup.github.io/images/ART_Dimitris_Figure_2.PNG)
![ArtDimitris_Fig_4](https://pragup.github.io/images/ART_Dimitris_Figure_3.PNG)
*Why there is a tradeoff between standard and adversarially robust accuracy ?*

*Reason:* standard classifier learns a lot from weakly correlated features to improve the accuracy of the model as discussed below. 

### STANDARD CLASSIFICATION ###
Let data model consists of input - output pair $(x, y)$ sampled from $D$ as below.
![ArtDimitris_Fig_1](https://pragup.github.io/images/ART_Dimitris_Figure_1.PNG)
$N(\mu, \sigma^2)$ is normal distribution with mean $\mu$, variance $\sigma^2$ and $p \geq 0.5$. $\eta$ is chosen such that linear classifier achieve higher accuracy e.g $\eta = O(\frac{1}{\sqrt{d}})$. 
Let $x_1$ is moderately correlated with label and $x_2, ........ , x_{d + 1}$ are weakly correlated with the label. For this simple problem linear classifier $f_{avg}(x) = sgn(w_{unif}^{T}\cdot x)$, where 
$w_{unif} = [0, \frac{1}{d}, ........ , \frac{1}{d}]$, can achieve an accuracy close to $100\%$ for $d$ large enough 

$Pr(f_{avg}(x) = y) = Pr(N(\eta, \frac{1}{d})  > 0) \geq 99 \%$, when $\eta \geq \frac{3}{\sqrt{d}}$. 
### ADVERSARIALLY ROBUST CLASSIFICATION ###
As we can see average of weakly correlated features can give us a single highly correlated meta-feature with the label. Unfortunately this will completely break in adversarial setting. If $l_{\infty}$ bounded adversary
is only allowed moderate amount of perturbation $\epsilon$, then adversary is not affected by meta feature. But for e.g $\epsilon = 2\eta$, then adversary can shift weakly correlated features to $-y$. Now perturbed input features
$x_2', ............, x_{d+1}'$ are sampled from i.e $N(-\eta y, 1)$. Now weakly correlated features belongs to a wrong class.

$\min_{\mid \mid \delta \mid \mid_{\infty}} Pr(sign(x + \delta) = y) \leq Pr(N(-\eta, \frac{1}{d}) > 0)$

Hence adversarial accuracy cannot be better than $1 \%$. It clearly indicate meta feature is far more predictive of true label, but highly inaccurate in case of adversary. Hence it creates a dilemma between standard and 
adversarial accuracy. Paper[^TsSaEnTuMa2019] gave robust accuracy trade off theorm $2.1$.
![ArtDimitris_Fig_2](https://pragup.github.io/images/ART_Dimitris_Theorm_2_1.PNG)

According to it if $p < 1$ as standard accuracy approach $100 \%$ ($\delta \to 0$), implies adversarial accuracy falls to $0\%$. If $p = 0.95$, then for any standard accuracy more than $1 - \delta$, robust accuracy is 
atmost $19\delta$.                                 

**Results from both the papers [^ScSaTsTaMa2018] [^TsSaEnTuMa2019] are not learning algorithm dependent. Hence can be extended to deep neural network.** 

## References ##

[^SzZaSuBrErGoFe2014]: Szegedy et al, 2014.Intriguing properties of neural networks. Available at: [https://arxiv.org/abs/1312.6199](https://arxiv.org/abs/1312.6199)

[^GiDoDaMA2013]: Ross et al, 2013. Rich feature hierarchies for accurate object detection and semantic segmentation. Available at: [http://arxiv.org/abs/1311.2524](http://arxiv.org/abs/1311.2524)

[^GoLeeLeSaNg2009]: Goodfellow et al, 2009. Measuring Invariances in Deep Networks. Available at: [http://papers.nips.cc/paper/3790-measuring-invariances-in-deep-networks.pdf](http://papers.nips.cc/paper/3790-measuring-invariances-in-deep-networks.pdf)

[^ZeFe2013]: Matthew et al, 2013. Visualizing and Understanding Convolutional Networks. Available at : [http://arxiv.org/abs/1311.2901](http://arxiv.org/abs/1311.2901) 

[^MiChCoDe2013]: Mikolov et al, 2013. Efficient estimation of word representations in vector space. Available at: [https://arxiv.org/abs/1301.3781](https://arxiv.org/abs/1301.3781)

[^IlEnAtLi2017]: Andrew et al, 2017. Query-Efficient Black-box Adversarial Examples. Available at: [http://arxiv.org/abs/1712.07113](http://arxiv.org/abs/1712.07113)

[^GoShSz2015]: Goodfellow et al, 2015. Explaining and Harnessing Adversarial Examples. Available at: [http://arxiv.org/abs/1412.6572](http://arxiv.org/abs/1412.6572)

[^ScSaTsTaMa2018]: Schmidt et al, 2018. Adversarially Robust Generalization Requires More Data. Available at: [http://arxiv.org/abs/1804.11285](http://arxiv.org/abs/1804.11285)

[^TsSaEnTuMa2019]: Dimitris et al, 2018. Robustness May Be at Odds with Accuracy. Available at: [https://arxiv.org/abs/1805.12152](https://arxiv.org/abs/1805.12152)
