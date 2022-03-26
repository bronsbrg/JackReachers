[//]: # (Image References)

[image1]: https://raw.githubusercontent.com/bronsbrg/JackReachers/main/training_early.gif "Training Early"
[image2]: https://raw.githubusercontent.com/bronsbrg/JackReachers/main/training_late.gif "Training Late"

# Project 2: Continuous Control

### Introduction

This project requires the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment, which trains 20 arms to follow goal locations.

Early in the training process, the arms looks like this:
![Training Early][image1]

When the training process is nearly complete, they look like this:
![Training Late][image2]

In this environment, double-jointed arms can move to target locations. A reward of +0.1 is provided for each step that the agents' hands are in the goal locations. Thus, the goal of the agents is to maintain their positions at the target locations for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of each arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector is a number between -1 and 1.

### Distributed Training

For this project, I used Udacity's second version of the Unity environment, containing 20 identical agents, each with its own copy of the environment.

The barrier for solving this second version of the environment is slightly different, to take into account the presence of many agents. In particular, the agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
- This yields an **average score** for each episode (where the average is over all 20 agents).

The environment is considered solved when the average (over 100 episodes) of those average scores is at least +30.

### How to run and train

1. Download the environment from one of the links below. You need only select the environment that matches your operating system:

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the cloned folder of this repository, and unzip (or decompress) the file. The code currently expects the executable at `./Reacher_Windows_x86_64/Reacher.exe`.

### Instructions

Follow the instructions in `Continuous_Control.ipynb` to get started with training the agent!
