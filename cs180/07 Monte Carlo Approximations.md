Daily Note: [[2023-02-23]] -- [*created*:: 2023-02-23] #cs180 

- (rev) Expectations
- Covariances
- Monte Carlo Approximations

# Expectations

Expectations are the expected values of random variables

Weights (1/n before each sum)

$$\text{expected value} = \sum_{i=1}^{N}{p(x_{i}) \cdot x_{i}} $$

Example: $\mathbb{E}_{p(x)} [2f(x)] = 2\mathbb{E}_{p(x)}[f(x)]$
Goes into this table:

| x    | 0   | 1   | 2   | 3   |
| ---- | --- | --- | --- | --- |
| f(x) | 17  | 12  | 9   | 18  |
| p(x) | 0.1 | 0.3 | 0.1 | 0.5 | 


# Variance/Covariance

## Variance:
*How much do values of x vary as you sample p(x)?*

Var(f(x)) = E\[(f(x) - E\[f(x)])^2]

## Covariance:
*Sense of how much two values are linearly related to each other, and the scale of these variables*
*High absolute values of the covariance mean that the values change a lot, and both far from their respective means at the same time.*
Cov(f(x)) , g(y)) = E...

### Covariance matrices:

$$\mathrm{Cov}(x)_{i,j} = \mathrm{Cov}(x_{i},x_{j})$$
$$\mathrm{Cov}(x)_{i,i} = \mathrm{Variance}(x_{i})$$
$$\text{The matrix denoted as: }\Sigma = \begin{bmatrix}
5 & 4\\
4 & 6
\end{bmatrix}$$

### Expectation by integration:

$$\mathbb{E}_{p(x)}[f(x)]=\int_{x}{p(x)f(x)}$$

well, it gets hard.

==approximate!==

# Monte-Carlo Approximations
*Use a bunch of samples with the right proportions*

$$\mathbb{E}_{p(x)}[f(x)] = p(x_{1})f(x_{1}) + p(x_{2})f(x_{2}) + ...$$

$$\frac1N \sum_{i=1}^{N}{f(x_{i})}, \hspace{5mm} x_i \sim p(x)$$

Use this to get a distribution for labs:
sample for p(x):
`x = np.random.normal(mean,sd,size=n)`