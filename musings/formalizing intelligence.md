# Formalizing Intelligence
by Abe Dillon

The term "intelligence" is used collqially to refer to a measure of a system. Particularly the system's ability to solve problems, although; we typically don't factor in the system's agency in actually *applying* solutions as part of the measure of its intelligence. If we did, we might conclude that someone like Stephen Hawking was of below average human intelligence, since He had limited physical agency. So a better deffinition of intelligence is: A measure of a system's ability to *produce solutions* to problems.

To formalize this concept, we must first formalize the terms "problem" and "solution". We can borrow the term "problem" from the field of mathematical optimization which defines an optimization problem as: 

1) Given: a function, f : A → 𝑅, from some set A to the real numbers

   Find: an element x0 ∈ A such that f(x0) ≥ f(x) for all x ∈ A.

However, while the optimization problem is explicitly to find an input that maximizes the given function, I'll subtly re-word expression 1 with more descriptive notation and call the function itself the problem, then define optimality in terms of inputs to the function which we'll call solutions:

2) Given: a function, problem : valid_solutions → rewards, from some set of valid_solutions to a real-valued reward

   For any two solutions, solution_1 and solution_2, from the set valid_solutions, solution_1 is defined as more optimal than solution_2 iff problem(solution_1) > problem(solution_2)

Example #1
... tic-tac-toe ...

We can imagine another function, an optimizer we'll call Λ, which takes a problem from some set of problems as input and returns a solution to the give problem. We'll call the set of all problems for which Λ returns a valid solution, the "valid domain" of Λ: 

3) Given: a function, Λ : problems → solutions, from some set of problems to solutions

   The valid domain of Λ is the set of all valid_problems ∈ problems :: ∀ problem ∈ valid_problems : problem(Λ(problem)) ∈ 𝑅

That is to say: the valid domain of Λ is the set of all problems for which Λ produces a valid solution. 

It might seem obvious to define the intelligence of Λ with respect to some subset of the valid domain of Λ as some aggregation (e.g. the average) of the reward yielded by the solutions produced by Λ over that subset, however; equating the term "intelligence" to some measure of optimality has three problems. One is that optimality is already a measure in it's own right, so there isn't much utility in coining a largely synonymous term. The second is that each problem may define its output in different and incompatible units that can't be so trivially aggregated.

Example #2
... problems with different units ...

We will eventually want to aggregate rewards for disparate problems, so we'll take a two-pronged approach. First, we don't wan't to overly constrain the definition of what is considered a problem, so we'll only add one caveat that each problem be associated with some unit for its reward. Second, we'll imagine some value() function which converts any tuple of a real-number and a unit to some other, equivalent real-number in a common unit we'll call 'common value units' (CVUs for short). 

4) ... value function ...

The third problem with defining intelligence as a simple aggregation of rewards is that it implies that the most intelligent algorithm for any given problem is to use brute force, which seems to starkly contradict our common intuition regarding the term "intelligence"

Example #3 
... brute force optimizer ...

A more useful formalization should include some measure of the resources required by the optimizer to produce each solution. Let's imagine some function resources() which takes an optimizer and a problem, then returns a vector of resources required to produce the solution to said problem. If each value in the vector has a corresponding unit, then we can convert all the resource metrics to CVUs with our value() function and add them up to get the total cost of producing the solution. Then we can subtact the total cost from the value of the reward yielded by the solution to get the net value of the solution:

5) ... net value ...

Example #4
... ...




