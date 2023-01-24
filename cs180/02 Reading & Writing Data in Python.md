Daily Note: [[2023-01-17]] -- [*created*:: 2023-01-17] #cs180 
- [x] DataSci Lab 2 ✅ 2023-01-24
- [x] Python Lab 2 ✅ 2023-01-24
- [x] Chapter 2 Reading ✅ 2023-01-24

## Writing a file
```python
with open("./data.txt", "w") as f:
	for i in range(100):
		# write a comma separated file
		# write line index, and its square
		f.write(f"{i},{i**2}\n")
```

## Reading a file
```python
with open("./data.txt", "r") as f:
	dta = f.readlines()
```
```python
dta = []
with open("./data.txt", "r") as f:
	for line in f:
		idx, square = line.strip().split(",")
		dta.append(int(square))
```

## Classes and Objects
```python
class MrRobot():
	robot_type = friendly

	def __init__(self, name: str)
		self.name = name

	def string(self):
		return "hello, world!"
```
### Inheritance
```python
class MsRobot():
	robot_type = angry

	def __init__(self, name):
		super(MsRobot, self).__init__(name)

	def string(self):
		return "goodbye, world."
```