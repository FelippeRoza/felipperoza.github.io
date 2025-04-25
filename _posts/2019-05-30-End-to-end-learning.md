---
layout: post
title: End-to-end learning, the (almost) every purpose ML method
---

##### Can E2E be used to solve every Machine Learning problem?

One of the most important skills for those who work with Machine Learning is to know which method is the right choice for a given problem. Some choices are trivial (e.g. supervised or unsupervised, regression or classification), because they are related to the problem formulation itself. However, even after defining what you are trying to solve, there are usually a myriad of algorithms that can be used.

For example, imagine you want to develop a system able to predict a categorical variable. The solve this problem either Classification Tree, K-nearest neighbors or even Artificial Neural Networks can be used. Of course, there is a reason for many algorithms to exist, even when they solve similar problems: each one has its particularities from which we can benefit.

What makes the task even harder is that for solving some problems, like speech recognition and autonomous driving, an architecture consisting of many layers is necessary (e.g. preprocessing, feature extraction, optimization, prediction, decision making). For each layer, many different algorithms may be used.
The issue is: for achieving better results, changes on the inner layers and its corresponding algorithms have to be applied. However, as each layer is responsible to solve particular tasks, it becomes really difficult to determine how such changes will affect the system as a whole.

End-to-end (E2E) learning refers to training a possibly complex learning system represented by a single model (specifically a Deep Neural Network) that represents the complete target system, bypassing the intermediate layers usually present in traditional pipeline designs.

## End-to-end learning

End-to-end learning is a hot topic in the Deep Learning field for taking advantage of Deep Neural Network’s (DNNs) structure, composed by several layers, in order to solve complex problems. Similar to the human brain, each DNN layer (or group of layers) is able to specialize to perform intermediate tasks necessary for such problems. Tobias Glasmachers evidenciate how E2E is framed in the Deep Learning context [1]:

`“This elegant although straightforward and somewhat brute-force technique [E2E] has been popularized in the context of deep learning. It is a seemingly natural consequence of deep neural architectures blurring the classic boundaries between learning machine and other processing components by casting a possibly complex processing pipeline into the coherent and flexible modeling language of neural networks. “ `

That alternative approach has been successfully applied to solve many complex problems. Bellow you can find how E2E is applied for Speech Recognition and Autonomous Driving problems.

## Speech Recognition
￼
The traditional approach design for a spoken language understanding system is a pipeline structure with a number of different components, exemplified by the following sequence:

* Audio (input) -> feature extraction -> phoneme detection -> word composition -> text transcript (output).

A clear limitation of this pipelined architecture is that each module has to be optimized separately under different criteria. The E2E approach consists in replacing the aforementioned chain for a single Neural Network, allowing to use a single optimization criterion for enhancing the system:

* Audio (input) —> (NN) —> transcript (output)

Mike Lewis et al. introduce an E2E learning approach for natural language negotiations [2]. The resulting system is a dialogue agent based on a single Neural Network that is able to negotiate in order to achieve an agreement. This was done by training the NN using data from a large dataset of human-human negotiation records containing a variety of different negotiation tactics.

Another benefit of the E2E approach is that it is possible to design a model that performs really well without a deep knowledge about the problem, despite its complexity. Ronan Collobert et al. explain how an unified Neural Network architecture and an appropriate learning algorithm for Natural Language Processing (NLP) can be used in order to avoid task-specific engineering and lots of prior knowledge [3]:

`“[...] we try to excel on multiple benchmarks while avoiding task-specific engineering. Instead we use a single learning system able to discover adequate internal representations. [...] Our desire to avoid task-specific engineered features prevented us from using a large body of linguistic knowledge. Instead we reach good performance levels in most of the tasks by transferring intermediate representations discovered on large unlabeled data sets. We call this approach “almost from scratch” to emphasize the reduced (but still important) reliance on a priori NLP knowledge.” `

## Autonomous driving

Autonomous driving systems can be classified as a remarkable example of complex systems composed by many layers. Following the architecture proposed by Alexandru Serban et al., we can design an autonomous driving system using 5 different layers [4]:
￼
The input data comes from several sensors (cameras, LIDAR, radars, etc.) that is processed in the sensor fusion layer to extract the relevant features (e.g. object detection). With all the data processed and the relevant features extracted, a “world model” is created in the second layer. That model comprises the complete picture of the surrounding environment together with the vehicle internal state.

