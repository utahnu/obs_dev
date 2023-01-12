Daily Note: [[2023-01-12]] -- [*created*:: 2023-01-12] #cs235

# Integers

(signed by default)

| name      | size (bits) |
| --------- | ---- |
| char      | 8    |
| short     | 16   |
| long      | 32   |
| long long | 64   |
| int       | *16*   | 

# Floating point

| name   | size (bits) |
| ------ | ---- |
| float  | 32   |
| double | 64   | 

# Overflow

when the value exceeds the capacity of the type
```cpp
//for a char:
254
255
0 //haha c++ go brr
```

# Const

creates an immutable variable

```cpp
const double VARIABLE = 12;
VARIABLE = 13 //the c++ compiler will not allow this command!
```

# Type Casting
## Implicit:
when you pass a value to an already made compatible type
- up-casting
	- don't lose data
- down-casting
	- maybe lose data

## Explicit:
- use `static_cast<new-type>(value)`
```cpp
static_cast<double>(a)
//static cast is a function.
```

`int foo = 7;` this is a C-style cast
just use `static_cast` instead.

# Arrays

```cpp
int fooArray[5] = {1,2,3,4,5};
//all must be the same type

fooArray[0] //outputs 1
fooArray[-1] //this breaks in cpp. (random memory before)
fooArray[5] //this will also break. (random memory after)
```

# Characters
`char` is an 8-bit unsigned integer
In C++, Single quotes 'A' represent a single `char`

# Namespaces
a way of organizing code

`#include` copy-pastes code
we then use the namespace

```cpp
#include <iostream>
using namespace std;
```

# Comments

```cpp
//this is a comment

/* 
this is a multi-
line comment
*/

a = /*this is an inline comment*/ 42
```