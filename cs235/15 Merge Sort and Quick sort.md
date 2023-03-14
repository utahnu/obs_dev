Daily Note: [[2023-03-02]] -- [*created*:: 2023-03-02] #cs235 

> "If I have seen further it is by standing on the shoulders of Giants."
> 
> \- Isaac Newton

# Merge Sort

## Pseudo-Code:

```
if List.size is at lease 2:
	split List into left and right
	recursively sort left
	recursively sort right
	merge left and right into 1 List
```

## Walk-through:

```
8 5 4 6 2 3 4 1

8 5 4 6  |  2 4 3 1

8 5  |  4 6  |  2 3  |  4 1

8  |  5 |  4  |  6  |  2  |  3  |  4  |  1

5 8  |  4 6  |  2 3  |  1 4

4 5 6 8  |  1 2 3 4

1 2 3 4 4 5 6 8
```

# Quicksort

## Walk-through:

```
9 8 1 6 (4) 3 7 5 2

(4) 8 1 6 9 3 7 5 2

(4) 2 1 6 9 3 7 5 8

(4) 2 1 3 9 6 7 5 8

2 1 3 (4) 9 6 7 5 8
```

Maximum time complexity: ==$\Theta (n^2)$== (in the pathological case)
(usually $\Theta (n \log n)$)

Though, Quick Sort has been demonstrated to perform faster than Merge Sort

```
2 7 2 5 8 9 1 2 (3)

(3) 7 2 5 8 9 1 2 2
    u             d

(3) 2 2 5 8 9 1 2 7
      u         d

(3) 2 2 5 8 9 1 2 7
        u       d

(3) 2 2 2 8 9 1 5 7
          u   d

(3) 2 2 2 1 9 8 5 7
           u^d

(3) 2 2 1 1 9 8 5 7
          d u

2 2 1 1 (3) 9 8 5 7
         d  u

return (4)
```

```
array = 1 3 ||| 10 2 9 7 -7 2 -2 9 -1 0 ||| 12 7 10 10 7 10 7 -3  
sorter.partition(array, 2, 11, 3) = 8
10 2 9 7 -7 2 -2 9 -1 0
(2) 10 9 7 -7 2 -2 9 -1 0
     u                  d
(2) 0 9 7 -7 2 -2 9 -1 10
      u              d
(2) 0 -1 7 -7 2 -2 9 9 10
         u         d
(2) 0 -1 7 -7 2 -2 9 9 10
           u       d
(2) 0 -1 7 -7 2 -2 9 9 10
              u    d
(2) 0 -1 7 -7 2 -2 9 9 10
                 u d
(2) 0 -1 7 -7 2 -2 9 9 10
                 d u      -->end
```