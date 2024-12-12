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

## How It Works

1. **Game Environment (`game.py`)**:
   - The Snake game is implemented using `pygame`.
   - The environment interacts with the agent by providing:
     - **Reward**: Positive rewards for eating food and negative rewards for collisions.
     - **State**: Information about the current game, including the snake's position, food location, and potential dangers.
     - **Game-over Flag**: Indicates when the game ends.

2. **Agent (`agent.py`)**:
   - The AI uses **Deep Q-Learning** to learn optimal actions based on the current state.
   - The agent maintains a **memory buffer** to store its experiences (state, action, reward, next state, done flag).
   - Two types of learning:
     - **Short-term memory**: Trains the neural network with the most recent experience.
     - **Long-term memory**: Samples a batch of experiences from memory to train the network.

3. **Model (`model.py`)**:
   - The neural network approximates Q-values for each possible action in a given state.
   - The architecture consists of input, hidden, and output layers:
     - Input size: Represents the state (11 features for this game).
     - Output size: Represents the possible actions (move straight, turn left, turn right).
   - The Bellman equation is used to compute the target Q-values:
     \[
     Q_{\text{new}} = R + \gamma \times \max(Q_{\text{next}})
     \]

4. **Training Process**:
   - The agent starts with random actions (exploration) and gradually shifts to learned actions (exploitation).
   - The agent receives feedback (reward) after each action, which helps it learn which actions are beneficial.

5. **Visualization**:
   - The game is displayed in real-time as the AI plays.
   - A plot of scores and mean scores is generated to track the AI's progress.

---

## Installation

Follow these steps to set up and run the project:

### 1. Prerequisites

Ensure you have the following installed:
- **Python 3.7+**: The project requires Python version 3.7 or later.
- **pip**: Python's package manager for installing dependencies.

### 2. Clone the Repository

Clone the project repository to your local machine. Replace `<your-repo>` with the actual URL of your GitHub repository:
```bash
git clone https://github.com/Jeet1309/Snake-Game-using-RL-QLearning.git
cd snake-ai-qlearning
```
### 3. Create a Virtual Environment (Optional but Recommended)

Set up a virtual environment to isolate the project dependencies:
```bash
python -m venv venv
```
Activate the virtual environment:

On Linux/macOS:
```bash
source venv/bin/activate
```
On Windows:
```bash
venv\Scripts\activate
```
### 4. Install Dependencies

Install the required Python packages listed in `requirements.txt`:
```bash
pip install -r requirements.txt
```
### 5. Run the Training Script
Start the training process by running the `agent.py` script:

```bash
python agent.py
```
The AI will begin playing the Snake game and learning to improve its performance over time.
The model's weights will be saved in a file named model.pth in the ./model directory.
## Results

The AI agent was trained using Deep Q-Learning, and its performance improved over time as it learned to play the Snake game. Below are some results demonstrating the agent's training progress:

1. **Training Progress**:
   - The following plots show the agent's scores and mean scores over a series of games.

   ### Short-term Training:
   ![Short-term Training Results](![Figure_1](https://github.com/user-attachments/assets/da31c18d-639d-4a94-a0be-61fe50f55e75)
)

   ### Long-term Training:
   ![Long-term Training Results](![Figure_longterm](https://github.com/user-attachments/assets/4592bee0-3e25-4848-adc4-5f96cdcc1e29)
)

2. **Observations**:
   - The agent begins with random actions and initially achieves low scores.
   - Over time, as the agent learns through experience and training, its performance improves significantly.
   - The blue line represents the score per game, while the orange line represents the running average (mean score).

---

### Insights
- The steady increase in the mean score demonstrates the AI's ability to learn and adapt.
- The game's growth stagnated after a while as it may now need changes in the model architecture.
- Variations in individual game scores highlight the stochastic nature of the game and the agent's exploration vs. exploitation strategy.

