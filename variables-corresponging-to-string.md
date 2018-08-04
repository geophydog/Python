:hotel: [Return to Python Home Page](https://github.com/geophydog/Python)

***

### Problem description
```
现有一些列形式为"sin1, sin2, sin3, ..."长度为n的m个三角函数，且有"data = numpy.zeros((m, n))",  
欲将"sin1, sin2, sin3, ..."填充在"data"中，且有"data[0] = sin1, data[1] = sin2, data[2] = sin3, ...",  
但是我并不想多写代码，该如何解决？
```

*** 

### Problem solution

##### :one: Dictionary 方案
```python
dataDict = {'1': sin1, '2': sin2, "3": sin3, ...}
for i in range(m):
    iString = str(i+1)
    data[i] = dataDict[iString]
```

#### :two: Pythonic 方案
```python
import numpy as np

def addPara(para, **kwargs):
    para.update(kwargs)

t = np.linspace(0, 5, 6)
sin1 = np.sin(2*np.pi*t)
sin2 = np.sin(4*np.pi*t)
sin3 = np.sin(6*np.pi*t)

para = {}
addPara(para, f1 = sin1, f2 = sin2, f3 = sin3, ...}
print(para)
```
__output__
```
{'f1': array([  0.00000000e+00,  -2.44929360e-16,  -4.89858720e-16,
         -7.34788079e-16,  -9.79717439e-16,  -1.22464680e-15]),
 'f2': array([  0.00000000e+00,  -4.89858720e-16,  -9.79717439e-16,
         -1.46957616e-15,  -1.95943488e-15,  -2.44929360e-15]),
 'f3': array([  0.00000000e+00,  -7.34788079e-16,  -1.46957616e-15,
         -2.20436424e-15,  -2.93915232e-15,  -1.07793678e-14])}
```
