# Python 中的 random.lognormvariate()函数

> 原文:[https://www . geesforgeks . org/random-lognormvariate-function-in-python/](https://www.geeksforgeeks.org/random-lognormvariate-function-in-python/)

`random`模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## random.lognormvariate()

`**lognormvariate()**`是`random`模块的内置方法。用于返回一个具有[对数正态分布](https://en.wikipedia.org/wiki/Log-normal_distribution)的随机浮点数。

> **语法:**random . lognormvvariate(mu，sigma)
> 
> **参数:**
> μ:均值
> σ:标准差，大于 0
> 
> **返回:**一个随机对数正态分布浮点数

**例 1:**

```py
# import the random module
import random

# determining the values of the parameters
mu = 0
sigma = 0.25

# using the lognormvariate() method
print(random.lognormvariate(mu, sigma))
```

**输出:**

```py
0.8585439051088984
```

**例 2:** 我们可以多次生成这个数，并绘制一个图来观察对数正态分布。

```py
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a  
# list 
nums = [] 
mu = 0
sigma = 0.25

for i in range(100): 
    temp = random.lognormvariate(mu, sigma)
    nums.append(temp) 

# plotting a graph 
plt.plot(nums) 
plt.show()
```

**输出:**
![](img/507b7ac685baacf02827e052bd239e06.png)

**例 3:** 我们可以创建一个直方图来观察对数正态分布的密度。

```py
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a list 
nums = [] 
mu = 0
sigma = 0.25

for i in range(10000): 
    temp = random.lognormvariate(mu, sigma) 
    nums.append(temp) 

# plotting a graph 
plt.hist(nums, bins = 200) 
plt.show()
```

**输出:**
![](img/bdd4e3e7b696d2b19535049ced861eaf.png)