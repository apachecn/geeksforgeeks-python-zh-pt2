# Python 中的 random.paretovariate()函数

> 原文:[https://www . geeksforgeeks . org/random-paretovariate-function-in-python/](https://www.geeksforgeeks.org/random-paretovariate-function-in-python/)

`random`模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## random.paretovariate()

`**paretovariate()**`是`random`模块的内置方法。用于返回带有[帕累托分布](https://en.wikipedia.org/wiki/Pareto_distribution)的随机浮点数。

> **语法:** random.paretovariate(alpha)
> 
> **参数:**
> α:形状参数
> 
> **返回:**一个随机的帕累托分布浮点数

**例 1:**

```
# import the random module
import random

# determining the values of the parameter
alpha = 3

# using the paretovariate() method
print(random.paretovariate(alpha))
```

**输出:**

```
1.0333528834896462
```

**例 2:** 我们可以多次生成这个数，并绘制一个图来观察帕累托分布。

```
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a  
# list 
nums = [] 
alpha = 3

for i in range(100): 
    temp = random.paretovariate(alpha)
    nums.append(temp) 

# plotting a graph 
plt.plot(nums) 
plt.show()
```

**输出:**
![](img/1b6ce2ada1ca983ef5d138b5c7b49eb8.png)

**例 3:** 我们可以创建一个直方图来观察帕累托分布的密度。

```
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a list 
nums = [] 
alpha = 3

for i in range(10000): 
    temp = random.paretovariate(alpha) 
    nums.append(temp) 

# plotting a graph 
plt.hist(nums, bins = 200) 
plt.show()
```

**输出:**
![](img/1a1999df008f7e9189080f0097e02369.png)