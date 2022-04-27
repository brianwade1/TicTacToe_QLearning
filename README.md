# Tic-Tac-Toe reinforcement learning practice

This repo teaches an agent to play tic-tac-toe using the standard Q-learning algorithm. The algorithm also includes a form of action masking where the environment returns only feasible actions (locations on the board without an X or O) and the agent only evaluates the Q-Value of those feasible states.

Users can play against another human or the trained agent. When a human plays against the agent, the agent uses imitation learning and uses the game history and outcome to update its policy. A trained agent is located in the agents](agents) folder for uses to continue training or to play against.

![tictactoe](/images/tictactoe_screenshot.png)

---

## Environment and Packages
The only package outside the standard packages required for this repo is numpy version >= 1.22. The [requirements.txt](requirements.txt) allows the user to create an environment with this package by running the command: conda create --name <env_name> --file requirements.txt

---

## Game Play
To play against a trained agent, run the [play_agent.py](play_agent.py) script (in the command line type: python play_agent.py after activating the environment with packages outlined above. Next, the program will ask the player if they want to be 'X' or 'O'. Type the letter (in caps) that you would like to play. The program then randomly chooses the player or agent to go first. At the players turn, choose the location to make a mark by specifying the row,column. The rows and columns start at 0 so the upper-left box is 0,0; the center box is 1,1; the lower-left box is 2,0; and the lower-right box is 2,2.

## Train Agent
To train the agent, run the [Q_learning_agent.py](Q_learning_agent.py) script. In the main section, the default number of games to train is 50,000 but this can be adjusted by the user. If the program detects an existing agent in the [agents](agents) folder, it will load that agent and continue to train with that agent. If it does not detect an agent, it will create a new one. Agents are saved to the [agents](agents) folder at the end of training.

---

## Folders and Files

This repo contains the following folders and files:

* [agents](agents) : Trained agents
   * Q_learning_TicTacToe_policy: Trained agent policy (state-value pairs) stored as a pickle object.

* [images](images) : Images used in this Readme file
   * [tictactoe_screenshot.png](tictactoe_screenshot.png): Screen shot from testing the agent.

* [game.py](game.py) - Main script for the tic-tac-toe game class and all of its methods. Running this file as main allows the user to play against another human.

* [play_agent.py](play_agent.py) - This script allows the user to play the agent. When run as main, the user can select X or O and then the game begins with a random toss of who goes first: the human or agent. 

* [Q_learning_agent.py](Q_learning_agent.py) - Main script for the Q-Learning-Agent class. When run as main, the agent plays 500,000 games against itself while updating its policy using the standard q-learning algorithm.

* [settings.py](settings.py) - Script that includes all the user settings for the tic-tac-toe game, q-learning agent, and training process.

* [requirements.py](requirements.py) - list of python packages required to run the scripts in this repo.

---
## References

1. Sutton, Richard S. and Barto, Andrew G. <ins>Reinforcement Learning: An Introduction</ins>, 2nd ed. The MIT Press; Cambridge, Massachusetts. 2018

2. Huang, S. and Ontañón, S., “A Closer Look at Invalid Action Masking in Policy Gradient Algorithms”, <i>arXiv e-prints: 
https://doi.org/10.48550/arXiv.2006.14171</i>, 2020.