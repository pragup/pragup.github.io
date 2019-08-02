---
title: 'Adversarial Robustness Training in Neural Network'
date: 2019-07-31
permalink: /posts/2019/07/Adversarial-Robustness-Training/
tags:
  - cool posts
  - category1
  - category2
---
## ABSTRACT ##
Neural network consistently misbehave on adversarial examples (input examples formed by little perturbation to examples from dataset such that perturbed examples output incorrect answers with high confidence. )

## RELATED WORK ##
Szegedy et al[^SzZaSuBrErGoFe2014] discovered that various machine learning algorithm including neural network misbehave with adversarial examples. It was observed that various type of models with different 
architecture misclassify same set of adversarial examples. Neural network in general can achieve high performance in supervised learning through back propagation making it hard to interpretate and can have
counter intuitive properties. Two of these counter intuitive properties are discussed in this paper[^SzZaSuBrErGoFe2014].
  
First property is related to semantic meaning of each unit. An example of semantic meaning is shown in Figure ??. In past work has been done by Ross et al[^GiDoDaMA2013], Goodfellow et al[^GoLeeLeSaNg2009]
, Matthew et al[^ZeFe2013] to show semantic meaning of any unit by finding an input that maximally activate a given unit. It is based on an underlying implicit assumption that units from last layer form 
distinguished basis for extracting semantics information. But they[^SzZaSuBrErGoFe2014] showed that random projection of activation function($\phi(x)$) can produce results semantically indistinguishable from 
coordinates of ($\phi(x)$) as shown in Figure ??. It give rise to a conjecture that neural network disentangle variation factor across coordinates. Typically it can be seen as space of 
activations rather than individual units, that contains semantic information. *A similar and important result was shown by Mikolov et al[^MiChCoDe2013] where words are represented in*
*vector space and it preserve semantic relation and analogies. At the same time each unit of vector (word) do not contain any semantic information.* 

The second property stability of neural network with respect to small perturbation to their input. Consider a task of recognizing objects by deep neural network. We would expect small perturbation do not 
change class of the image. But this not true, these examples are called adversarial examples. We can generate adversarial examples by applying perturbation to maximize the prediction error. *It has been*
*observed that adversarial examples are robust and are shared by neural network with varied number of layers, activation or trained on different subset of training data. If an example is hard for one neural*
*network then probalistically it is still hard for other neural network.*  This suggest deep neural network learned by back propagation have *counter intuitive charactierstics and intrinsic blind spots*, whose
structure is connected data distribution in non obvious way. Adversarial phenomenon is not specific to deep neural network but affects other machine learning models including linear classification such as
support vector machine(SVM). May be adversarial examples exist not due to nonlinearity of the neural network. There are many problems exist that behaves accordingly in two or three dimension but shows unexpected
behavior in higher dimension also know as curse of dimension. According to this interpretation[^GoShSz2015] infinitesimal perturbation in input leads to large change in higher dimension dot product. This 
interpretation can again be misleading since it is not necessary for this phenomenon to occur as shown Below in Figure ??. 
*At first glance we can think of reducing adversarial attack by restricting access to internal parameters and gradients. Even with limited access it is been shown by Andrew et al[^IlEnAtLi2017] that adversarial*
*attack is still feasible.* 
Recently some theoritical work has been done explaining existence of adversarial examples and adversarial robust learning [^ScSaTsTaMa2018] [^TsSaEnTuMa2019]. Schmidt et al shown that sample complexity for 
adversarial robustness learning is significantly large as compared to standard leanring even for simple natural data model(guassian data model) as shown in Figure ??. They showed sample complexity of standard 
generalization compared to adversarially robust generalization independently of any learning algorithm. 

### STANDARD GENERALIZATION ###
Let $f_{\hat{w}}(x) = sgn(<\hat{w}, x>)$ is a linear classifier where $f_{\hat{w}}: R^d \to {1, -1}$. They studied a situation where good standard classification error can be achieved by a single sample as shown
in Theorm $4$.
![ArtSchmidt_Fig_1](https://pragup.github.io/images/ART_Schmidt_Theorm_4.PNG)
### ROBUST GENERALIZATION ###
$l_{\infty}^{\epsilon}$ are $l_{\infty}$ perturbation of input $x$ within $B_{\infty}^{\epsilon}(x)$ = {$ x' \in R^d  ||x - x'||_{\infty} \leq \epsilon $}  ball. For $l_{\infty}^{\epsilon}$ robust classification
error requires significantly more samples shown by Theorm $5, 6$.      


















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
