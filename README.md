# Quantum Reinforcement Learning: CartPole with QDQN

This project implements a **Quantum Deep Q-Network (QDQN)** to solve the OpenAI Gym `CartPole-v1` environment. It replaces the classical neural network with a **Variational Quantum Circuit (VQC)** using PennyLane and PyTorch.

## Overview
* **Environment:** OpenAI Gym `CartPole-v1`
* **Method:** Deep Q-Network (DQN) with Quantum Neural Network (QNN)
* **Tools:** PennyLane, PyTorch, Gym

## Configuration & Customization

You can modify the following variables in the code to change the environment or hyperparameters:

### 1. Changing the Environment
To solve a different problem (e.g., MountainCar), modify these variables in the code:
* **Environment Name:** Change `env = gym.make('CartPole-v1')` to your desired environment.
* **Input Dimension:** Update `x_dim = 4` to match the observation space size of the new environment.
* **Action Space:** Update `n_qubits = 2` (and the circuit measurement) to match the number of actions.

### 2. Hyperparameters
* `learning_rate`: 0.0005
* `gamma`: 0.98 (Discount factor)
* `batch_size`: 32
* `n_layers`: 3 (Depth of quantum circuit)
* `epsilon`: Exploration rate (starts at 8%)

## How to Run

1. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
2. **Run the Notebook:**

* Open `QRL_Cartpole.ipynb` in Jupyter Notebook or Google Colab.

* Click Run All cells.

3. **Monitor Training:**

* Training progress (Episode, Score, Epsilon) will be printed in the output.

* TensorBoard logs are saved in the tensorboard/ directory.

## Model Architecture
* Encoding: Angle Embedding (`RX` gates)

* Variational Circuit: `Rot` gates (trainable) + `CZ` gates (entanglement)

* Measurement: Pauli-Z expectation values represent Q-values.