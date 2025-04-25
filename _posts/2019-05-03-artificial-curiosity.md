---
layout: post
title: Artificial Curiosity - How can artificial intelligence become curious?
---

Many people get interested into Machine Learning (or Artificial Intelligence as a more general field of study) by some extraordinary plots presented in books, movies and tv series. It is indeed very fascinating to study and implement algorithms that can specialize and outperform humans in solving many tasks. However, when it comes to the majority of the problems we usually deal with, it feels we are far away from the intelligent entities present in Azimov stories and Terminator movies. In the reality there is no publicly available information about an artificial intelligence created with the necessary complexity to get conscious and able to willingly start doing things on its own.

So, what is missing for us to reach that level of artificial intelligence? The answer is not simple, but I would say most of machine learning approaches are too dependent on the human supervision. For supervised learning big datasets with manual classified examples must be provided whereas in reinforcement learning the agent is highly dependent on the reward function. In that sense those algorithms are strongly tied to the tasks they were programmed to solve.

But how to make a system able to learn without explicitly programming it? One alternative is to make this system curious about novel things.

**What is artificial curiosity?**

In this context, curiosity is framed as the interest of an agent to learn unknown regularities. The idea is to reward the system if it finds something unexpected. On the other hand, such agent should get bored when facing patterns that are either predictable or inherently unpredictable. The second statement may sound weird, but it is not reasonable for the agent to spend lots of time trying to understand how some random event works. For example, static noise coming from a radio represents a continuous stream of unknown data. However, it is not possible to extract meaningful information out of it.

The term artificial curiosity stands for algorithms that implement this mechanism. A curiosity reward is added to the agent learning process, proportional to the difference between the expected result from a given input and the actual output. If this difference is big, it means the model the agent “created” about the surrounding world was not comprising this particular occurrence. After receiving the curiosity reward, the agent is stimulated to learn more about what happened. However, the more is learned about it, smaller will be the expected/real output difference (and the received reward), leading to a decrease in the interest.

This curiosity paradigm makes much sense when we put the human behavior in perspective. When faced by unknown, yet learnable situations, we have an inner motivation to understand it better. However, when solving some task that is too simple, or that have been already solved many times (e.g. repetitive routines), we fell bored and curiosity is not enough motivation to keep working on it.

**How can artificial curiosity help to solve problems?**

Artificial curiosity is a powerful tool for exploration. This is specially important in order to solve optimization problems. In such problems, it is sometimes difficult to avoid getting stuck into a sub-optimal solution. In Reinforcement Learning this is usually done by forcing the agent to explore in the beginning. Defining a good exploration/exploitation ratio is not easy, though.

For curious agents, exploration occurs naturally. The motivation that pushes them forward is intrinsic: the curiosity reward acts like an inner stimulus for finding something new. This can be easily combined with the task the agent is actually trying to solve. The result is an agent influenced by two distinct motivations: the extrinsic (for being rewarded when learning how to solve the task), and the intrinsic  (reward that is earned for discovering new things).

As an example, OpenAI was only able to develop an artificial intelligence that exceeds average human performance on Montezuma’s Revenge after using a curiosity-driven agent [1]. This is an Atari game with particular mechanics that make it really difficult to be learned by most machine learning methods.

Even not being able to develop artificial systems able to fulfill paradigms such as continuous learning, artificial consciousness and self-awareness, many methods that can help us to get there are already available.

[1] Burda, Y., Edwards, H., Storkey, A., & Klimov, O. (2018). Exploration by random network distillation.Â arXiv preprint arXiv:1810.12894.
