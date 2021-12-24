# Python–统计中的三角分布

> 原文:[https://www . geesforgeks . org/python-三角形-统计中的分布/](https://www.geeksforgeeks.org/python-triangular-distribution-in-statistics/)

**scipy.stats.triang ()** 是一个三角形连续随机变量。它继承自泛型方法的，作为 **rv_continuous 类**的实例。它用特定于这个特定分布的细节来完成这些方法。

**参数:**

> **q :** 上下尾概率
> T3】x:分位数
> **loc :** 【可选】位置参数。默认= 0
> **比例:**【可选】比例参数。默认值= 1
> **大小:**【整数元组，可选】形状或随机变量。
> **时刻:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**三角形连续随机变量

**代码#1:创建三角形连续随机变量**

```py
# importing library

from scipy.stats import triang 

numargs = triang .numargs 
a = 0.158
rv = triang (a) 

print ("RV : \n", rv)  
```

**输出:**

```py
RV : 
 scipy.stats._distn_infrastructure.rv_frozen object at 0x000002A9D843A9C8

```

**代码#2:三角形连续变量和概率分布**

```py
import numpy as np 
quantile = np.arange (0.01, 1, 0.1) 

# Random Variates 
R = triang .rvs(0.158, size = 10) 
print ("Random Variates : \n", R) 

# PDF 
x = np.linspace(0, 5, 10) 
R = triang.pdf(x, 1)
print ("\nProbability Distribution : \n", R) 
```

**输出:**

```py
Random Variates : 
 [0.83667827 0.23988855 0.17637281 0.28973544 0.26458145 0.3554613
 0.09420123 0.20821321 0.3357951  0.1249713 ]

Probability Distribution : 
 [0\.         1.11111111 0\.         0\.         0\.         0.
 0\.         0\.         0\.         0\.        ]

```

**代码#3:图形表示。**

```py
import numpy as np 
import matplotlib.pyplot as plt 

distribution = np.linspace(0, np.minimum(rv.dist.b, 3)) 
print("Distribution : \n", distribution) 

plot = plt.plot(distribution, rv.pdf(distribution)) 
```

**输出:**

```py
Distribution : 
 [0\.         0.02040816 0.04081633 0.06122449 0.08163265 0.10204082
 0.12244898 0.14285714 0.16326531 0.18367347 0.20408163 0.2244898
 0.24489796 0.26530612 0.28571429 0.30612245 0.32653061 0.34693878
 0.36734694 0.3877551  0.40816327 0.42857143 0.44897959 0.46938776
 0.48979592 0.51020408 0.53061224 0.55102041 0.57142857 0.59183673
 0.6122449  0.63265306 0.65306122 0.67346939 0.69387755 0.71428571
 0.73469388 0.75510204 0.7755102  0.79591837 0.81632653 0.83673469
 0.85714286 0.87755102 0.89795918 0.91836735 0.93877551 0.95918367
 0.97959184 1\.        ]

```

![](img/427ae732e6892eff28933da7c98bc901.png)

**代码#4:变化的位置参数**

```py
import matplotlib.pyplot as plt 
import numpy as np 

x = np.linspace(0, 5, 100) 

# Varying positional arguments 
y1 = triang  .pdf(x, 1, 3, 5) 
y2 = triang  .pdf(x, 1, 4, 4) 
plt.plot(x, y1, "*", x, y2, "r--") 
```

**输出:**
![](img/9370bf46388035f045d6cffa7f56b164.png)