From this model the system must choose which decisions to make in the behavior layer. According to the vehicle’s goals, it raises multiple behavior options based on the system policy and selects the best one by applying some optimization criterion.

With the decisions taken the system determines the maneuvers the vehicle must execute in order to satisfy the chosen behavior in the planning layer and finally the control values are send to the actuator interface modules in theÂ vehicle control layer.
￼
In the paper “End to End Learning for Self-Driving Cars”, Mariusz Bojarski et al. propose an E2E system that is able to control an autonomous car directly from the pixels provided by the embedded cameras [5]. The system was able to learn internal representations of intermediate steps, such as detecting useful road features, with only the human steering angle as the training signal. The usage of Convolutional Neural Networks (CNNs) plays an important role in the proposed system for its capacity of extracting useful features from image data:

`"The breakthrough of CNNs is that features are learned automatically from training examples. The CNN approach is especially powerful in image recognition tasks be- cause the convolution operation captures the 2D nature of images." `

The designed CNN goes beyond pattern recognition in order to learn the entire processing pipeline needed to steer an automobile. The network architecture consists of 9 layers, including a normalization layer, 5 convolutional layers and 3 fully connected layers. The system was trained using real driving recorded data collected in central New Jersey, Illinois, Michigan, Pennsylvania, and New York. The following figure shows the block diagram of the training system design:
￼
With approximately 72 hours of driving data, the system was able to learn how to steer the car in different road types and weather conditions:

`“A small amount of training data from less than a hundred hours of driving was sufficient to train the car to operate in diverse conditions, on highways, local and residential roads in sunny, cloudy, and rainy conditions. The CNN is able to learn meaningful road features from a very sparse training signal (steering alone). The system learns for example to detect the outline of a road without the need of explicit labels during training.” `

## Limitations of E2E

If using a single DNN between input and output works for the aforementioned examples, why not use it as a general approach for solving every Machine Learning problem?

Many are the reasons that make E2E an infeasible option in different cases:

* A huge amount of data is necessary: The incorporation of some prior knowledge into the training is considered a key element that will allow an increase of performance in many applications. For E2E learning not integrating this prior knowledge, more training examples must be provided.
* Difficult to improve or modify the system: If some structural change must be applied (e.g. increasing the input dimensions by adding more features) the old model has no use and the hole DNN has to be replaced and trained all over again.
* Highly efficient available modules cannot be used: Many techniques are really efficient to solve some tasks. As an example, state-of-the-art object recognition systems are largely distributed, but as soon as it is integrated to an E2E system, it cannot be considered E2E anymore.
* Difficult to validate: If a high level of validation is necessary, E2E may become infeasible. Due to the complex architecture, the potential number of input/output pairs can be big enough to make the validation impossible. This is specially important for some sectors like the automotive industry.

On top of these issues, E2E may not work for some applications, as shown in [1]:

` “We have demonstrated that end-to-end learning can be very inefficient for training neural network models composed of multiple non-trivial modules. End-to-end learning can even break down entirely; in the worst case none of the modules manages to learn. In contrast, each module is able to learn if the other modules are already trained and their weights frozen. This suggests that training of complex learning machines should proceed in a structured manner, training simple modules first and independent of the rest of the network.” `

## Conclusion

End-to-end is indisputably a great tool for solving elaborate tasks. The idea of using a single model that can specialize to predict the outputs directly from the inputs allows the development of otherwise extremely complex systems that can be considered the state-of-the-art. However, every enhancement comes with a price: while consecrated in the academic field, the industry is still reluctant to use E2E to solve its problems due to the need of large amount of training data and the difficulty of validation.

## References

[1] Glasmachers, Tobias. "Limits of end-to-end learning." arXiv preprint arXiv:1704.08305 (2017).

[2] Lewis, Mike, et al. "Deal or no deal? end-to-end learning for negotiation dialogues." arXiv preprint arXiv:1706.05125(2017).

[3] Collobert, Ronan, et al. "Natural language processing (almost) from scratch." Journal of machine learning research 12.Aug (2011): 2493–2537.

[4] Serban, Alexandru Constantin, Erik Poll, and Joost Visser. "A Standard Driven Software Architecture for Fully Autonomous Vehicles." 2018 IEEE International Conference on Software Architecture Companion (ICSA-C). IEEE, 2018.

[5] Bojarski, Mariusz, et al. "End to end learning for self-driving cars." arXiv preprint arXiv:1604.07316 (2016).
