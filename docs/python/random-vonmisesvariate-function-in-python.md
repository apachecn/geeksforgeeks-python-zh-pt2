# Python 中的 random.vonmisesvariate()函数

> 原文:[https://www . geesforgeks . org/random-vonmisevariate-function-in-python/](https://www.geeksforgeeks.org/random-vonmisesvariate-function-in-python/)

`random`模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## 随机。多个()

`**vonmisesvariate()**`是`random`模块的内置方法。用于返回带有[冯米塞斯分布或圆形正态分布](https://en.wikipedia.org/wiki/Von_Mises_distribution)的随机浮点数。

> **语法:**random . vonmisevariate(mu，kappa)
> 
> **参数:**
> μ:平均角度，以 0 和 2 *π之间的弧度表示
> κ:浓度参数，大于或等于零
> 
> **返回:**一个随机的冯米塞斯分布浮点数

**例 1:**

```
# import the random module
import random

# determining the values of the parameters
mu = 0
kappa = 4

# using the vonmisesvariate() method
print(random.vonmisesvariate(mu, kappa))
```

**输出:**

```
0.9429600175580171
```

**例 2:** 我们可以多次生成这个数，并绘制一个图来观察冯米塞斯分布。

```
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a  
# list 
nums = [] 
mu = 0
kappa = 4

for i in range(100): 
    temp = random.vonmisesvariate(mu, kappa)
    nums.append(temp) 

# plotting a graph 
plt.plot(nums) 
plt.show()
```

**输出:**
![](img/34a1ec5b4fe5476ad8131a890d198a11.png)

**示例 3:** 我们可以创建一个直方图来观察冯米塞斯分布的密度。

```
# import the required libraries 
import random 
import matplotlib.pyplot as plt 

# store the random numbers in a list 
nums = [] 
mu = 0
kappa = 4

for i in range(10000): 
    temp = random.vonmisesvariate(mu, kappa) 
    nums.append(temp) 

# plotting a graph 
plt.hist(nums, bins = 200) 
plt.show()
```

**输出:**
![](img/9345a3c1fb6475e0d2774c4dc250d4d5.png)