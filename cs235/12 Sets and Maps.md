Daily Note: [[2023-02-16]] -- [*created*:: 2023-02-16] #cs235 

## A set is a *set* of values with no duplicates

```cpp
#include <string>
#include <iostream>
```

```cpp
#include <set>
#include <unordered_set>
```

## Attributes:

- No defined order
- No duplicates
- Fast lookup

==sets are **associative containers**==

---

# Maps

*dictionaries in `python`*

Maps link a **key** with a **value**

- Use the key to store and retrieve the value

The collection of keys is a **set**
(unique, undefined order, associative)

```cpp
#include <map>

map<string, string> id_and_name = {
	{"110", "How to Program"}
	{"111", "Intro to Programming"}
	{"235", "Data Structures"}
	{"236", "Discrete Structures"}
}
```