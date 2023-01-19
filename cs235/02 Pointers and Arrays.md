Daily Note: [[2023-01-19]] -- [*created*:: 2023-01-19] #cs235 

# Memory Location

Storage is a series of bytes - a *variable* is an alias for a place in memory

The `&` operator gets the *address* of the bytes represented by a variable
`&bar;`

the `*` operator can get us the bytes stored at a specific address
`int*` 

```cpp
int foo = 7;
int* fooP = &foo; 
```

```cpp
int foo = 66;
int bar = 8;

int* fooPtr = &foo;
int* barPtr = &bar;

//value of foo: 66
//location of foo: 0xfffbbab0030
//value of fooPtr: 0xfffbbab0030
```

==a pointer is a new value (which is an address), a reference is another name for the same location==

```cpp
int &baz = bar; //baz is a reference
int* barPtr = &bar; //barPtr is a pointer
```

<br>

# `new` and `delete`
## Stack 
- Data deleted after termination of a function
## Heap
- Data that will be available after a function terminates (an address is needed)
- ==Must be deleted manually with `delete`==
	- When one fails to release memory, it is a *memory leak*
	- `valgrind` is a tool that can help identify memory leaks

Values declared with `new` will be stored on the heap

```cpp
int *foo = new int(7); //int is stored on the heap

delete foo; //the address is now marked as available
```

<br>

# Arrays

When C++ makes an array, it returns the address of the first element of the array

![[drawing_2023-01-19]]

### `new` and `delete` with Arrays:

```cpp
//to create an array on the heap:
int size = 10;
int* my_array = new int[size];

//to free the memory of an array on the heap:
delete[] my_array;
```

<br>

# `nullptr`

When you have a pointer, but nothing to point to, use `nullptr`

==*When a pointer's data is deleted, practice immediately replacing the pointer*==

<br>

# Combined

```cpp
int* arrayOfZeros(int size) {
	int* array = new int[size];
	for (int i = 0; i < size; i++) {
		array[i] = 0;
	}
	return array;
}

void newArray(int* &array, int size) {
	int* tmp = array;
	array = arrayOfZeros(size);
	delete tmp;
}
```

