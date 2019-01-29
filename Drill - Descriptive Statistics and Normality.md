

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
```


```python
binomial = np.random.binomial(20, .5, 100)
plt.hist(binomial)
plt.show()
```


![png](output_1_0.png)



```python
gamma = np.random.gamma(5, 1, 100)
plt.hist(gamma)
plt.show()
```


![png](output_2_0.png)



```python
poisson = np.random.poisson(1, 100)
plt.hist(poisson)
plt.show()
```


![png](output_3_0.png)



```python
normal = np.random.normal(20, 1, 100)
plt.hist(normal)
plt.show()
```


![png](output_4_0.png)



```python
uniform = np.random.uniform(1, 300, 100)
plt.hist(uniform)
plt.show()
```


![png](output_5_0.png)



```python
rayleigh = np.random.rayleigh(1, 100)
plt.hist(rayleigh)
plt.show()
```


![png](output_6_0.png)



```python
def v_lines(x, name):
    plt.hist(x, bins=20, color='c')
    plt.axvline(x.mean(), color = 'b', linestyle='solid', linewidth=2)
    plt.axvline(x.mean() + x.std(), color='b', linestyle='dashed', linewidth=2)
    plt.axvline(x.mean() - x.std(), color='b', linestyle='dashed', linewidth=2)
    plt.title(name)
    plt.show()
    
    
```


```python
v_lines(binomial, 'binomial')
v_lines(poisson, 'poisson')
v_lines(gamma, 'gamma')
v_lines(normal, 'normal')
v_lines(uniform, 'uniform')
v_lines(rayleigh,'rayleigh')
```


![png](output_8_0.png)



![png](output_8_1.png)



![png](output_8_2.png)



![png](output_8_3.png)



![png](output_8_4.png)



![png](output_8_5.png)


when considering the distribution of the binomial graph and the assumed 68% of values coming from within the 1 std of the mean makes it seem like that calcuation wouldn't apply. In fact the only one that would, it seems, would be the normal distribution histogram.


```python
normal1 = np.random.normal(5, .5, 100)
normal2 = np.random.normal(10, 1, 100)

normal3 = normal1 + normal2

plt.hist(normal3)
```




    (array([ 5.,  6., 13., 11., 15., 24., 16.,  5.,  1.,  4.]),
     array([12.92374574, 13.37541387, 13.82708201, 14.27875014, 14.73041828,
            15.18208641, 15.63375455, 16.08542268, 16.53709082, 16.98875895,
            17.44042709]),
     <a list of 10 Patch objects>)




![png](output_10_1.png)



```python
v_lines(normal3, 'normal 3')
```


![png](output_11_0.png)


the distribution of values doesn't seem to match the same 68% distribution as described in the beginning of the chapter
