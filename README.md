# Reinforcement-Learning-Comparison-of-SARSA-and-DQN-Algorithms-
This project evaluates SARSA and Deep Q-Network (DQN) in the Frozen Lake environment, focusing on both deterministic and stochastic settings. It compares how each algorithm navigates the grid to reach a goal while avoiding hazards, highlighting their strengths and limitations in handling uncertainty and complexity.

![SARSA Vs DQN](https://github.com/user-attachments/assets/d1bd49a5-401e-4d20-a656-b9525cbc3654)



## Introduction
This project investigates how the SARSA and DQN algorithms handle the challenge of navigating the Frozen Lake environment, a 4x4 grid where an agent must find its way from a starting point to a goal while avoiding dangerous holes. The Frozen Lake environment is an excellent testbed for understanding the decision-making processes of these algorithms in both predictable (deterministic) and unpredictable (stochastic) conditions.

## Problem Formulation
The Frozen Lake environment is defined as follows:
- **State-Space:** The environment consists of a 4x4 grid, with each cell representing a state. The agent begins at a designated start position and aims to reach the goal, avoiding cells that represent holes.
- **Action-Space:** The agent can move up, down, left, or right.
- **Reward Scheme:** 
  - Each step results in a reward of zero.
  - Reaching the goal yields a reward of +10.
  - Falling into a hole or making an invalid move incurs a penalty of -10.

## Solution Overview
We implemented and compared the SARSA and DQN algorithms:
- **SARSA (State-Action-Reward-State-Action):** An on-policy algorithm that updates its knowledge based on actions taken under its current policy.
- **DQN (Deep Q-Network):** An off-policy algorithm that uses a neural network to approximate the value function, leveraging experience replay and a target network to enhance stability.

## Evaluation Criteria
To evaluate the performance of these algorithms, we used the following metrics:
- **Learning Time:** The duration it takes for the algorithm to reach an optimal policy.
- **Steps:** The number of steps taken by the agent to reach the goal.
- **Average Reward:** The average reward obtained over several episodes, indicating the overall performance of the algorithm.

## Results and Discussion

### Deterministic Environment (Noise = 0)
- **Effect of Epsilon:** As epsilon increases, both algorithms converge faster but with reduced rewards. SARSA generally performs better at lower epsilon values, while DQN outperforms SARSA at higher exploration rates.
- **Effect of Alpha:** SARSA shows improved learning speed with a higher alpha value, while DQN struggles with reward optimization under the same conditions.
- **Effect of Gamma:** DQN manages long-term rewards more effectively with a higher gamma value, while SARSA performs consistently across different gamma settings.

### Stochastic Environment (Noise = 0.4)
- **Effect of Epsilon:** In noisy conditions, both algorithms struggle, but DQN consistently outperforms SARSA by managing exploration and exploitation more effectively.

### Comparison Across Environments
- In the deterministic environment, SARSA outperforms DQN with lower exploration rates.
- In the stochastic environment, DQN shows a significant advantage, handling noise better and achieving higher rewards.

## Conclusion
This project demonstrates that while SARSA excels in predictable environments with limited exploration, DQN is more versatile, performing better in noisy and unpredictable conditions. These findings suggest that DQN may be more suitable for real-world applications where environments are often complex and uncertain.

## How to Run the Code
1. Clone the repository.
2. Install the necessary dependencies using `pip install -r requirements.txt`.
3. Run the SARSA algorithm using `python sarsa_frozen_lake.py`.
4. Run the DQN algorithm using `python dqn_frozen_lake.py`.
5. Compare the results by analyzing the output logs and visualizations.

## Authors
- **Eng/Amr Mostafa Ibrahim** (TA @ ITCS School , Nile University , Cairo , Egypt)


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
