Daily Note: [[2023-01-24]] -- [*created*:: 2023-01-24] #cs235 

# Structs
Struct is a simple structuring of memory. 
```cpp
sizeof(int) //returns size of int (4 bytes)

struct TwoInts {
	int first;
	int second;
}

TwoInts foo;
TwoInts bar;

sizeof(TwoInts) //returns 8
```
by default, values in structs are ==public==

# Classes
```cpp
class TwoNumbers {
	double first;
	double second;
}

TwoNumbers doubles;
doubles.first = 1.24342
//ERROR - first is a private member of ''<namespace>::TwoNumbers'
```
By default, values in the class are ==private== to that class (data/strong encapsulation)
```cpp
class TwoNumbers {
	public:
	double first;
	double second;
}
```

## Member Access

```cpp
TwoNhumbers* moreNumbers = new TwoNumbers;
moreNumbers.first = <a number> //ERRORS - moreNumbers is a pointer

(*moreNumbers).first = <a number> //WORKS
moreNumbers->second = <a number2>  //Also has an operator
//(all of this works because these variables were declared public)
```

### ==this == self==

```cpp 
class TwoNumbers {
	private:
	double first;
	double second;
	public:
	double getFirst() {return this->first;}    //(this == self)
	double getSecond() {return this->second;}  //(this == self)
}
```

## Constructors
*Similar to Python's \_init_*

==Often in C++, you make member variables private, then setter methods public==

==INSTEAD - avoid setter methods and do it in the constructor==

==If a constructor takes no arguments, don't include ()==

```cpp
class HasADouble{
	private: 
	double cantTouch
	public: 
	HasADouble(double const& value) : cantTouch(value) {} //requires a value in the constructor
	double getDouble() const {
		return this->cantTouch;
	}
}
```

## Destructors

```cpp
class Noisy {
	public:
	Noisy() {}
	~Noisy() {
		//the destructor, with a tilde ~
		//call delete here if new is used within the class
	}
}
```

# `const` and `class`

```cpp

```

# Class Organization

In book.h:
```cpp
class Book {
private:
	string title;
	string author;
	int year;
public:
	book(title) : //the constructor

	string gettitle();
	string getauthor();
}
```

In book.cpp:
```cpp
string Book::getTitle() const {
	return nullptr;
}
```

==just do everything in .h for now==

`stringstream` seems pretty neat
```cpp
#include <sstream>

stringstream ss;
ss << this->function() << " " << "etc"
return ss.str();
```