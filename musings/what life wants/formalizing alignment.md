# Formalizing Alignment 
by Abe Dillon 

The alignment problem is usually informally defined as: 

  Ensuring that an Artificial Intelligent (AI) agent acts in accordance with the good of humanity.
  
We can generalize that definition to: 

  Ensuring minimal discord between two rational agents operating on the same environment.
  
The former deffinition can be seen as a special case of the latter where AI is one rational agent and humanity, collectively, acts as another rational agent.

The word 'minimal' in the generalized definition hints that the alignment problem is really just an optimization problem. We to model the system with some degrees of freedom which an optimizer can manipulate to minimize some measure we call discord. We can model the system as an agent-environment-loop with two agents, A and B, having corresponding goals, Ga and Gb, interact with a common environment, E:

//diagram

The two agents are considered "rational" according to the definition:

  An agent that acts so as to maximize the expected value of a performance measure based on past experience and knowledge.[Artificial Intelligence: A Modern Approach]
  
In this case, the performance measure (not to be confused with the alignment measure called "discord" which we have yet to formalize) for each agent is provided by its respective goal and the goals are generally functions of the state of the environment. That means the agents are both trying to manipulate the state of the environment according to their respective goals which may put them in contention. If the goal of agent A is to maximize the number of paperclips in the environment and the goal of agent B is to minimize the number of paperclips in the environment, the two agents are highly unaligned. They are trying to drive the state of the environment in conflicting directions.

We're typically interested in the case where the only degree of freedom available to the optimizer is the goal of one of the agents.
