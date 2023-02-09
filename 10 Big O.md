# $\Theta$

---

When solving a problem, which algorithm?
- Fastest?
- Smallest?
- Simplest?

How do you measure time/space?

- Empirical measurement
	- eg. `time ./a_program`
- Analysis
	- eg. look at code


$$ \text{Linear Time: } T(n) = 3n+5 $$
$$ \text{Exponential Time: } 2^n + 5n^3 + 2n^2 $$

2^n is a big deal - the smaller ones don't matter as much 

---

# Big $\Theta$ Notation

The "order" of an algorithm describes the dominating term in the algorithm's performance (in CS)

$$ T(n) = n^2 + n + 5 $$

This would be $$ \Theta(n^2) $$ because it is dominated by the n^2 term.

$$ T_{1} = 3n + 20 $$
$$ T_{2} = n^2 + 10$$

Which of the two above would be faster?

## Different growths:

- $$\Theta(1) = \text{constant}$$
- $$\Theta(n) = \text{linear}$$
- $$\Theta(\log n) = \text{logarithmic}$$
- $$\Theta(n\log n) = n\log n$$
- $$\Theta(n^2) = \text{quadratic}$$
- $$\Theta(n^3, n^6, ...) = \text{polynomial}$$
- $$\Theta(2^n) = \text{exponential}$$
- $$\Theta(n!) = \text{factorial}$$

In order: 
1. Logarithmic - $\Theta(\log n)$
2. Linear - $\Theta(n)$
3. Polynomial - $\Theta(n^c)$
4. Exponential - $\Theta(c^n)$
5. Factorial - $\Theta(n!$)

*Exponential and factorial time is pretty bad*

### Definition of $\Theta$:

#### $$\Theta$$

$$T(n) \text{ is } \Theta(f(n)) \text{ if there exists two constants, } c \text{ and } n_{0} \text{ such that:}$$

#### $$T(n) \leq c \cdot f(n) \text{ } \forall n \geq n_{0}$$

---

# Determining Big $\Theta$

## Simple statements have **constant time**

```cpp
int a = 42;
```

## Loops:
- Determine big $\Theta$ of loop body
- Multiply by number of loops
```cpp
for (int i=0; i<n; i++) {
	a = a + i;
}

//Nested loops and would multiply
```

big $\Theta$ gets bigger as we have n\*n or nested loops or other factors

### ==this loop is constant==
```cpp
for (int i=0; i<10; i++) {
	a = a + i;
}
```

## Conditional statements:
```cpp
if () {
	//body
} else {
	//body
}
```

If the probability of each is similar, big $\Theta$ would take the more costly condition
One could argue for big $\Theta$ of the cheaper option if it is more likely

---

# Different Big $\Theta$ time complexities

### $\Theta(n)$
```cpp
for (int i=0; i<n; i++){
	a = a + i;
}
```

### $\Theta(n^2)$
```cpp
for (int i=0; i<n*n; i++) {
	a = a + i;
}
```

### $\Theta(\log n)$
```cpp
for (int i=0; i<n; i*=2) {
	a = a + i;
}
```

---

# Vector vs. SLL vs. DLL

|               | Vector      | SLL (no tail)            | DLL (w/tail) |
| ------------- | ----------- | ------------------------ | ------------ |
| pop_back      | $\Theta(1)$ | $\Theta(n)$              | $\Theta(1)$  |
| push_back     | $\Theta(1)$ | $\Theta(n)$              | $\Theta(1)$  |
| insert_front  | $\Theta(n)$ | $\Theta(1)$              | $\Theta(1)$  |
| insert_middle | $\Theta(n)$ | $\Theta(1) or \Theta(n)$ | $\Theta(n)$  |
| at            | $\Theta(1)$ | $\Theta(n)$              | $\Theta(n)$  | 

