Daily Note: [[2023-01-12]] -- [*created*:: 2023-01-12] #cs235 

# Streams
`<<` is a the "leftshift" operator
When used on a **stream**, it passes the thing on the right into the thing on the left

```cpp
cout << "hello, world!" << endl;
cerr << //there can also be other streams
```

## Formatting with streams
streams can also receive formatting 

```cpp
#include <iomanip>
using namespace std;

double foo = 3.14159625;
cout << foo << endl;

cout << fixed;
cout << setprecision(3);
cout << foo << endl;
//outputs 3.131
```

## Reading Input
In Python, you use the `input` function
In C++, you use the `cin` function

```cpp
#include <iostream>
#include <string>
using namespace std;

int foo;
string bar;
double baz;

cin >> foo >> bar >> baz;
//waits for input
cout << foo << endl << bar << endl << baz << endl;
//outs what was read into each name

//also has a getline function
getline;
```

### If the `>>` operator fails, it returns `false` and stops
```cpp
if (cin >> foo) {
	//execute;
}
else {
	cerr << "error duuddee" << endl;
}
```