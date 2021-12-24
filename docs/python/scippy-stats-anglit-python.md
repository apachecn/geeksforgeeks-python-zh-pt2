# scippy stats . angit()| python

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scippy-stats-English-python/

**scipy.stats.anglit()** 是一个 anglit 连续随机变量，用标准格式和一些形状参数定义，以完成其规格。

![](img/c28209ac4faafc1774e38200cee929d1.png)

> **参数:**
> **q :** 上下尾概率
> **x :** 分位数
> **loc :** 【可选】位置参数。默认= 0
> **比例:**【可选】比例参数。默认值= 1
> **大小:**【整数元组，可选】形状或随机变量。
> **瞬间:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**为连续随机变量

**代码#1:创建一个连续的随机变量**

```
# import scipy
from scipy.stats import anglit

numargs = anglit.numargs
[ ] = [0.6, ] * numargs
rv = anglit()

print ("RV : \n", rv)
```

**输出:**

```
RV :  
<scipy.stats._distn_infrastructure.rv_frozen object at 0x0000029484AA02E8>
```

**代码#2:英国随机变量和概率分布函数。**

```
import numpy as np
quantile = np.arange (0.01, 1, 0.1)

# Random Variates
R = anglit.rvs(scale = 2,  size = 10)
print ("Random Variates : \n", R)

# PDF
R = anglit.pdf(quantile, loc = 0, scale = 1)
print ("\nProbability Distribution : \n", R)
```

**输出:**

```
Random Variates : 
 [-0.73702502 -1.38273136  0.39618481 -0.48434091 -0.85635192 -0.36402882
 -0.21016273  0.53857078  0.96918022 -0.84314795]

Probability Distribution : 
 [0.99980001 0.97589745 0.91308894 0.81387846 0.68222121 0.52336595
 0.34364575 0.15022547 0\.         0\.        ]

```

**代码#3:图形表示。**

```
import numpy as np
import matplotlib.pyplot as plt

distribution = np.linspace(0, np.minimum(rv.dist.b, 5))
print("Distribution : \n", distribution)

plot = plt.plot(distribution, rv.pdf(distribution))
```

**输出:**

```
Distribution : 
 [0\.         0.01602853 0.03205707 0.0480856  0.06411414 0.08014267
 0.0961712  0.11219974 0.12822827 0.14425681 0.16028534 0.17631387
 0.19234241 0.20837094 0.22439948 0.24042801 0.25645654 0.27248508
 0.28851361 0.30454214 0.32057068 0.33659921 0.35262775 0.36865628
 0.38468481 0.40071335 0.41674188 0.43277042 0.44879895 0.46482748
 0.48085602 0.49688455 0.51291309 0.52894162 0.54497015 0.56099869
 0.57702722 0.59305576 0.60908429 0.62511282 0.64114136 0.65716989
 0.67319843 0.68922696 0.70525549 0.72128403 0.73731256 0.7533411
 0.76936963 0.78539816]
```

![](img/9d680dc498f386be8902fc61e4ff4a3a.png)

**代码#4:变化的位置参数**

```
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 5, 100)

# Varying positional arguments
y1 = anglit.pdf(x, 1, 6)
y2 = anglit.pdf(x, 1, 4)
plt.plot(x, y1, "*", x, y2, "r--")
```

**输出:**
![](img/0962b3f1afc0aac4e2ee6cbf18de0cee.png)