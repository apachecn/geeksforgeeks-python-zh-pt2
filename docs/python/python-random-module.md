# Python 随机模块

> 原文:[https://www.geeksforgeeks.org/python-random-module/](https://www.geeksforgeeks.org/python-random-module/)

Python **随机模块**是 Python 的内置模块，用于生成随机数。这些是伪随机数，意味着它们不是真正随机的。该模块可用于执行随机操作，如生成随机数、为列表或字符串打印随机值等。

**示例:**从列表中打印随机值

## 蟒蛇 3

```
# import random
import random

# prints a random value from the list
list1 = [1, 2, 3, 4, 5, 6]
print(random.choice(list1))
```

**输出:**

```
2
```

如上所述，随机模块创建伪随机数。随机数取决于种子值。例如，如果播种值是 5，那么下面程序的输出将总是相同的。

**示例:**用种子值创建随机数

## 蟒蛇 3

```
import random

random.seed(5)

print(random.random())
print(random.random())
```

**输出:**

```
0.6229016948897019
0.7417869892607294
```

上述代码的输出将始终相同。因此，不得用于加密。

让我们讨论本模块执行的一些常见操作。

## 创建随机整数

[random.randint()](https://www.geeksforgeeks.org/python-randint-function/) 方法用于生成给定范围之间的随机整数。

**语法:**

```
randint(start, end)
```

**示例:**创建随机整数

## 蟒蛇 3

```
# Python3 program explaining work
# of randint() function

# import random module
import random

# Generates a random number between
# a given positive range
r1 = random.randint(5, 15)
print("Random number between 5 and 15 is % s" % (r1))

# Generates a random number between
# two given negative range
r2 = random.randint(-10, -2)
print("Random number between -10 and -2 is % d" % (r2))
```

**输出:**

```
Random number between 5 and 15 is 7
Random number between -10 and -2 is -9
```

## 创建随机浮动

[random.random()](https://www.geeksforgeeks.org/random-random-function-in-python/) 方法用于生成 0.0 到 1 之间的随机浮点数。

**语法:**

```
random.random()
```

**示例:**

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
0.3717933555623072
```

## 选择随机元素

[random.choice()](https://www.geeksforgeeks.org/python-numbers-choice-function/) 函数用于从列表、元组或字符串中返回随机项。

**语法:**

```
random.choice(sequence)
```

**示例:**从列表、字符串和元组中选择随机元素

## 蟒蛇 3

```
# Python3 program to demonstrate the use of
# choice() method

# import random
import random

# prints a random value from the list
list1 = [1, 2, 3, 4, 5, 6]
print(random.choice(list1))

# prints a random item from the string
string = "geeks"
print(random.choice(string))

# prints a random item from the tuple
tuple1 = (1, 2, 3, 4, 5)
print(random.choice(tuple1))
```

**输出:**

```
2
k
5
```

## 洗牌列表

[random.shuffle()](https://www.geeksforgeeks.org/random-shuffle-function-in-python/) 方法用于对序列(列表)进行洗牌。洗牌意味着改变序列元素的位置。这里，洗牌操作正在进行。

**语法:**

```
random.shuffle(sequence, function)
```

**示例:**重排列表

## 蟒蛇 3

```
# import the random module
import random

# declare a list
sample_list = [1, 2, 3, 4, 5]

print("Original list : ")
print(sample_list)

# first shuffle
random.shuffle(sample_list)
print("\nAfter the first shuffle : ")
print(sample_list)

# second shuffle
random.shuffle(sample_list)
print("\nAfter the second shuffle : ")
print(sample_list)
```

**输出:**

```
Original list : 
[1, 2, 3, 4, 5]

After the first shuffle : 
[4, 3, 5, 2, 1]

After the second shuffle : 
[1, 3, 4, 5, 2]
```

## 随机模块中所有功能的列表

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| [种子()](https://www.geeksforgeeks.org/random-seed-in-python/) | 初始化随机数生成器 |
| [getstate（）](https://www.geeksforgeeks.org/random-getstate-in-python/) | 返回一个具有随机数生成器当前内部状态的对象 |
| set state() | 用于将随机数生成器的状态恢复到指定状态 |
| [彩现位元()](https://www.geeksforgeeks.org/random-getrandbits-in-python/) | 返回具有指定位数的整数 |
| [边缘范围()](https://www.geeksforgeeks.org/randrange-in-python/) | 返回范围内的随机数 |
| [边缘()](https://www.geeksforgeeks.org/python-randint-function/) | 返回范围内的随机整数 |
| [选择()](https://www.geeksforgeeks.org/python-numbers-choice-function/) | 从列表、元组或字符串中返回随机项 |
| [选择()](https://www.geeksforgeeks.org/random-choices-method-in-python/) | 通过替换从列表中返回多个随机元素 |
| [样品()](https://www.geeksforgeeks.org/python-random-sample-function/) | 返回从序列中选择的特定长度的项目列表 |
| [随机()](https://www.geeksforgeeks.org/random-random-function-in-python/) | 生成随机浮点数 |
| [制服()](https://www.geeksforgeeks.org/python-number-uniform-method/) | 返回两个数字之间的随机浮点数，包括两个数字 |
| [三角形()](https://www.geeksforgeeks.org/random-triangular-method-in-python/) | 返回一个范围内的随机浮点数，偏向一个极端 |
| [βvariate()](https://www.geeksforgeeks.org/random-betavariate-method-in-python/) | 返回一个带有 beta 分布的随机浮点数 |
| [指数()](https://www.geeksforgeeks.org/random-expovariate-function-in-python/) | 返回一个指数分布的随机浮点数 |
| [gamma variable()](https://www.geeksforgeeks.org/random-gammavariate-function-in-python/) | 返回伽玛分布的随机浮点数 |
| [高斯()](https://www.geeksforgeeks.org/random-gauss-function-in-python/) | 返回高斯分布的随机浮点数 |
| [对数变异()](https://www.geeksforgeeks.org/random-lognormvariate-function-in-python/) | 返回一个对数正态分布的随机浮点数 |
| 常变型() | 返回一个正态分布的随机浮点数 |
| [杂项()](https://www.geeksforgeeks.org/random-vonmisesvariate-function-in-python/) | 返回具有冯米塞斯分布或循环正态分布的随机浮点数 |
| [paretovariate()](https://www.geeksforgeeks.org/random-paretovariate-function-in-python/) | 返回一个具有帕累托分布的随机浮点数 |
| [威布尔变量()](https://www.geeksforgeeks.org/random-weibullvariate-function-in-python/) | 返回具有威布尔分布的随机浮点数 |

</figure>