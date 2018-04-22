:hotel: [Reutrn to Python Home Page](https://github.com/geophydog/Python)

***

```
You can reference to codes as below when you want to input many lines from your keyboard
```

### Example :one:
```python
terminator = 'end'
lines = []
for line in iter(input, terminator):
    lines.append(line)

for line in lines:
    print(line)
```

__input__
```
1 2 3
4 5 6
7 8 9
end
```

__output__
```
1 2 3
4 5 6
7 8 9
```

*** 

### Example :two:
```python
import sys

lines = []
linesNew = []

for line in sys.stdin:
    linesNew = line.split()
    lines.extend(linesNew)

print(lines)
```

__input__
```
1 2 3 4
5 6 7 8
0 0 0 0
1 1 1 1
```
__output__
```
['1', '2', '3', '4', '5', '6', '7', '8', '0', '0', '0', '0', '1', '1', '1', '1']
```
