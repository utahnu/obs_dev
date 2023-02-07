Daily Note: [[2023-02-07]] -- [*created*:: 2023-02-07] #cs235 

```cpp
#include <iostream>
#include <string>
```

If I have *n* items, how many items get copied with `push_back`? `pop_back`? `insert`?
Adding/removing the back, accessing items is efficient
The front or middle sucks

# Linked Lists

![[drawing_2023-02-07|700]]

```cpp
#include <list> //cpp's integration of linked lists
list<string> names;
names.push_back("thing");
names.push_fron("other");

names.front()
names.back()
//indexing the middle does not work
```

Linked lists don't have random access - Rather sequential access

| Vectors                     | Linked Lists           |
| --------------------------- | ---------------------- |
| good for +/- at end         | good for +/- anywhere  |
| bad for +/- everywhere else |                        |
| has random access           | bad with random access |

<br>

# Iterators

When iterating over a vector, one uses an index
When iterating over a list, one uses `next` and `previous` pointers
```cpp
vector<string> words;
words.push_back("one");
words.push_back("two");
words.push_back("three");

for (vector<string>::iterator iter=words.begin(); it!=words.end(); ++it) {
	std::cout << *it << std::endl;
}
```

```cpp
list<string> worrds;
words.push_back("one");
words.push_back("two");
words.push_back("three");

for (list<string>::iterator iter=words.begin(); it!=words.end(); ++iter) {
	std::cout << *it << std::endl;
}
```

> [!difference between i++ and ++i]
`i++` increments after `i` gets used
`++i `increments before `i` gets used

```cpp
for (auto iter=words.begin(); it!=words.end(); ++iter) {
	std::cout << *it << std::endl;
```

```cpp
words.insert(++words.begin(), "foo");
```

## Syntactic sugar

```cpp
for (string item : words) {
	std::cout << item << std::endl;
}
```

```cpp
for (const auto& c : foo) {
	std::cout << c << std::endl;
}
//faster with a reference
```

<br>

# Single Linked Lists

![[drawing_2023-02-07_0]]

