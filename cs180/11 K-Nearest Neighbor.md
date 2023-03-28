Daily Note: [[2023-03-23]] -- [*created*:: 2023-03-23] #cs180 

To classify a new input vector x, examine the k closest training data points to s and assign the object to the most  frequently occurring class

Common values for k include 3, 5, 10

![[Pasted image 20230323093929.png]]

## When to consider:

- less than 20 attributes per instance
- lots of training data

## Advantages

- no optimization or training required
- easy to program
- learns complex target functions
- accuracy can be very good
- does not lose information

## Disadvantages

- slow at query time
- easily fooled by irrelevant attributes

```python
y = y[X['state'] == "NY"]
X = X[X['state'] == "NY"]
```


Binarize:
```python
y = np.where(y < median, 0.0, 1.0)
# where y < median, y = 0, else y = 1
```