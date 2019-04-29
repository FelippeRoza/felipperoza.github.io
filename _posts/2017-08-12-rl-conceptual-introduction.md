---
layout: post
title: Reinforcement Learning - A Conceptual Introduction
---

As described in a previous post, Reinforcement Learning is the topic in Artificial Intelligence that interests me the most. Even not being a computer scientist, it matches really well with my background, and the concept itself is quite fascinating. In this post I will try to give a nice initial picture for those who want to know more about RL.

### So, what is reinforcement learning?

Conceptually, RL is a framework that describes systems (here called agents) that are able to learn how to interact with the surrounding environment only by means of gathered experience. After each action (or interaction), the agent earns some reward, a feedback from the environment that quantify the quality of that given action.

Humans learn by the same principle. Think about a baby walking around. For him, everything is new. How can a baby know that grabbing something hot is dangerous? Of course, after touching this hot object he can get a painful burn. With this bad reward (actually, a punishment) the baby will learn that it is good to avoid everything too hot.

It is important to point out that the terms agent and environment must be interpreted in a broader sense. It is easier to visualize the agent as something like a robot and the environment as the place where it is situated in. This is a right analogy, however it can be much more. I like to think that the agent is like a controller in a closed loop system: It is basically an algorithm responsible for making decisions. The environment can be anything that the agent interacts with.


### Lets try a simple example

For a better understanding I will use a simple example here. Imagine a wheeled robot inside of a maze, trying to learn how to reach a goal marker. However, some obstacles are in its way. The aim is that the agent learn how to reach the goal without crashing into the obstacles. So, lets highlight the main components that compose this RL problem:

* Agent: It is the decision making system. The robot, in our example.
* Environment: A system which the agent interacts with. The maze.
* State: For the agent to choose how to behave, it is necessary to estimate the environment state. For each state, it should exist an optimal action for the agent to choose. It can be the robot position, or some obstacle detected by the sensors.
* Action: It is how the agent interact with the environment. Usually there is a finite number of actions that the agent is able to perform. In our example it is the direction that the robot should move to.
* Reward: It is the feedback that allows the agent to know if the action was good or not. A bad reward (it can be a low or negative value) can be also interpreted as a punishment. The main goal of RL algorithms is to maximize the long-term reward. If the robot achieves the goal mark, a big reward should be given. However, if it crashes into an obstacle a punishment should be given instead.
* Episode: Most of the RL problems are episodic. The meaning is that it has to exist some event that terminate the episode execution. In our example the episode should finish when the robot reaches the goal or if some time limit is exceeded (to avoid the robot to stay still forever).

Usually, it is supposed that the agent has no previous knowledge about the environment. Therefore, in the beginning actions will be chosen randomly. For each wrong decision the agent will be punished (for example, crashing into an obstacle). In the other hand, good decisions will be rewarded. The learning happens by the agent figuring out how to avoid getting into situations where punishment may occur and choosing actions that will allow the agent to find the goal.

The reward accumulated in each episode is expected to increase and can be used to estimate the agent’s learning rate. After many episodes, the robot should be able to know how to behave in order to find the goal marker while avoiding any occasional obstacle with no previous information about the environment. Of course there are many other things to be considered, but let’s keep it simple for this post.
