## Neural Network Dynamics for Model-Based Deep Reinforcement Learning with Model-Free Fine-Tuning

###### Anusha Nagabandi, Gregory Kahn, Ronald S. Fearing, Sergey Levine



This paper tries to achieve better convergence time while learning simple trajectory following tasks based on the Mujoco environment. This done by using a model based learning approach in which dynamics of the system are learned using a neural network. The controller is based on MPC (Model Predictive Control) and is thus acting and replanning after each step. Since learning a dynamics model requires state transition data which keeps changing with the policy (as the agent explores the unseen parts of the environment), the dynamics need to be learned iteratively. 

Therefore, we start with state transition data generated from random actions, and then alternate between learning the dynamics and updating the data by aggregating paths seen by the controller (MPC in this case) with the original dataset. Note that here the controller is just a direct shooting method based controller which simulates many trajectories based on random actions and the learned forward dynamics model and chooses the trajectory with the least cost. The first action of such an optimal trajectory is then applied, a new state is observed and a new action is planned following the same procedure.

The authors report that although such a model based controller helps in terms of sample efficiency, it indepedenty fails to learn a policy with high reward as compared to model free learning methods such as TRPO. To tackle this issue, a neural network policy is trained to immitate the actions of the MPC controller for a given state. Such a policy can then be used to warm start any model free learning method (TRPO in this case) to learn quickly as compared to when learning with just a model free method. 

Results for HalfCheetah, Ant, Hopper and Swimmer are reported.