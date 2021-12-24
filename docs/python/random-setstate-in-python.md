# Python 中的 random.setstate()

> 原文:[https://www.geeksforgeeks.org/random-setstate-in-python/](https://www.geeksforgeeks.org/random-setstate-in-python/)

`**Random**`模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## random.setstate()

`random`模块的`setstate()`方法与`getstate()`方法结合使用。使用`getstate()`方法捕获随机数发生器的状态后，使用`setstate()`方法将随机数发生器的状态恢复到指定状态。

`setstate()`方法需要一个状态对象作为参数，可以通过调用`getstate()`方法获得。

**例 1:**

```
# import the random module
import random

# capture the current state
# using the getstate() method
state = random.getstate()

# print a random number of the
# captured state
num = random.random()
print("A random number of the captured state: "+ str(num))

# print another random number
num = random.random()
print("Another random number: "+ str(num))

# restore the captured state
# using the setstate() method
# pass the captured state as the parameter
random.setstate(state)

# now printing the same random number
# as in the captured state
num = random.random()
print("The random number of the previously captured state: "+ str(num))
```

**输出:**

> 捕获状态的一个随机数:0.8059083574308233
> 另一个随机数:0.46568313950438245
> 之前捕获状态的随机数:0.805908233

**例 2:**

```
# import the random module
import random

list1 = [1, 2, 3, 4, 5]  

# capture the current state
# using the getstate() method
state = random.getstate()

# Prints list of random items of given length 
print(random.sample(list1, 3)) 

# restore the captured state
# using the setstate() method
# pass the captured state as the parameter
random.setstate(state)

# now printing the same list of random
# items
print(random.sample(list1, 3)) 
```

**输出:**

```
[5, 2, 4]
[5, 2, 4]
```