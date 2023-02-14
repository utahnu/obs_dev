Daily Note: [[2023-02-14]] -- [*created*:: 2023-02-14] #cs180 

# Terms:

### Stochastic:
A process that is **predictably random**. 
We can generally understand the randomness with probability distributions, random variables

### Deterministic:
In computing, **given a particular input, the process will always produce the same output.**

### Non-Deterministic:
A process where, **given a particular input, is not guaranteed to produce the same output.**

---

# Stochasticity in Computing

*Most branches in CS are entirely deterministic*

- This becomes important in AI:
	- The process of learning: updating reasoning in a world of uncertainty

> [!Statistics is the Language of uncertainty]

---

# Two  types of uncertainty in a system:

### Aleatoric Uncertainty:

*Noise that is inherent in the observation measurements of a system*
(observation noise) - like from sensors

- Measurement noise

### Epistemic Uncertainty:

*Uncertainty in the parameters of a model - captures our ignorance*

- Incomplete observation/observability
- Incomplete modeling

---

# Probability Theory

*A mathematical framework for representing uncertain statements*

> Probability is just common sense reduced to calculus

### Logic:

provides a set of formal rules for determining **what propositions are implied to be true or false** given the assumption that some other set of propositions is true/false.

### Probability:

provides a set of formal rules for determining the **likelihood of a proposition being true** given the likelihood of other propositions

## Two Perspectives:

### Repeated Trials (frequentist)

Originally developed to analyze frequencies of **repeated events**

## Degree of Belief (Bayesian view)

Probability can be used to represent **degree of belief**, (0,1)

---

# Probability Rules

1. Probability is in range $(0,1)$
2. The sum of all possibilities is $1$
3. For any event, $A$, $P(A') = 1-P(A)$
4. and some others, and/or

---

# Random variables

- A random variable, random quantity, aleatory variable, or stochastic variable whose value is subject to variations due to chance
- Can take on a **set** of possible different values, each with an associated probability.


Sample space: the range of possible values

### Sampling
$x\sim p(X)$
### Scoring
$p(x)$

## Discrete random variable

- described with a **probability mass function (pmf)**
- probabilities are positive && sum to 1
	- *What's the most likely value of X?*
	- *the domain of a discrete variable is not necessarily integers*

What things are modeled well by discrete random variables?
