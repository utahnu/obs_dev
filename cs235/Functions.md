Daily Note: [[2023-01-12]] -- [*created*:: 2023-01-12] #cs235 

```cpp
int add(int a, int b) {
	return a + b;
}

add(7, 8) //returns 15
```
If a function does not return anything, the `void` prefix is added
```cpp
#include <iostream>
#include <string>
using namespace std;

void print4x(string message) {
	cout << message << message << message << message << endl;
}
```

# The Main Function
Every program must have a main function that returns an integer. A successful program run will return with an exit code `0` (the return value of the main function).
```cpp
int main(int argc, char* argv[]) {
	//return 0 (is not required)
}
```

## Functions cannot be defined inside of other functions (except for lambdas)