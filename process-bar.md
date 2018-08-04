:hotel: [Return to Python Home Page](https://github.com/geophydog/Python/blob/master/README.md)

***

## code
```python
import sys, time

for i in range(10):
    s = '='*(i+1)
    p = (i+1)*10
    p = ' ' + str(p) + '%\r'
    if (i+1)*10 <100:
        sys.stdout.write(s + '>' + p)
        sys.stdout.flush()
        sys.stdout.write(s + '>' + p)
        sys.stdout.flush()
   else:
        sys.stdout.write(s + p)
    time.sleep(1)
```

## output
![process-bar-pic](https://github.com/geophydog/Python/blob/master/Images/process-bar.png)
