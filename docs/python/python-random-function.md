# Python 随机–随机()函数

> 原文:[https://www.geeksforgeeks.org/python-random-function/](https://www.geeksforgeeks.org/python-random-function/)

**Python random.random()函数**生成 0 到 1 之间的随机浮点数。

> **语法:** random.random()
> 
> **参数:**此方法不接受任何参数。
> 
> **返回:**这个方法返回一个 0 到 1 之间的随机浮点数。

## Python random.random()方法示例

### **例 1:**sample()函数的简单实现。

## 蟒蛇 3

```
# Python3 program to demonstrate 
# the use of random() function . 

# import random  
from random import random 

# Prints random item 
print(random())
```

**输出:**

```
0.41941790721207284
```

### **示例 2: Python random.random 范围**

## 蟒蛇 3

```
# Python3 program to demonstrate
# the use of random() function . 

# import random  
from random import random

lst = []

for i in range(10):
  lst.append(random())

# Prints random items
print(lst)
```

**输出:**

> [0.12144204979175777, 0.27614050014306335, 0.8217122381411321, 0.34259785168486445, 0.6119383347065234, 0.8527573184278889, 0.9741465121560601, 0.21663626227016142, 0.9381166706029976, 0.2785298315133211]

### 示例 3: Python random.random()种子

## 蟒蛇 3

```
import random

random.seed(10)
print(random.random())
```

**输出:**

```
0.5714025946899135
```