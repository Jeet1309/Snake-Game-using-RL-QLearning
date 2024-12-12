# Snake AI Using Deep Q-Learning

This project implements an AI agent to play the classic Snake game using **Deep Q-Learning**. The AI learns by interacting with the environment (game) and improving its performance over time by optimizing its neural network.

---

## Features

- **Deep Q-Learning**: Uses a neural network to approximate Q-values for better decision-making.
- **Self-Learning Agent**: The agent improves its gameplay through training, using short-term and long-term memory.
- **Customizable Neural Network**: Adjust the architecture, learning rate, and other hyperparameters for experimentation.
- **Real-time Visualization**: Watch the Snake game live as the agent plays and improves.
- **Score Tracking and Plotting**: Tracks the agent's scores over time and visualizes its progress.

---

## Project Structure

```plaintext
.
├── agent.py       # Implements the Q-learning agent
├── game.py        # The Snake game environment
├── model.py       # Neural network (Deep Q-Learning model)
├── helper.py      # (Optional) Helper functions for plotting results
├── README.md      # Project description (this file)
├── requirements.txt # Python dependencies
