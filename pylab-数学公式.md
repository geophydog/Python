:hotel: [Return to Python Home Page](https://github.com/geophydog/Python)

***

```python
from pylab import *

eqs = []
eqs.append((r'$  \bar{h} \int_{-\infty}^{\infty}f(x)e^{-i\omega x}dx $'))

axes([0.025, 0.025, 0.95, 0.95])

text(0.5, 0.85, eqs[0], ha='center', va='center', color='r', alpha=1, transform=gca().transAxes, fontsize=30, clip_on=True)
text(0.5, 0.5, eqs[0], ha='center', va='center', color='b', alpha=1, transform=gca().transAxes, fontsize=30, clip_on=True)
text(0.5, 0.2, eqs[0], ha='center', va='center', color='k', alpha=1, transform=gca().transAxes, fontsize=30, clip_on=True)

xticks([])
yticks([])
savefig('eqs.pdf', dpi=300) # .png .tif等格式皆可.
```

