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
Because of the huge continuous state and action space the training of the neural networks with a fast GPU is inevitable. 
The following pseudocode tries to show how the Algorithm by (Lillicrap et al., 2015) works.

In order to define a reward we define this simple equation:

![alt-text-1](http://mathurl.com/ybfraejf.png)

Wherby delta is the distance to the red object at time t. We are trying

The following picture shows the learned gait pattern when the robot is walking straightforward.
![alt-text-1](robot/diagram.png)
As you can see it follows a natural trot gait by always lifting the diagonally opposite leg. 
# References:
[Continuous control with deep reinforcement learning](https://arxiv.org/abs/1509.02971) 

[Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602)

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/WHAAAT/DDPG-Gait/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
