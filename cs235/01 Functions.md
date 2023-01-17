Daily Note: [[2023-01-12]] -- [*created*:: 2023-01-12] #cs235 

# Defining a Function

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

# When you call a function:
- All the variables for the current function & position are stored on the program stack
- Any arguments passed in are copied into a memory space for the function
- Function executes,
	- allocating memory for new variables as needed
- When the function returns, 
	- its memory is freed, 
	- the old function is reloaded into memory, 
	- return value is placed in the position of the function call, 
	- execution of old function resumes.

# Declaration and Definition of Functions

```cpp
double divide_ints(int a, int b);
//this is a DECLARATION, the function is not yet implemented
```

# References

```cpp
int a = 7;
int &b = a;
int& c = a; //both syntaxes work
b = 8;
a //outputs 8
```
![[drawing_2023-01-17|350]]

## Const References
```cpp
int magic(int const& a, int b) {
	return a + b;
}
```

# Multiple Return

```cpp
void mulit_return(int const& mid, int& out_less, int& out_more) {
	out_less = mid - 1;
	out_more = mid + 1;
}

int b = 7
int a, c;
multi_return(b, a, c);
cout << a << b << c << endl;
678
```

# Default Parameters

```cpp
void say_something(string message, string something="wassup") {
	cout << message << something << endl;
}

say_something("yep")
yepwassup
```

# Function Overloading
you can have many functions by the same name that take in different data types
```cpp
int add(int a, int b) {
	return a+b;
}

double add(double a, double b) {
	return a+b;
}
```

# Conditional statements

```cpp
if (a < b) {
	cout << "wassup" << endl;
} else if (a > b) {
	cout << "dapmeup" << endl;
}
```

## Logical Operators `! && ||`
`not` == `!`
`and` == `&&`
`or` == `||`

3 < 4 < 2 (does not work)
3 < 4 evaluates to 1
1 < 2 is true
True

# Loops
`while`
`do while`
`for`

# Switch functions
idk, maybe if I want to

# Ternary operator
idk, maybe if I want to