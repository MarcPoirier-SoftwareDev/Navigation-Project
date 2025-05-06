# Navigation Project

This project trains an agent to navigate and collect bananas in the Unity ML-Agents Banana environment using reinforcement learning. The agent employs a Deep Q-Network (DQN) approach to learn an optimal policy for collecting yellow bananas while avoiding blue ones.

## Environment Details

- **State Space**: 37 dimensions, consisting of:
  - Ray-based perceptions from 7 rays at different angles, capturing information about yellow bananas, blue bananas, walls, and the agent, along with distance measurements.
  - The agent's velocity in two dimensions (forward/backward and left/right).
- **Action Space**: 4 discrete actions:
  - 0: Move forward
  - 1: Move backward
  - 2: Turn left
  - 3: Turn right
- **Objective**: Maximize the score by collecting yellow bananas (+1 reward each) while avoiding blue bananas (-1 reward each).
- **Solved Criteria**: The environment is considered solved when the agent achieves an average score of at least +13 over 100 consecutive episodes.

## Installation

To set up the project and prepare the environment for training, follow these steps:

1. **Install Python Dependencies**:
   - Ensure you have Python 3.6 or later installed on your system.
   - Use pip to install the required packages:
     ```bash
     pip install torch numpy matplotlib unityagents
     ```

2. **Download Unity Environment**:
   - Download the Banana environment specific to your operating system from the [Unity ML-Agents GitHub repository](https://github.com/Unity-Technologies/ml-agents).
   - Extract the downloaded zip file and note the path to the executable (e.g., `Banana.x86_64` for Linux; adjust for Windows or macOS).

3. **Configure the Environment Path**:
   - In your training script (e.g., `train.py`), update the path to the Unity environment file. For example:
     ```python
     env = UnityEnvironment(file_name="/path/to/Banana_Linux_NoVis/Banana.x86_64")
     ```
   - Replace `/path/to/Banana_Linux_NoVis/Banana.x86_64` with the actual path to the executable on your system.

## Running the Code

To train the agent in the Banana environment, follow these instructions:

1. **Prepare the Training Script**:
   - Ensure the Unity environment path is correctly set in the script (e.g., `train.py`).
   - Verify that the script includes the agent initialization, environment setup, and training loop as outlined in the notebook.

2. **Train the Agent**:
   - Execute the training script from the command line:
     ```bash
     python train.py
     ```
   - The script will start training the agent, displaying episode scores and average scores over the last 100 episodes in the console.
   - Training will continue until the environment is solved (average score ≥ +13 over 100 episodes) or the maximum number of episodes (default 2000) is reached.

3. **Monitor Training Progress**:
   - The script periodically saves model checkpoints and generates plots of the training progress (e.g., every 100 episodes).
   - When the environment is solved, the final trained model is saved (e.g., as `model.pt`).
   - Check the console output for performance metrics, such as the average score, to assess the agent’s learning progress.
