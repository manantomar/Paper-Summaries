# Paper Summary : Control of Memory, Active Perception and Action in Minecraft

> Abstract : This paper proposes three architectures based on DQN which target the problem of temporally related context retrieval. The training is done on three different maps in Minecraft each targetting a specific cognitive feature to be learned. 

## Concept details

  - Three networks are proposed, one with a memory block (MQN), one with a memory block and a recurrent layer (RMQN), and one with a feedback connection between the memory block and recurrent layer (FRMQN)
  - Baselines are DQN network and a DQN network with a recurrent layer (RDQN)

## Drawbacks / Questions
- For testing how well the network is able to generalize, a new set of maps is lerned upon. This seems more like transfer learning than using the new maps as a test set. The aim for transfer learning should be to learn faster, which is not the case here.
- While comparing the results, DQN is given a lower number of frames as input (because of a fixed DQN architecture while training). Although DQN performs decently well, it is clear that results should be compared while keeping most of the parameters constant across all architectures.
- Sequential learning task : In the paper, a positive reward is given if a sequence of tasks is achieved and negative if the order is changed. I believe that both cases should be given a positive reward as both tasks are completed irrespective of the order of completion. On top of that the correct sequence should get a higher reward than the incorrect sequence to really appreciate the task as a sequential learning task. In the current setting it can be considered more as a single task. 

