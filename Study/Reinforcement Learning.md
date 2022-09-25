---
Credits: 5
Notes: No
Status: Studying
Year: 4
---
# Reinforcement Learning
[MyCourses](https://mycourses.aalto.fi/course/view.php?id=37149&section=1)

Exam:
- 20%: Quizzes
- 60%: 7 individual assignments
- 20%: 1 project work, in groups, max. 3 students, alone is unadvised

## Submission checklist
- “ex1” directory: files NOT zipped
- pdf file: without a specific name?
- pkl files: state values and the policy (Task 1)

## Schedule

- Lecture 1
    - Readings 5 chapt: ~0:50m, 2-2.3, 2.5-2.6
    - Readings 8 chapt: ~4h, 3-3.8
    - Quiz 1
    - Exercise 1: ~9h
- Lecture 2
    - [ ] Readings 5 chapt: ~1:30h, 5-5.4, 5.6
    - [ ] Readings 5 chapt: ~1:30h, 6-6.5
    - Quiz 2
    - [ ] Exercise 2
- Lecture 3
    - [ ] Readings 5 chapt: 9-9.3
    - [ ] Readings 2 chaps: 10-10.1

## Notes
Decision: make an action based on an observation
$$
$$
![Untitled](Reinforcement%20Learning/Untitled.png)

**State (S)** is the information used for the decision, e.g. position where I’m am in the grid

**Environment** comprises everything outside the agent

**Observation (O, z)** is a State when we cannot observe the whole environment

**Action (A)** $a=\pi(o)$

**Rewards (R)**

**Planning**: sequential decision making, is an optimization of a policy with respect to expected returns

**Evaluating** a policy quality is done through rewarding

**Optimizing the policy** is the trade-off beween learning (exploration) and maximizing rewards (exploitation)

**Reward function** (R), then rt=R(st, at)

**Cumulative rewards** (G), Timesep (t)

$$
G = \sum_{t}r_{t}
$$

Expectation (E): valore atteso

$$
\pi^* = \underset{\pi}{\mathrm{arg\ max}}\ \mathbb{E}[G]
$$

**Task**: choose a sequence of actions that maximizes cumulative reward

**r** (reward)

Policies can be **deterministic** when we get the same actions when going into a state multiple times, or **stochastic** (aka randomized) when we take actions based on a distribution.

## Markov Decision Process
**Markov decision process** (MDP) simplifies learning in action, states and rewards, setting an agent–environment boundary where for instance we define that endurance of our body is part of the environment and not agent.

**Markov properies** include information about all aspects of the past agent–environment interaction

**Markov decision process** (MDP) uses Markovian dynamics, meaning we don’t care what happened in the past, but only in the current state, e.g. chess
$$
p(s',r|s, a)
$$
Probability of each possible value for $S_t$ and $R_t$ depends only on the immediately preceding state and action, and the sum of these probabilities is 1
$$
\sum_{s^{\prime}\in{\mathcal G}}\sum_{r\in\mathcal G}p(s^{\prime},r|\,s,\,a)=\,1,
$$
**Episode** is a set of steps ending in a terminal state

**Discount factor** (γ) is used in cumulative rewards (G) function to allow an episode to end, e.g. if each state gives rewards +1 the reward is always infinite, on the other hand with discount factor it always converges. Practically is gives more importance to currect rewards compared to the future ones, it makes sense to have it in case we have the reward not changing during time.
$$
G_{t}\doteq R_{t+1}+\gamma R_{t+2}+\gamma^{2}R_{t+3}+... = \sum_{k=0}^{\infty}\gamma^{k}R_{t+k+1}
$$
**Policy (π)** is a mapping from states, to probabilities of selecting each possible action $\pi:O \rightarrow A$ . The policy function $\pi(a|s)$ defines the probability that an agent takes an action a given a state s.

**Value function** ($v_\pi$) 
$$
v_{\pi}(s)\ \doteq\ \mathbb{E}_{\pi}[G_{t}\mid S_{t}=s]
$$
**State-value function** ($q_\pi$)
$$
q_{\pi}(s,a)~\doteq~\mathbb{E}_{\pi}[G_{t}~|~S_{t}=s,A_{t}=a]
$$
Both functions can be estimated from experience by taking an average of the return for each state encountered, after infinite number of steps the will converge to $v_\pi(s)$.
Monte Carlo methods consider separate averages for each action and $q_{\pi}(s,a)$.

**Bellman equation** express the relationship between the value of a state and the values of its successor states by averaging all the possible state action pairs weighing the reward with the probabability of it occurring.

**Optimal Value function**
$$
v_{\ast}(s)\,=\,\operatorname*{max}_{a\in\mathcal{A}(s)}\,q_{\pi_{\ast}}\!\left(s,a\right)
$$
Optimal 

$$
q_{\star}\left(S,\,a\right)=
$$





**Reinforcement Learning** (RL) the goal is to maximize the expected total reward

**Optimal planning** for fixed-lenght plans: cost is the sum between all the steps + the final cost, defined as infinity if we don’t ge there. The goal is to minimize the cost (L).

![Untitled](Reinforcement%20Learning/Untitled%204.png)

![Untitled](Reinforcement%20Learning/Untitled%205.png)

![Untitled](Reinforcement%20Learning/Untitled%206.png)

![Untitled](Reinforcement%20Learning/Untitled%207.png)

**Value function** is used to solve optimal planning.
Optimal (*), starting point (k), end point (K)

![Untitled](Reinforcement%20Learning/Untitled%208.png)

**Value function** (V) can be computed where we have a policy, just by following the steps

![Untitled](Reinforcement%20Learning/Untitled%209.png)

***State-Value function** is fourmulated by the Bellman equasion, measures how good it is for the agent to be in a given state. Expected value is used because we are dealing with stochastic actions and transitions, not deterministic.*

![Untitled](Reinforcement%20Learning/Untitled%2012.png)

**Action-value function** (Q) we have the first action that is not random, then other values are random.

![Untitled](Reinforcement%20Learning/Untitled%2013.png)

Optimal policy, at least one optimal policy exists.

![Untitled](Reinforcement%20Learning/Untitled%2014.png)

Markov decision process is defined by (S, A, T, R , γ)

- S: States
- A: Actions
- T: timesteps?
- R: reward function
- γ: Discount factor

Complexity for value function is $O(|A||S|^2)$, for action-value function is $$O(|A|^2|S|^2)$$

## Monte Carlo methods

**Monte Carlo** describes trial and error algorithms

**Model-free**, used by Monte Carlo, is the opposite of model-based learning, used by MDP

v(s) is the average return achieed after visiting the state (s)

Value function V is initially randomized, Returns is the list of returns experienced for each state

![Untitled](Reinforcement%20Learning/Untitled%2015.png)

*Action state functions (Q) are more useful than Value function (V) because we don’t know how our pair necesserly translates.*

**Sampling retuns** is the technique used by Monte Carlo (left picture), opposed to MDP that uses the Bellman equasion (right picture)

![Untitled](Reinforcement%20Learning/Untitled%2016.png)

**Off-Policy** learning uses a target policy (π) that can be deterministic, and behavior policy (b) used to explore and update the target policy

Ordinary vs Weighted importance sampling

![Untitled](Reinforcement%20Learning/Untitled%2017.png)

Example

![Untitled](Reinforcement%20Learning/Untitled%2018.png)

![Untitled](Reinforcement%20Learning/Untitled%2019.png)

## Practical

Episode: 100 steps

In the standard formulation, a reward of 1 is given for every timestep the pole remains balanced. Upon failing (the pole falls) or completing the task, an episode is finished.

I *am writing to remind you to include the results of Question 2 (i.e., the program in the Jupiter notebook) in your solution pdf file. A short report about those values and pasting the figures generated by the code will be enough.*