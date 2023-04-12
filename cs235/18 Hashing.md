Daily Note: [[2023-04-04]] -- [*created*:: 2023-04-04] #cs235 

# The Hash Table

- A **Hash Function** converts a value into an integer
- A **Hash Table** uses a hash function to determine the location in which to store the value

The Big-O Complexity to add, remove, or lookup a value is ==$\Theta(1)$==

## Hash Function Qualities:

- **Determinism**: the same value will always yield the same hashcode
- **Efficiency**: the hashcode can be computed quickly
- **Defined Range**: the distribution covers the full defined range
- **Uniformity**: the hashcodes are uniformly distributed across the full possible space

### Collisions:

What if two inputs are hashed to the same value?

`foo` and `oof` both hash to the same value:

1.
2.
3. `oof` `<-` `oof` ?
4.
5.

#### Managing collisions:

**Probing:** if the slot is occupied, find another one
(sucks with edge cases)

**Chaining:** Store a list in each slot
as long as the number of items assigned to the same slot stays small, performance stays the same

1.
2.
3. `oof` , `foo`
4. 
5.

## Growing

- Create a new array
- Re-add each item to the table

## Big-O:

- Computing the position is O(1)
- Finding the bucket is O(1)
- Assuming the hash function uniformly distributes the data, the probability that there is a collision is small
- Growing is n, but only happens once every n times, averages to O(1)

$$O(1)$$