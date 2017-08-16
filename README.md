**This is a work in progress project.**

## Overview:
Recent publications from DeepMind like (Mnih et al., 2013) and (Lillicrap et al., 2015) in the fields of deep reinforcement learning opened a new field for robot locomotion. Reinforcement learning is a form of machine learning by trial & error. The Robot can evaluate the goodness of a state and is trying to advance in order to maximize its reward. By applying deep neural networks we try to generate more complex robot locomotion. 
 

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

The critic is trained by minimizing the bellman equation in line 11. But in contrast to Deep-Q-Learning it only outpus only one Q-value per state-action pair. The actor on the other hand can be trained by directly applying the gradient in line 14. 
The equation was derived by (Silver et al., 2014). 

However state, reward, actions and the enviornment need to be defined:

1. **Environment_** The Enviornment is given by the Simulator. 
2. **Actions** the most straighforward approach is to define the actions by a 12 dimensional vector <br> 

<div align="center">
<img src="http://mathurl.com/yd8axedl.png" alt="hi" class="inline"/>
</div>
Wherby theta defines the servo angle at time t.
3. **State** the state can be defined as action taken in t-1. However in order to localize the agent relative to the red ball we added angle and distance relative to an abritary aim. 
4. **Reward** In order to get an reward we defined the moved distance from time t-1 to t. 
<div align="center">
<img src="http://mathurl.com/ybfraejf.png" alt="hi" class="inline"/>
</div>


### Results
The picture below shows the robot gait pattern. <br>
<div align="center">
<img src="robot/walking_straight.jpg" alt="hi" class="inline"/>
</div>
In order to visualize this pattern we plotted a gait diagram. Every dot in the following picture marks the time when the specific leg is lifted<br>
<div align="center">
<img src="robot/diagram.png" alt="hi" class="inline" width="70%"/>
</div>
As you can see it follows a natural trot gait by always lifting the diagonally opposite leg. 

# Acknowledgement
We gratefully acknowledge the support of NVIDIA Corporation with the donation of the Titan X Pascal GPU used for this research.
# References:
[Continuous control with deep reinforcement learning, (Lillicrap et al., 2015)](https://arxiv.org/abs/1509.02971) 

[Playing Atari with Deep Reinforcement Learning, (Mnih et al., 2013)](https://arxiv.org/abs/1312.5602)

[Deterministic Policy Gradient, (Silver et al. 2014)](http://www0.cs.ucl.ac.uk/staff/D.Silver/web/Applications_files/deterministic-policy-gradients.pdf) 
