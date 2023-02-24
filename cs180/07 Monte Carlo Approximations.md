Daily Note: [[2023-02-23]] -- [*created*:: 2023-02-23] #cs180 

- (rev) Expectations
- Covariances
- Monte Carlo Approximations

---

# Expectations

## Averages:

### $$\mathrm{average} = \sum_{i=1}^N {\frac1N x_i} = \frac1N \sum_{i=1}^N {x_i}$$

## Expected Values:

*Essentially a weighted average*

Expectations are the expected values of random variables

### $$\mathrm{expected \ value} = \sum_{i=1}^{N}{p(x_{i}) \cdot x_{i}} $$

Expectations also have the following properties:

$$\mathbb{E}_x[\alpha f(x) + \beta g(x)] = \alpha \mathbb{E}_x[f(x)] + \beta \mathbb{E}_x[g(x)]$$

$$\mathrm{where \ \alpha \ and \ \beta \ are \ not \ dependent \ on \ x}$$

Example: $\mathbb{E}_{p(x)}[2f(x)]=2\mathbb{E}_{p(x)}[f(x)]$
Goes into this table:

| x          | 0   | 1   | 2   | 3   |
| ---------- | --- | --- | --- | --- |
| f(x)       | 17  | 12  | 9   | 18  |
| p(x)       | 0.1 | 0.3 | 0.1 | 0.5 |
| f(x)\*p(x) | 1.7 | 3.6 | 0.9 | 9.0 | 

- Sum of $f(x) \cdot p(x) = 15.2$
- $\mathbb{E}[f(x)] = 15.2$
- $2\mathbb{E}[f(x)] = 30.4$

---
# Variance/Covariance

## Variance:
*How much do values of x vary as you sample p(x)?*

### $$\mathrm{Var}(f(x)) = \mathbb{E}\Bigl{[}(f(x)-\mathbb{E}[f(x)])^2\Bigl{]}$$

## Covariance:
*Sense of how much two values are linearly related to each other, and the scale of these variables*
High absolute values of the covariance mean that the values change a lot, and both far from their respective means at the same time.

### $$\mathrm{Cov}\bigl{(}f(x),g(y)\bigl{)} = \mathbb{E}\Bigl{[}\bigl{(}f(x) - \mathbb{E}[f(x)]\bigl{)}\bigl{(}g(y)-\mathbb{E}[g(y)]\bigl{)}\Bigl{]}$$

### Covariance matrices:

$$\mathrm{Cov}(x)_{i,j} = \mathrm{Cov}(x_{i},x_{j})$$

$$\mathrm{Cov}(x)_{i,i} = \mathrm{Variance}(x_{i})$$

$$\text{The matrix denoted as: }\Sigma = \begin{bmatrix}
5 & 4\\
4 & 6\\
\end{bmatrix}$$

### Expectation by integration:

$$\mathbb{E}_{p(x)}[f(x)]=\int_{x}{p(x)f(x)}$$

It's fine for continuous expectations. For others...

well, it gets hard.

"not analytically  tractable"

==approximate!==

# Monte-Carlo Approximations
*Use a bunch of samples with the right proportions*

$$\mathbb{E}_{p(x)}[f(x)] = p(x_{1})f(x_{1}) \ + \ p(x_{2})f(x_{2}) \ + \ ...$$

### $$\mathbb{E}_{p(x)}[f(x)] \approx \frac1N \sum_{i=1}^{N}{f(x_{i})}, \quad x_i \sim p(x)$$

Use this to get a distribution for labs:
sample for p(x):
`x = np.random.normal(mean,sd,size=n)`