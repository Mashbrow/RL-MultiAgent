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

Follow the instructions on this [repo](https://github.com/udacity/deep-reinforcement-learning#dependencies) to install all the dependencies Note that if you are running the code on Windows you might have trouble installing the box2d environnement you can solve this issue by using `pip install box2d` instead of `pip install gym[box2d]`.

Then follow the instructions on this [section](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet).

## Method

Code was taken from my previous project on the repository [RL-Reacher-Continous-Control](https://github.com/Mashbrow/RL-Reacher-Continuous-Control) and adapted so that it can resolve the task.

I started by changing things in the architecture model itself. I used only one neural network for the actor and one neural network for the critic. Hence each agent is training the same models. Then I tried exploring various hyperparameters that led me to observe that training was unstable. It led me to add Batchnorm and to modify ReLU functions by Leaky ReLU to the models and to reduce the noise to finally resolve the task.

## What contains this repository ? 

- A notebook containing the code to train an agent to solve the task.
- A .py file containing the architecture of MADDPG Agent.
- A .py file containing the architecture model.
- Two .pth files containing the weights of the Actor and the Critic models.
- A report describing the architecture and the hyperparameters used to solve the task as well as my approach to solve the task.
