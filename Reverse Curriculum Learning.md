## Reverse Curriculum Generation for Reinforcement Learning

###### Carlos Florensa, Markus Wulfmeier, David Held, Michael Zhang, Pieter Abbeel 

This work is motivated by the idea of learning using an automatic curriculum, so that the agent starts by solving easy tasks first, shifting slowly to more challenging tasks and finally achieving the difficulty level of the original task. This is what is meant by following a reverse curriculum. The authors suggest slowly expanding the state initialization distribution to finally achieve the original distribution. 

The agent starts in the goal state after which nearby start states are sampled by doing random walks. These candidate sampled start states are then used to run trajectory samples, collect total rewards and update the current policy using any on policy method. If the total reward from a candidate start state is between a minimum and maximum reward limit, such a state is appended to the start states list. Selecting such a state basically means that it is a good start state ie. the current policy solves the task most of the time starting from such a state. This is continued till the start state distribution resembles the original state distribution.

Although such a technique can be added to any on policy method, one major drawback is that as it is, it can only solve for tasks with a fixed goal state. It can be argued that for many tasks the goal might remain fixed, however fixing the goal state as well adds an unnecessary constraint on the goal being reached only through a single state. For example, such a method will fail for the simple reacher task as the target always keeps changing. Therefore, the sampled start states for one goal state will  be very far from a different goal state, making the problem difficult.



