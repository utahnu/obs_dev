Daily Note: [[2023-01-19]] -- [*created*:: 2023-01-19] #cs180 

- A Highly optimized n-dimensional array library (c/c++ underthehood)
- Python has lists, but are slow to process
- NumPy provides an array object that is up to 50x faster
- array object in NumPy is called ndarray
	- also provides supporting functions

## N-dimensional Arrays

| Dim | Array  |
| --- | ------ |
| 0D  | Scalar |
| 1D  | Vector |
| 2D  | Matrix |
| nD  | Tensor |

```python
# a scalar (no dimension)
a = 10

# a vector (1 dimension)
b = [1, 3, 2, 4]

# a matrix (2 dimensions) 
c = [
	 [1, 2],
	 [3, 4]
]

# a tensor (n dimensions)
d = [
	 [[1,2],
	 [3,4]],

	 [[5,6],
	 [3,4]]
]
```

## Using NumPy
```python
import numpy as np

a = [1, 2, 3]

vector = np.array(a, dtype=float) #dtype "object" for strings)

vector
	# returns array([10., 5., 12.,])
vector.dtype == 'float64'
	# True


# init empty array
x = np.zeros(10) #an array of length 10
y = np.zeros((10,3 #*args)) #a matrix of 10 rows, 3 columns

y.shape
	#returns (10,3)
y.dim
	#returns 2d
```

## Slicing/Indexing
```python
array[:, 0:2] #all rows, columns 0-2
```

## Iterating (you probably shouldn't)
```python
for row in array:
	print(row)
#prints rows iteratively

for i in range(n_rows):
	for j in range(n_cols):
		print(array([i,j]))
```

## Axes and Vectorized Operations
```python
array.mean()
#returns mean of all values

array.mean(axis=0)
#returns mean of all values in the 0th dimension


array.reshape(10,1) #arguments are the new specs (transpose)


array.sum()
array.sum(axis=0)
```

## Element-wise Operations
```python
#say arrayA and arrayB are both arrays of size (10,3)
arrayA + arrayB
	#will perform the operator on each corresponding element pair

3 * arrayA
	#will perform scalar multiplication on each element
3 + arrayA
3 / arrayA
```

## Broadcasting
```python
#say arrayA has shape (10,3), arrayB has shape (10,1)
arrayB * arrayB #will apply column to column to all 3 of arrayA
```

## Linear Algebra
```python
#say arrayA has shape (2,3) and arrayB has shape (3,2)

A.transpose() #transpose
np.dot(arrayA, arrayB) #dot product
np.matmul(arrayA.transpose(), arrayB) #matrix multiplication
arrayA @ arrayB #alternate syntax for matrix multiplication

np.linalg.inv(arrayA) #inverse of matrix
np.linalg.det(arrayA) #determinant of matrix
```