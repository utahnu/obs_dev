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