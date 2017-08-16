## Overview:
Recent publications from DeepMind like (Mnih et al., 2013) and (Lillicrap et al., 2015) in the fields of deep reinforcement learning opened a new field for robot locomotion. Reinforcement learning is a form of machine learning by trial & error. The Robot can evaluate the goodness of a state and is trying to advance in order to maximize its reward. By applying deep neural networks we try to generate more complex robot locomotion. 

## quadrupedal robot
In order to research in the field of model free gait generation we created a quadrupedal robot. By using deep neural networks we try to generate stable walking gaits and even more complex moving tasks. 
<img src="robot/render.jpg" alt="hi" class="inline" width="70%"/>
The robot has three degrees of freedom per leg and is also completely simulable.
div class="image123">
    <div style="float:left;margin-right:5px;">
        <img src=""robot/render.jpg" height="200" width="200"  />
        <p style="text-align:center;">This is image 1</p>
    </div>
    <div style="float:left;margin-right:5px;">
        <img class="middle-img" src=""robot/render.jpg" height="200" width="200" />
        <p style="text-align:center;">This is image 2</p>
    </div>
    <div style="float:left;margin-right:5px;">
        <img src="robot/render.jpg" height="200" width="200" />
        <p style="text-align:center;">This is image 3</p>
    </div>
</div>

## a robot learns to walk 
The aim of this project is to teach an agent how to walk by itself. As you can see in the following video the agent always tries to follow the red dot.
<iframe width="560" height="315" src="https://www.youtube.com/embed/SIs9NMIHulU" frameborder="0" allowfullscreen></iframe>

In order to define a reward we define this simple equation:

![eq1](http://mathurl.com/ybfraejf.png)
Format: ![eq1](url)
wherby delta is the distance to the red object for time t. 


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
