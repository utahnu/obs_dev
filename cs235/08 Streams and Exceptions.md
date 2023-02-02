Daily Note: [[2023-02-02]] -- [*created*:: 2023-02-02] #cs235 


# File streams
```cpp
! cat example.txt
// idk, this file has some text

#include <iostream>
#include <fstream>
#include <sstream>

std::ifstreaim in;
in.open("example.txt");

if (!in.is_open()) {
	std::cerr << "Failed to open file!" << std::endl;
} else {
	string line;
	while (getline(in, line)) {
		std::cout << "Line: " << line << std::endl;
	}
}

in.close();
```

```cpp
std::ofstream out;
out.open("ex2.txt");

if (!out.is_open()) {
	std::cerr << "Failed to open file!" << std::endl;
} else {
	for i(int i = 0; i < 5; i++) {
		out << i << std::endl;
	}
}

out.close();
```

# String Streams
```cpp
#include <sstream>

//ostringstream, istringstream for output/input
stringstream outs;
outs << "fee " << 7 << " bar";

std::cout << outs.str() << std::endl; //remember to call .str()
//foo 7 bar
```

```cpp
isringsttream ins("7 8 9 10");
int num;
while (ins >> num) {
	std::cout << num << std::endl;
}
```

# Exceptions
```cpp
#include <stdexcept>

void angry_func(int should_be_seven) {
	if (should_be_seven != 7) {
		throw std::invalid_argument "should_be_seven");
	}
	std::cout << "This is seven: " << should_be_seven << std::endl;
}


try {
	angry_func(8);
} catch (std::invalid_arguemtn &ex) {
	std::cerr << "this argument was not 7: " << ex.what() << std::endl;
}
```

```cpp
try {
	angry_func(10;);)
} catch (std::exception &ex) {
	std::cerr << "error" << ex.what() << std::endl;
}

try {
	angry_func(10);
} catch (...) {
	std::cerr << "error" << std::endl;
}
```


## Guidance for Exceptions
- Try to catch the specific exceptions
	- only use `std::exception` as a last resort
	- only use `catch (...)` as a total last resort
- Throw exceptions when unexpected things happen
		- Document the exceptions you throw
			- and the reasons for throwing them
- Never throw an exception in a destructor