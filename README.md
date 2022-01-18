# RL-MultiAgent

## Introduction

![Video of the environment](tennis_agent.gif "A video of mine showing agents playing tennis")

This project is part of the Udacity Nanodegree on Reinforcement Learning and aims at training two agents to play tennis.

Description:

- Reward: +0.1 if the agent hits the ball over the net, -0.01 if the agent lets the ball hit the ground or hits the ball out of bounds. The more the ball stays in game the more the reward.
- Observation Space: 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own local observation of the space
- Action State: 2-dimensional continuous space corresponding to jumping and movement toward (or away) from the net.

The task is episodic and considered solved when the agents get an average reward of +0.5 over 100 consecutives episodes.

## Installation

The instructions steps are taken from this [repo](https://github.com/udacity/deep-reinforcement-learning#dependencies) and this [section](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet).

1) Create (and activate) a new environment with Python 3.6.
- Linux/Mac
```shell
conda create --name drlnd python=3.6
source activate drlnd
```
- Windows
```shell
conda create --name drlnd python=3.6 
activate drlnd
```
2) If running in Windows, ensure you have the "Build Tools for Visual Studio 2019" installed from this [site](https://visualstudio.microsoft.com/downloads/). This [article](https://towardsdatascience.com/how-to-install-openai-gym-in-a-windows-environment-338969e24d30) may also be very helpful. This was confirmed to work in Windows 10 Home.
3) Follow the instructions in this repository to perform a minimal install of OpenAI gym and install classic control and box2d linked to gym (instructions are on the same page).
Note: You might have trouble installing box2d on Windows try `pip install box2d` inspite of `pip install gym[box2d]`
4) Execute those lines:
```shell
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
```
5) Create an IPython kernel for the drlnd environment.
```shell
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```
6) Download the Unity ML project environment
- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
- Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
7) Clone this repo and place the file in this GitHub Repository folder, and unzip (or decompress) the file.
8) You're ready to run the code ! :) 

## Running the Code

1) Launch Jupyter Notebook, be sure to select the drlnd kernel
2) Run the Notebook named Tennis.ipynb
3) You can then run each cells, the last one trains the agent.
4) If you want to check/tweak hyperparameters, you can head to utils/maddpg_agent.py
5) If you want to change the models architecture, you can find them in utils/model.py

## Method

Code was taken from my previous project on the repository [RL-Reacher-Continous-Control](https://github.com/Mashbrow/RL-Reacher-Continuous-Control) and adapted so that it can resolve the task.

I started by changing things in the architecture model itself. I used only one neural network for the actor and one neural network for the critic. Hence each agent is training the same models. Then I tried exploring various hyperparameters that led me to observe that training was unstable. It led me to add Batchnorm and to modify ReLU functions by Leaky ReLU to the models and to reduce the noise to finally resolve the task.

## Future Work

- Try different architectures and other hyperparameters to reach a better score in less time.
- Implement other algorithms used in multi-agent reinforcement learning.
- Stay in touch with the news in the reinforcement learning domain. 

## What contains this repository ? 

- A notebook containing the code to train an agent to solve the task.
- A .py file containing the architecture of MADDPG Agent.
- A .py file containing the architecture model.
- Two .pth files containing the weights of the Actor and the Critic models.
- A report describing the architecture and the hyperparameters used to solve the task as well as my approach to solve the task.
