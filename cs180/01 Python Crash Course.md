Daily Note: [[2023-01-12]] -- [*created*:: 2023-01-12] #cs180 

## Assign a variable
```python
x = 100 #int
x = 100.0 #float
type(x) == float
#python is dynamically typed, no datatype declaration required
fn = 'Porter' + " " + 'Jenkins'
fn == 'Porter Jenkins'
```

## Memory management
```python
x = 100
y = x #make a copy of x
x += 1 #increment
x == 101
y == 100
```

## Lists
```python
a = [0,1,2,3]
b = list(range(10)) #b = list(range(10,20))
b == [0,1,2,3,4,5,6,7,8,9]
b[0] == 0
b[-1] == 9
b[:3] == [0,1,2] == b[0:3]
b[-3:] == [7,8,9]
a.append() #append
c = a + b #concatenate
```

## Dictionaries
```python
food = {}
food["main course"] = "tacos"
food
	{'main course': 'tacos'}

grades = {'peter': [1,3,2], 'amanda': [3,2,1]} #lists as values
grades["homework"] = {hw1: 92, hw2: 80} #nested dictionaries

"michael" in grades
	False
grades.get("michael", "student does not exist")
	'student does not exist' #return michael if exists, else:
grades.get("amanda", "student does note exist")
	[3,2,1]

grades.keys()
	#returns a list of keys
grades.values() 
	#returns a list of values
grades.items() 
	#returns tuples of each item (key and value)
for k, v in grades.items():
	print(k,v) 
		#prints each item on its own line
```

## Sets
```python
#sets collapse values that are the same
z = set([0,1,2,3])
	z == {0,1,2,3}
z.add(4)
	z == {0,1,2,3,4}
z.add(4)
	z == {0,1,2,3,4}

z.intersection(set([0,1]))
	{0,1}
```

## String Operations
```python
fn = "porter reece jenkins\n"

splits = fn.split(" ") #split
splits
	['porter', 'reece', 'jenkins']

fn.strip() #strip, remove whitespace
	'porter reece jenkins'

fn[0] #indicies
	'p'
fn[:6] #slices
	'porter'
#concatenate with + operator
f"string {name}" #formatted string
```