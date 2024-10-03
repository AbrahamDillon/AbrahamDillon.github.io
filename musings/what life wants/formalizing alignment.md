# Formalizing Alignment 
by Abe Dillon 

The alignment problem is usually informally defined as: ensuring that an Artificial Intelligence (AI) agent acts in accordance with the good of humanity. However, a more generalized definition would be: ensuring two intelligent agents act with minimal discord. This accomodates the former deffinition by modeling AI as one agent and humanity, collectively, as the other agent.

We can model the situation using the agent-environment-loop framework from reinforcement learning as: two agents, A and B, having corresponding goals, Ga and Gb, interact with a common environment, E.

<diagram>

Generally, Ga and Gb are functions of the state of the environment.

The word 'minimal' in the generalized definition hints that the alignment problem is really just an optimization problem. We need some measure of discord within the system and some degrees of freedom to manipulate to minimizes that measure. In the general case, the measure would be a function of all the variables in the system and any of those variables could be parameterized with degrees of freedom:

Given A = A_generator(x), B = B_generator(x), Ga = Ga_generator(x), Gb = Gb_generator(x), E = E_generator(x), and some measure discord(A, B, Ga, Gb, E)
Find argmax_x discord(A, B, Ga, Gb, E)

 
