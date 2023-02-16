Daily Note: [[2023-02-15]] -- [*created*:: 2023-02-15] #cs235 

# Queues 
- Ordered
- First-in, First-out (FIFO)
- `front`, `push`, `pop`, `empty`

```cpp
#include <queue>

queue<string> names;

names.push("Abinadi");
names.push("Zeniff");
names.push("Pahoran");
names.push("Kishkuman");
names.push("Nephi");
names.push("Lehi");

while (!names.empty()) {
    cout << names.front() << endl;
    names.pop();
}
```
```
Abinadi
Zeniff
Pahoran
Kishkuman
Nephi
Lehi
```

### Used when:
- Insertion order should be preserved
- Only access allowed is to the front

(Queues can be more efficient by following FIFO)

---

# Stacks
- Ordered (but not by insertion)
- Last-in, First-out (LIFO)
- `push`, `pop`, `top`, `empty`

```cpp
#include <stack>

stack<string> names;

names.push("Abinadi");
names.push("Zeniff");
names.push("Pahoran");
names.push("Kishkuman");
names.push("Nephi");
names.push("Lehi");

while (!names.empty()) {
    cout << names.top() << endl;
    names.pop();
}
```
```
Lehi
Nephi
Kishkuman
Pahoran
Zeniff
Abinadi
```

### Used for:
- Inverting/Reversing
	- Retracing steps/backing up
- Nested Problems
	- Sub-problem has the same quality as the primary problem
		- maze
- Symmetric problems
	- matching parentheses, chiasmus, palindromes
- Memory allocation for fuctions

(allows for algorithms with nested, symmetric, reversing qualities)
(simple to implement efficiently [with a vector])

## Implementing Stack Interface with a vector:

```cpp
template <class T>
class Stak {
    vector<T> items;
    
    public:
    Stak() : items() {}
    
    size_t size() const { return items.size(); }
    void push_back(T const& item) { items.push_back(item); }
    T back() const { return items.back(); }
    void pop_back() { items.pop_back(); }
};
```

> [!Delegation pattern]
> Often, data structures are implemented by wrapping and combining other structures. This is called the **delegation pattern**.

---

# Priority Queues

- Ordered (sorted)
- `top`, `push`, `pop`

==*By default, the 'smaller' items come out last.*==

```cpp
#include <queue>

priority_queue<int> numbers;
numbers.push(7);
numbers.push(8);
numbers.push(2);

while (!numbers.empty()) {
    cout << numbers.top() << endl;
    numbers.pop();
}
```
```
8
7
2
```
```cpp
priority_queue<string> names;

names.push("Abinadi");
names.push("Zeniff");
names.push("Pahoran");
names.push("abinadi");
names.push("Kishkuman");
names.push("Nephi");
names.push("Lehi");

while (!names.empty()) {
    cout << names.top() << endl;
    names.pop();
}
```
```
abinadi
Zeniff
Pahoran
Nephi
Lehi
Kishkuman
Abinadi
```
```cpp
priority_queue<string, vector<string>, greater<string>> names;
//                                     ^^^^
// What you put as the comparer defines what items come out LAST, not first
// It may be counter intuitive to some. You've been warned. :)

names.push("Abinadi");
names.push("Zeniff");
names.push("Pahoran");
names.push("Kishkuman");
names.push("Nephi");
names.push("Lehi");

while (!names.empty()) {
    cout << names.top() << endl;
    names.pop();
}
```
```
Abinadi
Kishkuman
Lehi
Nephi
Pahoran
Zeniff
```

### Used for:
- Triage, Prioritization
	- Emergency room
	- OS Scheduling
	- Memory allocation (heaps)
- Solving least-cost paths

most Priority Queue operations are $\Theta (\log n)$.

---

# Deques
*Double-ended queues*

```cpp
#include <deque>

deque<int> numbers;
numbers.push_back(7);
numbers.push_front(8);
numbers.push_back(9);
numbers.push_front(10);

for (auto const& num : numbers) {
    cout << num << endl;
}
```
```
10
8
7
9
```

- Supports  adding/removing from front or back
- Supports random access

---

# Postfix notation (Integration example)

```
3 1 2 + + 5 *
```
1. Stack (3)
2. Stack (1,3)
3. Stack (2,1,3)
4. Stack (2+1,3) -> (3,3)
5. Stack (3+3) -> (6)
6. Stack (5,6)
7. Stack (5\*6) -> 30

```cpp
double calc(string const& expression) {
    stack<double> pending;
    stringstream ss(expression);
    string token;
    while (ss >> token) {
        if (isdigit(token[0])) {
            // Assume the whole thing is a number
            stringstream ts(token);
            double val;
            ts >> val;
            pending.push(val);
            
        } else {
            double a = pending.top();
            pending.pop();
            
            double b = pending.top();
            pending.pop();
            
            if (token == "+") {
                pending.push(b + a);
            } else if (token == "*") {
                pending.push(b * a);
            } else if (token == "-") {
                pending.push(b - a);
            } else if (token == "/") {
                pending.push(b / a);
            } else {
                cerr << "unrecognized operand: " << token << endl;
            }
        }
    }
    return pending.top();
}
```