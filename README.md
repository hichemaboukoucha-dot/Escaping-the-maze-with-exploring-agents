# Circle Maze Escape Simulation

## Overview

This is a Python-based simulation of a circle escaping a 5x5 maze, aided by scout X agents, using reinforcement learning (Q-learning). The circle learns to navigate to the exit while adapting to the dynamic positions of X agents that flee from it and provide environmental feedback.

## Features

- **Maze**: 5x5 grid with walls (1) and open paths (0), exit at (4,4).
- **Circle Agent**: Uses Q-learning to find the escape path, starting from a random position each episode.
- **X Agents**: 4 scouts that perform random walks, flee from the circle if within distance 2, and report (x, y) coordinates with binary direction indicators (x, x', y, y') for walls (1) or open paths (0).
- **Cohesion**: Geometrically-based function D, derived from the inverse average distance to X agents, influences movement angles.
- **Learning**: 100 training episodes with epsilon-greedy exploration (epsilon=0.1), tested over 10 trials with a greedy policy.

## Requirements

- Python 3.x
- NumPy (`pip install numpy`)

## Usage

1. Clone or download the repository.
2. Ensure NumPy is installed.
3. Run the script:

   ```bash
   python maze_simulation.py
   ```
4. The script trains the model and prints the success rate over 10 test runs.

## Code Structure

- **Maze Definition**: Hardcoded 5x5 grid in the script.
- **Agent Classes**:
  - `Agent`: Base class with position.
  - `XAgent`: Scouts with movement and measurement logic.
  - `CircleAgentQL`: Circle with Q-learning and knowledge integration.
- **Functions**:
  - `train()`: Trains the Q-table over 100 episodes.
  - `test()`: Evaluates the trained model over 10 trials.

## Results

- Training success rate: \~85-90% after 100 episodes.
- Test success rate: Reported after each run, typically high due to learned policy and X feedback.

## Customization

- Adjust `maze` size or layout by modifying the grid.
- Change number of X agents by altering the range in `xs = [XAgent(...) for _ in range(4)]`.
- Modify rewards or episode length in `train()`.

## License

This project is for educational purposes. Feel free to modify and use it as needed.

## 
