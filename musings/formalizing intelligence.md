# Formalizing Intelligence
by Abe Dillon

The term "intelligence" is used collqially to refer to a measure of a system. Particularly the system's ability to solve problems, although; we typically don't factor in the system's agency in actually *applying* solutions as part of the measure of its intelligence. If we did, we might conclude that someone like Stephen Hawking was of below average human intelligence, since He had limited physical agency. So a better deffinition of intelligence is: A measure of a system's ability to *produce solutions* to problems.

To formalize this concept, we must first formalize the terms "problem" and "solution". We can borrow the term "problem" from the field of mathematical optimization which defines an optimization problem as: 

1) Given: a function, f : A → 𝑅, from some set A to the real numbers

   Find: an element x0 ∈ A such that f(x0) ≥ f(x) for all x ∈ A.

However, while the optimization problem is explicitly to find an input that maximizes the given function, we will subtly re-word expression 1 with more descriptive notation and call the function itself the problem, then define optimality in terms of inputs to the function which we'll call solutions:

2) Given: a function, problem : valid_solutions → rewards, from some set of valid_solutions to a real-valued reward

   For any two solutions, solution_1 and solution_2, from the set valid_solutions, solution_1 is defined as more optimal than solution_2 iff problem(solution_1) > problem(solution_2)

Example #1
... tic-tac-toe ...

We can imagine another function, an optimizer we'll call Λ, which takes a problem from some set of problems as input and returns a solution to the give problem. We'll call the set of all problems for which Λ returns a valid solution, the "valid domain" of Λ: 

3) Given: a function, Λ : problems → solutions, from some set of problems to solutions

   The valid domain of Λ is the set of all valid_problems ∈ problems :: ∀ problem ∈ valid_problems : problem(Λ(problem)) ∈ 𝑅





