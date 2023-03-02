Daily Note: [[2023-02-28]] -- [*created*:: 2023-02-28] #cs235 

# Selection Sort

## Algorithm:

Given a list of items:

- Partition the list into *sorted* and *unsorted*
	- *sorted* starts as empty
- Until *unsorted* is empty:
	- Find the **smallest** item in *unsorted*
	- Swap it wit the **first** item in *unsorted*
	- *sorted* now includes the first swapped item

```
5 2 7 3 5

Smallest is 2, swap with 5
5 2 7 3 5
^ |

Smallest is 3, swap with 5
2 5 7 3 5
  ^   |

Smallest is 5, swap with 7
2 3 7 5 5
    ^ |

2 3 5 5 7
      ^ |

2 3 5 5 7
        ^ |
```

## Pseudo-Code

```
for each i from 0 to size-1
	min = i
	for each j from i+1 to size
		min = j
	swap list[i] and list[min]
```

## Runtime Complexity: 

$\Theta(n^2)$

## Space Complexity: 

O$(n)$

*Running time is constant depending on sorted/reverse-sorted, random input*

```
5 2 7 3 4
^ |

2 5 7 3 4
  ^   |

2 3 7 5 4
    ^   |

2 3 4 5 7
      ^ |

2 3 4 5 7
          ^
```

---

# Insertion Sort

## Algorithm:

- Partition the collection into sorted and unsorted parts
	- The sorted part starts with the first item
- While the unsorted part is not empty
	- Take the first item in the unsorted part, insert into its place
	- Increment the partition

```
 8 5 2 7 3
 ^
 
 8 5 2 7 3
|  ^

 5 8 2 7 3
|    ^

 2 5 8 7 3
    |  ^

 2 5 7 8 3
  |      ^

 2 3 5 7 8
```

## Pesudo-Code

```
for each i from 1 to size
	j = i
	item = list[j]

	while j > 0 and list[j-1] > item
		list[j] = list[j-1]
		j--
		
	list[j] = item
```

## Runtime Complexity: 

- Random Data: $\Theta(n^2)$
- Sorted Data: $\Theta(n)$
- Reversed Data: $\Theta(n^2)$

## Space Complexity:

- O$(n)$

---

# Bubble Sort

## Runtime Complexity:

- Each time through is $\Theta(n)$
- Each item moving from back to front is $\Theta(n^2)$
- Total is $\Theta(n^2)$

## Space Complexity:

- O$(n)$