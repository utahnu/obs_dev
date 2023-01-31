Daily Note: [[2023-01-31]] -- [*created*:: 2023-01-31] #cs235 
```cpp
#include <string>
#include <iostream>
#include <sstream>
```

#### *==Polymorphism== is when an object from a derived class are inherited from a base class, where that same object can take many forms*

## `virtual` in the base class method:

(call the child-class method by default (override the parent))

### `virtual` and destructors:
If you have a virtual function in your class, ==your destructor should be virtual also==

### Pure Virtual classes

```cpp
class Loud {
	public:
	virtual: string makeNoise() const = 0;
	//a pure virtual method (abstract base classes, or an interface)
	//probably should make a virtual destructor here
}

class Dog : public Loud {
	string makeNoise() const { return string("bork") }
}
```

Use interfaces/abstract base classes (like above). But avoid writing classes where the functionality requires looking at more than one class definition.

==Avoid overriding non-virtual methods.==

When modularizing code, use **composition** instead of inheritance.