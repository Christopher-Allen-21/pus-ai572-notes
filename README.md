# PSU AI-572 Reinforcement Learning

## General Notation
- **E (epsilon)** - exists
  - ex: *a E A* - for action *a* there exists an action space
- **|** - given that; conditional upon
  - ex: P(s' | s,a) - the probability of *s'* given *s* and *a*

## Markov Decision Process (MDP)
- The MDP is the key ingredient for reinforcement learning. It is based on the *Markov Property*
- A sequence of states is Markov if and only if the probabilty of moving to the next state S<sub>t+1</sub> depends only on the present state S<sub>t</sub> and not on the previous states S<sub>1</sub>, S<sub>2</sub>, ..., S<sub>t-1</sub>
- The goal of RL algorthms (agents) is to choose actions over time so as to maximize the expected value of the return. To be precise, the goal of the agents is to choose the optimal policy. We use a discount factor to get the discounted future rewards which can be interpreted as the current value of future rewards.

- **S** - state
- **A(s), A** - actions
- **T(s,a,s') ~ P(S' | s,a)** - transition model
  - *s* - current state
  - *a* - action
  - *s'* - new state
- **R(s), R(s,a), R(s,a,s')** - rewards; all three are equivalent
  - two approaches to reward the agent
    - *credit assignment problem* - look at the past and check which actions led to the present reward (i.e. which action gets the credit)
    - *delayed rewards* - check which action to take that will lead us to potential rewards; delayed rewards form the idea of foresight planning
- **γ** - discount factor; used to determine how much future rewards should be discounted
  - <img width="249" height="80" alt="Screenshot 2026-05-30 at 2 53 15 PM" src="https://github.com/user-attachments/assets/2353892c-031e-4ff2-928c-879d9bb7d9be" />
- **π(s)** - policy; the solution to the MDP problem; function that takes a state as the input and outputs an action that the agent needs to take
  - a policy is time-independent and guides the choice of the action for the agent at a given state
  - <img width="319" height="49" alt="Screenshot 2026-05-30 at 2 54 59 PM" src="https://github.com/user-attachments/assets/022f75f5-04b7-437d-8826-6c7886c669f1" />

- **Bellman Equation** - mathematical formula used in dynamic programming and RL to break complex decision-making problems into simpler recursive problems **(used to solve an MDP problem)**
  - For each state in the state space, the Bellman Equation gives us the value of that state, *v(s)*. The value of the state *s* is the reward we get upon leaving that state plus a discounted average over the next possible succesor states where the value of each possible successor state is multiplied by the probability of landing in that state
  - <img width="663" height="268" alt="Screenshot 2026-05-30 at 2 57 35 PM" src="https://github.com/user-attachments/assets/39fef9e2-0e01-4d4e-9148-a997b9839ece" />
  - <img width="1084" height="449" alt="Screenshot 2026-05-30 at 3 02 54 PM" src="https://github.com/user-attachments/assets/095c0e78-3886-40df-bce8-393b6036a91b" />



## Dynamic Programming (DP)
- **dynamic programming** - refers to a collection of algorthms that can be used to compute the optimal policies given a perfect model of the environment as in MDP
  - has limited utility in Reinforcement Learning because it assumes a perfect model and is computationally expensive
  - **key idea of dynamic programming and reinforcement learning in general is to use the value functions to organize and structure the search for obtaining good policies**
