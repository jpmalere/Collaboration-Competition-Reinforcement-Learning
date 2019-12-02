# Report 

## Project - Collaboration and Competition

### Deep Reinforcement Learning - Udacity Nanodegree program

### 1. Introduction

The ```Tennis.ipynb``` notebook implements two agents by the Actor-Critic method. One neural network (critic) represents the action-value function (Q) and other neural network estimates agent actions given its associated states (actor). The implementation uses the Unity Tennis environment.

For each episode the match continues until the ball hits the ground or is out of boundary. For each step, the agent learns and updates the neural netowrks weights.

The Multi-Agent Actor-Critic method can be found at Reference [1] - Algorithm 1 description. 

### 2. Implementation

The ```Tennis.ipynb``` implements the Multi-Agent Actor-Critic method for the Tennis Unity environment. 

The agent implementation is performed with three auxiliary files:
- ```model.py```: contains the classes Actor and Critic where the neural networks are implemented. The Actor neural network consists of three layers with 200, 150 and 2 neurons for the first, second and third layers respectively. The first and second layers are composed of linear functions with relu activations and a tanh activation for the last layer. The Critic neural network consists of three layers with 200, 150 and 1 neurons for the first, second and third layers respectively. The first and second layers are composed of linear functions with relu activations and no activation for the last layer.
- ```ddpg_agent.py```: implements the class Agent with the ```step```, ```act```, ```learn```,  ```soft_update``` and ```reset``` methods. The ```step``` method evokes the ```learn``` function when necessary or just save the experiences in a buffer. The ```learn``` function updates the neural networks weights in order to minimize the actor-critic loss functions. The ```act``` function chooses the action based on the neural network . The ```soft_update```function updates the neural network weights and the ```reset``` function resets the internal state.
- ```ReplayBuffer.py```: provides the buffer addition and sampling functions. 

There is a shared buffer between the agents that stores experiences with all states and actions. This shared buffer is sampled by the two agents in order to train the neural networks.

The criteria for choosing the number of layers and the number of neurons was from less complex to more complex models. The initial considered number of layers was three and the first two layers number of neurons was 150 and 100. This first configuration was slow to increase the score and after 1800 episodes the averaged score was 0. The number of neurons was increased to 200 and 150 on the first two layers and the stopping criteria was reached after 2100 episodes. More neurons were added to evaluate the learning speed, but with 300 and 200 neurons on the first two layers the average score was only 0.1 after 1800 episodes. The 200, 150 neurons configuration was kept for both networks (actor and critic). 
The batch size was increased (from from 128 to 250) to improve the agent score for this configuration.

The graph below shows the score per episode during the training time.
![result](https://user-images.githubusercontent.com/8217602/69991960-6cb60f00-1527-11ea-82f9-39ed22563371.png)

### 3. Discussion and future works

The Multi-Agent Actor-Critic method was able to train two agents to play tennis on a simulated environment and fulfilled the specified requirement (average score equal or greater than 0.5 for 100 episodes). For future works the following aspects could be tested for agent performance improvement:
- Different loss functions;
- Different optimizers for hyperparameters update; 
- Other variants of the Actor-Critic method;
- Other supervised learning algorithms.

### 4. References¶

[1] Loew R., Wu Y., Tamar A., Harb J., et al, "Multi-Agent Actor-Critic for Mixed
Cooperative-Competitive Environments".
