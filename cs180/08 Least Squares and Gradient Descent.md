Daily Note: [[2023-03-02]] -- [*created*:: 2023-03-02] #cs180 

Learning parameters from data:

- maximum likelihood (last lecture MISSED)
- least squares
- gradient descent

Data Science Pipeline:
1. Collect data
2. Build model
3. Estimate parameters
4. Make predictions/inferences

## Maximum likelihood estimation

**Big Idea**: Search for the parameters that* maximize the likelihood* (joint probability) of our data

- optimization with calculus
- more complex - numerical optimization

what set of parameters **maximizes** the likelihood of the observed data?
(find where parabolic-shaped distribution has derivative 0, use first/second derivative test to find min/max)

## Least Squares

minimize the total sum of squared errors

**Gradient Descent** is a ubiquitous and popular algorithm to calculate this.

---

# Gradient Descent

## Key parts:

- A function we want to minimize: **Loss Function**
- (Randomly chosen) starting point: **Initialization Point**
- Compute steepness at point: **Gradient**
- Step downward (in steepest direction): **Negative Gradient**
- Continue until the function does not change: **Local Minimum**

![[drawing_2023-03-02]]

$$\text{Gradient:} \quad \nabla f(x,y) = \bigl(\frac{df}{dx}\frac{df}{dy}\bigl)$$

$$x^{(i+1)}=x^{(i)} - a \cdot \frac{df}{dx}(x^{(i)}, y^{(i)}) = (1-a) \cdot x^{(i)}$$