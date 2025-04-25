---
layout: post
title: Active Learning
---

## A tool for training ML models using less labeled data

Machine Learning (ML) has revolutionized the world in the past decades, benefiting from the increasing computational power in order to solve problems unsolvable not so long ago. However, despite its potential, many technical and practical challenges face those who work with ML. 

In particular, the necessary effort to produce the data on which the models are trained is becoming an intricate issue. With the complexity and size of the problems we are currently trying to solve, labeling the necessary data becomes a laborious and expensive task since much of the process has to be done manually. This question is even more critical when dealing with problems which require a high level of specialization. As an example, for detecting diseases from MRI scans using deep neural networks, thousands of examples must be classified by doctors experienced in diagnosing such images. With the view of this, developing methods to improve the dataset labeling workflow efficiency becomes critical. 

One effective option would be to partially or completely automate the labeling process. However, when considering complex and high dimensional data, not much in the labeling workflow can be automated (if you have a system able to automatically label your data, the problem is solved and there is no need to train a ML model whatsoever).

Another approach consists of somehow decreasing the dataset size. Although it is known that complex problems require large datasets, it is also a fact that not all the examples are so meaningful for the learning model. Therefore, choosing only the most informative examples for labeling allows us to achieve a good model while learning from fewer examples.

Active Learning is a framework that relies on this idea, where the model chooses the most informative unlabeled samples and then asks an external specialist (commonly called oracle) to label only these examples. Active Learning is classified by some authors as a semi-supervised learning framework, since it uses both labeled and unlabeled data while training the model. The interaction with the oracle is iterative, with new unlabeled examples being given to the oracle in each iteration. 

In [1] Burr Settles presents an extensive survey regarding Active Learning. He summarizes the concept behind it in an intuitive way:

> “The key hypothesis is that, if the learning algorithm is allowed to choose the data from which it learns —to be “curious,” if you will— it will perform better with less training. “ [1]

Two interesting Active Learning applications will be shown next.

### Active Learning in sentiment analysis

Sentiment analysis is an important application in the Natural Language Processing (NLP) field. It focuses on classifying a text in terms of the attitude expressed by the author. Despite looking like a simple task, it is generally something really difficult for ML models to deal with since subtle changes in the text can result in a completely different meaning for the reader.

In [2], the authors applied Active Learning in a sentiment analysis problem, proposing an algorithm called Active Deep Networks (ADN), a combination of Active Learning and deep neural networks. The results are really interesting since this method not only used fewer examples to learn from, but it outperformed other well-known models considered state-of-the-art at the time.

> “[…] ADN can make the right decision about which training data should be labeled based on existing unlabeled and labeled data. By using unsupervised and supervised learning iteratively, ADN can choose the proper training data to be labeled and train the deep architecture at the same time. Active learning for sentiment analysis”

### Active Deep Learning for Classification of Hyperspectral Images

Hyperspectral image is a representation of spectral responses across the electromagnetic spectrum. It is composed of several spatial images representing the measurements at a particular electromagnetic wavelength and is used in different applications, from astronomy to biomedicine. Due to the great extent of different wavelengths usually represented, the data becomes high dimensional. As an example, a single image captured by NASA AVIRIS (Airborne Visible/Infrared Imaging Spectrometer) can contain up to 140MB of raw data [3].

This is a great application for Active Learning, since classifying such images is a long task that requires deep knowledge about the application. In [4], the authors proposed an Active Learning algorithm called WI-DL, using a Deep Belief Network with 4 hidden layers. This model achieved an accuracy close to 95% with only 5000 labeled samples, showing that it is possible to train an accurate model while using fewer data by actively selecting relevant training samples.

### Conclusion

Producing good quality datasets for complex and high-dimensional problems is already a challenge for Machine Learning applications. Here, a framework called Active Learning was presented alongside two pertinent applications. Despite allowing to decrease the number of labeled examples, Active Learning is not a definitive solution for the given problem, since a human being responsible for manual labeling is still needed. It is also important to remark that the oracle has to be included in the training loop, waiting for the algorithm to provide new unlabeled samples at each new iteration. This is a workflow that may be inconvenient or of difficult implementation depending on the application.

### References 

[1] Settles, Burr. Active learning literature survey. University of Wisconsin-Madison Department of Computer Sciences, 2009.

[2] Zhou, Shusen, Qingcai Chen, and Xiaolong Wang. "Active deep networks for semi-supervised sentiment classification." Proceedings of the 23rd International Conference on Computational Linguistics: Posters. Association for Computational Linguistics, 2010. 

[3] Cheung, Ngai-Man, and Antonio Ortega. "Distributed compression of hyperspectral imagery." Distributed Source Coding (2009): 269-292.

[4] Liu, Peng, Hui Zhang, and Kie B. Eom. "Active deep learning for classification of hyperspectral images." IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing 10.2 (2016): 712-724.
