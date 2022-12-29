# Multi-Agent-Final-Project
Multi Agent Final Project

Project Details
In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.
The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.
The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).
After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
This yields a single score for each episode.
The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

Multi-agent DDPG Actor-Critic Architecture
To achieve the goal score, a multi-agent DDPG (deep deterministic Policy Gradient) Actor-Critic architecture was chosen.
 
Similar to single-agent Actor Critic architecture, each agent has it’s own actor and critic network. The actor network takes in the current state of agent and output a recommended action for that agent. However the critic part is slightly different from ordinary single-agent DDPG. Here the critic network of each agent has full visibility on the environment. It not only takes in the observation and action of that particular agent, but also observations and actions of all other agents as well. Critic network has much higher visibility on what is happening while actor network can only access to the observation information of the respective agent. The output of the critic network is, nevertheless, still the Q value estimated given a full observation input(all agents) and a full action input(all agents). The output of the actor network is a recommended action for that particular agent.
Actor - It proposes an action given a state.
Critic - It predicts if the action is good (positive value) or bad (negative value) given a state and an action.
Why two networks? Because it adds stability to training. In short, we are learning from estimated targets and Target networks are updated slowly, hence keeping our estimated targets stable.

Goal
The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.
Reacher environment  used: UnityEnvironment(file_name="/data/Tennis_Linux_NoVis/Tennis")
Getting Started:
What you need to install 
Pytorch
Python 3x
Instructions:
How to Run, simple agent:
Github Link:
https://github.com/ChristianET-DS/Multi-Agent-Final-Project/blob/main/TennisFinal.ipynb




