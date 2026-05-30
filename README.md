# PSU AI-572 Reinforcement Learning

## General Notation
- **E (epsilon)** - exists
  - ex: a E A - for action there exists an action space
- **|** - given that; conditional upon
  - ex: P(s' | s,a) - the probability of s' given s and a

## Markov Decision Process (MDP)
- The MDP is the key ingredient for reinforcement learning. It is based on the *Markov Property*
- A sequence of states is Markov if and only if the probabilty of moving to the next state S<sub>t+1</sub> depends only on the present state S<sub>t</sub> and not on the previous states S<sub>1</sub>, S<sub>2</sub>, ..., SS<sub>t-1</sub>
- The goal of RL algorthms (agent) is to choose actions over time so as to maximize the expected value of the return. To be precise, the goal of the agents is to choose the optimal policy. We use a discount factor to get the discounted future rewards which can be interpreted as the current value of future rewards.

- **S** - state
- **A(s), A** - actions
- **T(s,a,s') ~ P(S' | s,a)** - transition model
  - s - current state
  - a - action
  - s' - new state
- **R(s),R(s,a),R(s,a,s')** - rewards; all three are equivalent
  - two approaches to reward the agent
    - _credit assignment problem_ - look at the past and check which actions led to the present reward, that is, which action gets the credit
    - _delayed rewards_ - check which action to take that will lead us to potential rewards; delayed rewards form the idea of foresight planning
- **γ** - discount factor; used to determine how much future rewards should be discounted
- **π(s)** - policy; the solution to the MDP problem; function that takes a state as the input and outputs an action that the agent needs to take

## Dynamic Programming (DP)
- **dynamic programming** - refers to a collection of algorthms that can be used to compute the optimal policies given a perfect model of the environment as in MDP
  - has limited utility in Reinforcement Learning because it assumes a perfect model and is computationally expensive
  - **key idea of dynamic programming and reinforcement learning in general is to use the value functions to organize and structure the search for obtaining good policies**
