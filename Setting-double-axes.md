:hotel: [Return to Python Home Page](https://github.com/geophydog/Python)

***

## code
```pyton
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0.0001, np.e, 101)
y1 = np.exp(-x)
y2 = np.log(x)

fig = plt.figure()
ax1 = fig.add_subplot(111)
ax1.plot(x, y1, 'r')
ax1.set_xlabel('x axis')
ax1.set_ylabel(r'e^x')
#ax1.set_title('Double Y axes')

ax2 = ax1.twinx() # this function is the key to setting double axes; ax2.twiny(): set double x axes.
ax2.plot(x, y2, 'b')
ax2.set_ylabel(r'lin(x)')

plt.show()
```

## output
![double-axes-python](https://github.com/geophydog/Python/blob/master/Images/double-y-axis.png)
