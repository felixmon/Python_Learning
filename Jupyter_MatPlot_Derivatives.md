Plot derivatives with Jupyter and Matplotlib

[reference 1 Stackoverflow](https://stackoverflow.com/a/31558968)  
[reference 2 socratic.org](https://socratic.org/questions/how-do-you-find-the-nth-derivative-of-the-function-f-x-x-n)  
[reference 3 scipy.org](https://docs.scipy.org/doc/scipy/reference/generated/scipy.misc.derivative.html)  
```python
%matplotlib inline
import matplotlib.pyplot as plt
import numpy as np
from scipy.misc import derivative
def f(x): return x**3+x**2
# Return evenly spaced numbers(-2,2) over a specified interval(100).
# linspace stands for Linear Space
xs=np.linspace(-5,5,100)
# scipy.misc.derivative(func, x0, dx=1.0, n=1, args=(), order=3)
# func: input function
# x0: The point at which the nth derivative is found.
# dx: spacing
# n: Order of the derivative. Default is 1.
derivative(f,1,dx=0.0001)
plt.plot(xs,f(xs))
plt.plot(xs,derivative(f,xs, dx=0.001))
# plt.gca gca means get current axe
ax = plt.gca()
ax.set_ylim(-5,5)
# set cross axis
ax.spines['left'].set_position('center')
ax.spines['bottom'].set_position('center')
# hide the borders
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
plt.savefig('temp.png')
```
