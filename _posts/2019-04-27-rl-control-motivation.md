---
layout: post
title: Reinforcement Learning - Motivation for a Control Engineer
---

Having a strong control theory background, I was never really impressed by usual machine learning applications. Off course I understand the importance of supervised and unsupervised algorithms, and how machine learning has been used for years to pump up the technological development (and society I would say). However, I can not find most of the introductory examples appealing enough (training a neural network for several hours in order to classify cats and dogs is not something for me).

What changed everything was when I started studying more deeply the Reinforcement Learning theory. The concepts match so well with the kind of problem I used to study in control theory classes that the first thing I tried was basically to set and agent to learn how to control some dynamical system. In fact its origin is in the control optimization theory, with the Bellman equation as the beginning of everything.

So here is the RL main idea: An agent must learn how to behave in the environment he is located at in order to optimize the long term reward received from the environment. Some points that make me like RL so much:

+ RL framework basically describes a closed loop system. The agent (controller) performs actions (control signal), observes the environment state (system output) and receives a reward that has to be optimized (similar to MPC cost functions).
+ Not necessarily the agent must have previous knowledge about the environment. Those algorithms are known as model-free methods.
+ The learning basically occur by trial-and-error. This mimics really well the learning process of a human, for example.
+ Also, being an optimization problem, it is possible to obtain nice convergence properties for many algorithms.
