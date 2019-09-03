---
layout: post
title: Revisiting previous experiences can help artificial systems to learn faster
---

## Prioritized Experience Replay proposes mixing new and old experiences in order to speed up learning

Reinforcement Learning (RL) is a framework with a great potential to be the basis for the "next level" artificial intelligence, what is so called human-level AI. In [1], Nils J. Nilsson describes this next level as:

> "[...] general-purpose, educable systems that can learn and be taught to perform any of the thousands of jobs that humans can perform."

The reason for RL being a good candidate to achieve such goal is simple: its reward-based learning mechanism is close to the mechanism used by the human brain for learning things. Basically, RL agents learn -by trial and error- how to behave in order to maximize the received reward (one can think of a dog receiving treats from its owner/trainer).

Despite its potential, classical RL approaches are limited and, even being able to solve numerous complex problems, are far from achieving this general-porpuse long-term goal. In the search for improvement, many researchers propose biologicaly-inspired methods that extend RL.

The method described below consists in using stored memories in a efficient way to speed up learning.

### Memories help us to learn

Studies in the neuroscience field evidentiate that memories containing prior episodes of experiences are replayed in the hippocampus of rodents, an occurrence observed in different levels of brain activity.

The results also show that experiences which resulted in some level of reward are more frequently replayed. Even more interesting is that the sense of novelty is also associated with the probability of replaying some experience, as described in [2]:

> "[...] we have identified dopaminergic release during, for example, novel environments and reward-driven spatial tasks, as being important for biasing the content of subsequently replaying trajectories, potentially to strengthen new place cell assemblies and place-reward associations."

This basically means that learning also happens by revisiting old experiences and some mechanism is used in order to choose the better experiences for optimizing the learning process, e.g. choosing experiences that present some degree of novelty or are associated with received rewards.

### Experience Replay

To mimic this experience mechanism present in biological systems, the method called Experience Replay was proposed in [3], alongside with learning action models for planning, and teaching. These three extension methods are suggested to speed up learning of both AHC (adaptive heuristic critic) and Q-learning algorithms. The motivation to apply Experience Replay is:

> "The basic AHC- and Q-learning algorithms [...] are inefficient in that experiences obtained by trial-and-error are utilized to adjust the networks only once and then thrown away. This is wasteful, since some experiences may be rare and some (such as those involving damages) costly to obtain. Experiences should be reused in an effective way."

The assumption is that storing and processing previous experiences is "cheaper" than interacting with the environment.

Experience is defined as a quadruple, $(s, a, s', r)$, meaning that the execution of an action $a$ in a state $s$ results in a new state $s'$ and reward $r$. While interacting with the environment, the agent remembers (by sampling) its past experinces in order to learn more from them.

Two main problems that are mittigaded by applying Experience Replay are:

1. Strongly correlated updates: popular stochastic gradient-based algorithms assume that the variables are i.i.d. (independent and identically distributed). However, i.i.d. assumption does not fit very well with Markov chains (sequence of states). When mixing online experiences with stored ones, it is possible to "break" the correlation between consecutive states.
2. Forgetting important experiences: as aforementioned, some situations can be rarely experienced and classic RL algorithms just throw away the old experiece in the next iteration.

### Prioritized Experience Replay (PER)

The introduction of Experience Replay was already a big improvement for RL. However, biological evidences support that some experiences are more frequently replayed than others.

In [4], PER, an improved version of the Experience Replay method, is presented. The main idea is to use TD error as a metric to define the probability of replaying some experience.

TD error basically represents the prediction error (the difference between the model output and the received reward) for a given state and is frequently used as a prioritization mechanism (e.g. artificial curiosity [5] and feature selection [6]).

The motivation is that, similar to biological systems, experiences from which the learning system can learn more (i.e. states associated with large TD errors) should be replayed more frequently, speeding up the learning process.

The results in [4] showed that applying PER on an agent supposed to learn how to play Atari games allowed to speed up learning by a factor of 2.

### Not only RL can benefit from this

Another interesting result given in [4] is that this same method can be applied to improve supervised learning methods. The method, renamed as Prioritized Sampling, consists in using more frequently the examples that represent a higher error for focusing the optimization (learning) process:

> "The  analogous  approach  to  prioritized  replay  in  the  contextof supervised learning is to sample non-uniformly from the dataset, each sample using a priority based on  its  last-seen error. This can help focus  the learning on those  samples that can still  be learned from,  devoting additional resources to the (hard) boundary cases"

That method can be beneficial specially when dealing with imbalanced datasets, because examples containing less-represented classes will have a higher sampling priority, provided they still result in a large prediction error.

When applied to a class-imbalanced variant of the classical MNIST digit classification problem, prioritized sampling is proven to result in an increase of performance in terms of generalization and in terms of learning speed.

### References

[1] Nilsson, Nils J. "Human-level artificial intelligence? Be serious!." AI magazine 26.4 (2005): 68-68.

[2] Atherton, Laura A., David Dupret, and Jack R. Mellor. "Memory trace replay: the shaping of memory consolidation by neuromodulation." Trends in neurosciences 38.9 (2015): 560-570.

[3] Lin, Long-Ji. "Self-improving reactive agents based on reinforcement learning, planning and teaching." Machine learning 8.3-4 (1992): 293-321.

[4] Schaul, Tom, et al. "Prioritized experience replay." arXiv preprint arXiv:1511.05952 (2015).

[5] "How can Artificial Intelligence become curious?"" https://towardsdatascience.com/artificial-curiosity-e1837e4ca2c9

[6] Sun, Yi, et al. "Incremental Basis Construction from Temporal Difference Error." ICML. 2011.
