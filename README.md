# bandits_contextual_lowrank
Code for https://arxiv.org/abs/2306.13053v2 and a different approach for leveraging low-rank structure in contextual bandits thorugh matrix completion. We follow hypotheses setup as in the paper, where an added gap between rewards is supposed.
This code performs Monte Carlo aggregation on the experiments to attain a mean behavior of regret for different instances.  

Data:
Synthetic data for K-armed bandits with an high probability of arms strongly separated by a gap between clusters. 
That is, we use hamming distance to ensure a strong separation. We also have comparable maximal reward among clusters. 

Bandit class:
Each cluster is assigned with a mean reward for each arm, then subgaussian noise is added on the observation.

Procedure:
Tree clustering as in Lee et al: provide code for the article https://arxiv.org/abs/2306.13053v2
Matrix clustering: compute an empirical observed distance between observed rewards (Delta), then update incrementally a communication graph between contexts (W), where each edge is weighted with respect to the observed distance between contexts. CLusters are identified more efficiently by the matrix procedure, while slower convergence is achieved by the hierarchical partitioning update. 

Output:
Regret for each run with different problem instance. 

