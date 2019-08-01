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

## Related Work ##
Szegedy et al[^SzZaSuBrErGoFe2014] discovered that various machine learning algorithm including neural network misbehave with adversarial examples. It was observed that various type of models with different 
architecture mis-classify same set of adversarial examples. Neural network in general can achieve high performance in supervised learning through back propagation making it hard to interpretate and can have
counter intuitive properties. Two of these counter intuitive properties are discussed in this paper[^SzZaSuBrErGoFe2014].  
First property is related to semantic meaning of each unit. An example of semantic meaning is shown in Figure ??. In past work has been done by Ross et al[^GiDoDaMA2013], Goodfellow et al[^GoLeeLeSaNg2009]
, Matthew et al[^ZeFe2013] to show semantic meaning of any unit by finding an input that maximally activate a given unit. It is based on an underlying implicit assumption that units from last layer form 
distinguished basis for extracting semantics information. But they[^SzZaSuBrErGoFe2014] showed that random projection of activation function($\phi(x)$) can produce results semantically 
indistinguishable from coordinates of ($\phi(x)$) as shown in Figure ??. It give rise to a conjecture that neural network disentangle variation factor across coordinates. Typically it 
can be seen as space of activations rather than individual units, that contains semantic information. A similar and important result was shown by Mikolov et al[^MiChCoDe2013] where words are represented in vector space 
and it preserve semantic relation and analogies. At the same time each unit of vector (word) do not contain any semantic information. 

The second property stability of neural network with respect to small perturbation to their input. Consider a task of recognizing objects by deep neural network. We would expect small perturbation do not 
change class of the image. But this not true, these examples are called adversarial examples. We can generate adversarial examples by applying perturbation to maximize the prediction error.   
    


















## References ##

[^SzZaSuBrErGoFe2014]: Szegedy et al, 2014.Intriguing properties of neural networks. Available at: [https://arxiv.org/abs/1312.6199](https://arxiv.org/abs/1312.6199)

[^GiDoDaMA2013]: Ross et al, 2013. Rich feature hierarchies for accurate object detection and semantic segmentation. Available at: [http://arxiv.org/abs/1311.2524](http://arxiv.org/abs/1311.2524)

[^GoLeeLeSaNg2009]: Goodfellow et al, 2009. Measuring Invariances in Deep Networks. Available at: [http://papers.nips.cc/paper/3790-measuring-invariances-in-deep-networks.pdf](http://papers.nips.cc/paper/3790-measuring-invariances-in-deep-networks.pdf)

[^ZeFe2013]: Matthew et al, 2013. Visualizing and Understanding Convolutional Networks. Available at : [http://arxiv.org/abs/1311.2901](http://arxiv.org/abs/1311.2901) 

[^MiChCoDe2013]: Mikolov et al, 2013. Efficient estimation of word representations in vector space. Available at: [https://arxiv.org/abs/1301.3781](https://arxiv.org/abs/1301.3781)
}
