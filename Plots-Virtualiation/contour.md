:hotel:[Return to Python Home Page](https://github.com/geophydog/Python)

***

# Question Discription
```
在GM地球物理常用绘图软件）中， 我们可以先用‘xyz2grd’将如(x, y, value)这样格式的文本文件转化成二进制grid网格文件，
再用'grdiamge'命令画等值线图。 python中matplotlib.pyplot也可以做相应的事情。
```

***

# Demo
```python
import matplotlib.pyplot as plt
import numpy as np

def f(x, y):
  return (-x/2+x**5+y**3)*np.exp(-x**2-y**2)

x = np.linspace(-3, 3, 601)
y = np.linspace(-3, 3, 601)

X, Y = np.meshgrid(x, y)

plt.contour(X, Y, f(X, Y), alpha=0.75, cmap=plt.cm.rainbow)
plt.show()
```

![Demo]()
