# Python 中的 random.getstate()

> 原文:[https://www.geeksforgeeks.org/random-getstate-in-python/](https://www.geeksforgeeks.org/random-getstate-in-python/)

random()模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## random.getstate()

随机模块的 getstate()方法返回一个具有随机数生成器当前内部状态的对象。可以将此对象传递给 setstate()方法来恢复状态。此方法中没有传递参数。
**例 1:**

## 蟒蛇 3

```py
import random

# remember this state
state = random.getstate()

# print 10 random numbers
print(random.sample(range(20), k = 10))

# restore state
random.setstate(state)

# print same first 5 random numbers
# as above
print(random.sample(range(20), k = 5))
```

**输出:**

```py
[16, 1, 0, 11, 19, 3, 7, 5, 10, 13]
[16, 1, 0, 11, 19]
```

**例 2:**

## 蟒蛇 3

```py
import random

list1 = [1, 2, 3, 4, 5, 6] 

# Get the state
state = random.getstate()

# prints a random value from the list
print(random.choice(list1))

# Set the state
random.setstate(state)

# prints the same random value
# from the list
print(random.choice(list1))
```

**输出:**

```py
3
3
```