Daily Note: [[2023-01-31]] -- [*created*:: 2023-01-31] #cs235 

```cpp
#include <iostream>
#include <string>
#include <sstream>
```

### Say we have a function that prints the input:
```cpp
void printThing(int thing) {
	std::cout << "The thing is: " << thing << std::endl;
}
	//can only take in an int argument, cannot print a string or others
```
*What about the type of the input? Should we make a new function for each data type?*

---

# Templates

*A pattern that the compiler uses to create functions (or classes) for type-specific code*

### Functions
```cpp
template <class T> //<class DTYPE>
void printThing(T thing) {
	std::cout << "The thing is: " << thing << std::endl;
}
	//this template will now create a function for each dataype for us.
```

### Classes:
```cpp
template <class T>
class Pair {
	T first;
	T second;

	public:
	Pair(T const& first, T const& second) : first(first), second(second) {}
	T getFirst() const { return this->first; }
	T getSecond() const { return this->second; }
}
```

### Having multiple template types:
```cpp
template <class T1, class T2>
void printThings(T1 thing1, T2 thing2) {
	std::cout << "The things are: " << thing1 << ", " << thing2 << std::endl;
}

Pair<int> ints(1, 3);
printThins(ints); //prints
```