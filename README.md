# 🐦 Flappy Bird AI — Reinforcement Learning with DQN

A fully functional Flappy Bird game featuring an AI agent built using **Deep Q-Network (DQN)** and **PyTorch**. The agent interacts with the game environment, observes states, selects actions, and learns through rewards to improve its gameplay.

This project combines game development with practical Reinforcement Learning concepts.

## 📌 Project Overview

The goal of this project is to explore how an AI agent can learn to play Flappy Bird using Reinforcement Learning.

Instead of manually controlling the bird, the agent selects actions based on the current game state. During training, it receives rewards from the environment and uses these experiences to improve its decision-making policy.

The project includes a playable game environment, an AI agent, configurable training parameters, and model evaluation using a saved model.

## ✨ Features

- 🐦 Fully functional Flappy Bird game environment
- 🧠 Deep Q-Network (DQN) implemented with PyTorch
- 🎯 State-based action selection
- 🏆 Reward-based learning
- 🔁 Experience Replay for training
- 🎯 Target Network for more stable Q-value learning
- ⚙️ Configurable hyperparameters through `parameters.yaml`
- 💾 Model saving and loading for evaluation
- 🖥️ Visual gameplay rendering

## 🛠️ Technologies Used

- **Python** — Core programming language
- **PyTorch** — Deep learning and DQN implementation
- **Gymnasium** — Reinforcement Learning environment interface
- **flappy-bird-gymnasium** — Flappy Bird game environment
- **NumPy** — Numerical computations
- **YAML** — Training configuration

## 🧠 How It Works

The project uses a Deep Q-Network to estimate the expected future reward associated with possible actions.

### 1. Observe the State

The agent receives an observation from the game environment, representing information about the current game situation.

### 2. Select an Action

The agent chooses an action using an epsilon-greedy strategy. It explores actions during training and increasingly uses its learned policy as exploration decreases.

### 3. Receive a Reward

After taking an action, the agent receives a reward and observes the next state.

### 4. Store Experience

The agent stores transitions in replay memory:

`(state, action, reward, next_state, done)`

### 5. Learn with DQN

The network learns from sampled experiences to estimate better action values. A target network helps stabilize training.

### 6. Evaluate the Agent

The trained model can be loaded to test its learned policy and render the agent playing the game without further training.

## 📂 Project Structure

```text
Flappy-Bird/
│
├── agent.py                 # Agent, training and evaluation
├── dqn.py                   # Deep Q-Network
├── experience_replay.py     # Replay memory
├── game_flappy_bird.py      # Game implementation, if used
├── parameters.yaml          # Hyperparameter configuration
├── requirements.txt         # Python dependencies
├── .gitignore               # Files excluded from Git
├── README.md                # Project documentation
└── runs/                    # Saved models and training logs
```

## ⚙️ Configuration

The `parameters.yaml` file stores the hyperparameters used by the agent. Depending on your implementation, these may include:

- Learning rate
- Discount factor (gamma)
- Initial and minimum exploration rate (epsilon)
- Epsilon decay
- Replay memory capacity
- Mini-batch size
- Target network synchronization frequency
- Reward threshold

These parameters influence how the agent explores the environment, learns from experience, and evaluates its policy.

## 📊 Results and Evaluation

The agent can be trained and evaluated through the game environment.

For a meaningful evaluation, record:

- Number of training episodes
- Average reward over evaluation episodes
- Best reward achieved
- Survival time or score, if supported by the environment
- A comparison between early and later training performance

## 🎓 Key Learning Outcomes

Through this project, I explored:

- Fundamentals of Reinforcement Learning
- Deep Q-Networks and Q-value estimation
- Epsilon-greedy exploration
- Experience Replay and Target Networks
- Training versus inference
- Model persistence and evaluation
- Integration of a learned policy with a game environment
