Daily Note: [[2023-01-31]] -- [*created*:: 2023-01-31] #cs180 

### Contents
- Basic terminology
- Statistical Data Types
- Continuous Data
- Discrete (categorical) Data

# What is Exploratory Data Analysis?

*Getting to know the data - The First Step*

## Reasons to perform EDA:
- Detect mistakes
- Check assumptions
- Preliminary model selection
- Determining relationships
	- Among explanatory variables
- Assessing direction and size of relationships
	- Between explanatory/outcome variables

## Terminology:

### $$ y_{i} = f(x_{i};\theta) $$

| symbol   | significance                              |
| -------- | ----------------------------------------- |
| y        | Dependent Variable, Target                |
| f        | The Function                              |
| x        | Explanatory variable(s), features         |
| $\theta$ | Parameters (quantity estimated from data) |

# (Statistical) Data Types

### Categorical (Discrete) Variables
```python
import numpy as np
import matplotlib.pyplot as plt
```

```python
cities = ["provo", "orem", "sanfran"]
np.random.choice(cities, p=[0.5, 0.4, 0.1], size = 10)

sex = ["male", "female"]
np.random.choice(sex, size=10)
```

### Quantitative (Continuous) Variables
*Typically real-valued numbers*
```python
np.random.multivariate_normal(np.zeros(3), np.eye(3), 10)
# bell curve
```

### Ordinal Variables

*Captures the raking of data*
Which has less, which has more? 
(but hard to say, by how much?)

```python
scale = ["hot", "hotter", "hottest"]
np.random.choice(scale, size=10)
```

### Some mathy stuff

$$ mean:\mu = \frac1n \sum_{i=1}^n  $$

$$ variance: S^2 = \frac1n \sum (x_i - \mu)^2 $$