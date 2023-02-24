Daily Note: [[2023-02-23]] -- [*created*:: 2023-02-23] #cs235 

# Sum

Define a function, `sumto`, such that

$\mathrm{sumto}(x) = \sum_{i=1}^x {i}$
$\mathrm{sumto}(4) = 4+3+2+1$

$\mathrm{sumto}(4) = 4 + \mathrm{sumto}(3)$

$$\mathrm{sumto}(4) = \begin{cases}
4\\
\mathrm{sumto}(3) \begin{cases}
3\\
\mathrm{sumto}(2) \begin{cases}
2\\
\mathrm{sumto}(1) \begin{cases}
1\\
\mathrm{sumto}(0) \begin{cases}
0
\end{cases}
\end{cases}
\end{cases}
\end{cases}
\end{cases}$$

```cpp
int sumto(int x) {
	//must progress towards base case:
	if (x<0) { throw std::invalid_argument("x must be a positive integer!")}
	if (x==0) { return 0; } //The base case
	
	return x + sumto(x-1); //The recursive call
}
```

## Rule of Recursion #0:
> [!Identify the recursive relationship]
> how does this problem actually recurse?

## Rule of Recursion #1:

> [!A recursive function must include a base case]
> or it will never end

## Rule of Recursion #2:

> [!A recursive function must progress towards the base case]
> if it doesn't, it'll never reach the base case

## Rule of Recursion #3:

> [!Trust the induction]
> assume that the recursive call worked, then solve the $k \rightarrow k+1$ problem

---

## Rule of Recursion #4:

> [!Make sure that the number of recursive calls is reasonable]
> be mindful of the depth of recursive calls and the memory they require

## Rule of Recursion #5:

> [!Never solve the same sub-problem more than once]
> if your recursive solution calls the function with the same arguments more than once, it is redundant.
> caching these answers is a useful solution


<br>

# Induction [proof by]

- Show that the base case is correct
- Show that if it works correctly for $k$, it will work correctly for $k+1$

# When to use Recursion?

Should I use a loop or recursion?
Are there problems that are naturally recursive?

## Examples of recursive cases:

- Recursive Data
	- File system (folders contain folders)
	- Arithmetic expressions (expressions contain expressions)
	- Programming languages (statements contain statements)
- Divide and Conquer
	- Solve a problem by dividing it into smaller problems of the same kind
- Backtracking
	- Permutations
	- Boggle
	- Chess-move exploration

# Deep Recursion

Lots of layers & memory use
(see [[13 Recursion#Rule of Recursion 4:|Rule of Recursion #4]])

# Excessive Recursion

$$fib(n) = \begin{cases}
n = 0 \quad 0\\
n = 1 \quad 1\\
n > 1 \quad fib(n-1)+fib(n-2)
\end{cases}$$

```cpp
int fib(n) {
	if (n == 0) { return 0; }
	if (n == 1) { return 1; }
	return fib(n-1) + fib(n-2)
}
```

$2^n$ big$\Theta$ time curve

4x larger $\rightarrow$ 2,000,000x slower

---

How about all possible permutations of `ABC`?
eg. `ACB`, `BAC`, `BCA`...
$perm(S) = s + perm(S-s)\forall s \in S$

==Permuting things is a **factorial** big$\Theta$ curve==

---

# Binary Search

![[drawing_2023-02-23]]