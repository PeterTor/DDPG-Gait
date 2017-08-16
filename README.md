## Overview:
Recent publications from DeepMind like (Mnih et al., 2013) and (Lillicrap et al., 2015) in the fields of deep reinforcement learning opened a new field for robot locomotion. Reinforcement learning is a form of machine learning by trial & error. The Robot can evaluate the goodness of a state and is trying to advance in order to maximize its reward. By applying deep neural networks we try to generate more complex robot locomotion. 

This is a work in progress. 

## The quadrupedal robot
In order to research in the field of model free gait generation we created a quadrupedal robot. By using deep neural networks we try to generate stable walking gaits and even more complex moving tasks. <br>
<img src="robot/render.jpg" alt="hi" class="inline" width="49%"/>
<img src="robot/real_small.jpg" alt="hi" class="inline" width="49%"/> <br>
The robot has three degrees of freedom per leg and is also completely simulable in V-Rep.
We try to transfer the learned behavior later to the real robot that is shown in the picture above.

## A robot learns to walk 
The aim of this project is to teach an agent how to walk by itself. As you can see in the following video the trained agent always tries to follow the red dot.
<iframe width="560" height="315" src="https://www.youtube.com/embed/SIs9NMIHulU" frameborder="0" allowfullscreen></iframe>

The agents learns by using the deep deterministic policy gradient approach by (Lillicrap et al., 2015).
Our approach is called DDPG-Gait and consists of two neural networks.
The first neural network (the actor) generates the 12 continuous servo positions directly. It does so by getting judged from the second neural network (the critic), that evaluates the state and actions taken by trying to maximize its reward. 

### The model 
The following pseudocode tries to show the DDPG Algorithm by (Lillicrap et al., 2015). <br>
<img src="robot/pseudocode" alt="hi" class="inline" width="80%"/> <br>
The critic is training by minimizing the bellman equation in line 11. But in contrast to Deep-Q-Learning it only outpus only one Q-value per state-action pair.  
Because of the huge continuous state and action space the training of the neural networks with a fast GPU is inevitable. 

In order to define a reward we define this simple equation:<br>
![alt-text-1](http://mathurl.com/ybfraejf.png)<br>
Wherby delta is the distance to the red object at time t in the video. 

### Results
The following picture shows the learned gait pattern when the robot is walking straightforward.<br>
<img src="robot/diagram.png" alt="hi" class="inline" width="70%"/> <br>
As you can see it follows a natural trot gait by always lifting the diagonally opposite leg. 

# Acknowledgement
We gratefully acknowledge the support of NVIDIA Corporation with the donation of the Titan X Pascal GPU used for this research.
# References:
[Continuous control with deep reinforcement learning](https://arxiv.org/abs/1509.02971) 

[Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602)


