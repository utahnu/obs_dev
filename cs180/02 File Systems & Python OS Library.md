Daily Note: [[2023-01-17]] -- [*created*:: 2023-01-17] #cs180 

## OS Library
[OS Module in Python with Examples - GeeksforGeeks](https://www.geeksforgeeks.org/os-module-python-examples/?ref=lbp)
```python
import os

os.mkdir("./data")
os.path.exists("data")
	#true

os.getcwd()
	#gets current working directory

fpath = os.path.join(os,getcwd(), "data", "hello_world.txt")
	#fpath returns '/folder/data/hello_world.txt'
```

## JSON (JavaScript Markup Language)
```python
word_counts = {
	"word": 1,
	"word2": 2,
	"word3": 3
}

import json
fpath = os.path.join("data", "file.json")

with open(fpath, "w") as f:
	json.dump(word_counts, f)

with open(fpath, "r") as f:
	word_counts_2 = json.load(f)

word_counts_2
	#returns the same as word_counts
```

## YAML (YAML Ain't Markup Language)
```python
import yaml
with open("yamlEX", "r") as f:
	out = yaml.load(f)
```
