# pus-ai572-notes

## General Notation
- **E (epsilon)** - exists
  - ex: a E A - for action there exists an action space
- **|** - given that; conditional upon
  - ex: P(s' | s,a) - the probability of s' given s and a

## Markov Decision Process
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
- **π(s)** - policy; the solution to the MDP problem; function that takes a state as the input and outputs an action that the agent needs to take
