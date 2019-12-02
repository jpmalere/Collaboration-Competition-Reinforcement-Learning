# Readme

##  Collaboration and Competition - Deep Reinforcement Learning

### Udacity - Nanodegree Program

### 1. Introduction

The code contained in the ```Tennis.ipynb``` file trains two agents representing tennis players. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.

The observation space consists of three sets of 8 variables corresponding to the position and velocity of the ball and racket. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The training is performed on ```n_episodes = 5000``` and is interrupted if the mean average score is equal or greater than 0.5 

### 2. Getting Started

The following packages are necessary to run the code:
- ```UnityEnvironment```. The executable file of the environment is available at (for Windows x64): https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip.
- ```gym```
- ```matplotlib```
- ```numpy```
- ```torch```
- ```collections```

The following files are necessary to run the code:
- ```model.py```
- ```ddpg_agent.py```
-```ReplayBuffer.py```

The following Python version was used:
-```Python 3.6```

### 3. Instructions

In order to run the code, execute the steps provided on the ```Tennis.ipynb``` notebook

### 4. More about the method

The ```Report.md``` contains more information about the deep deterministic policy gradient method.

