# 在 Python 中混洗元组的方法

> 原文:[https://www . geesforgeks . org/how-to-shuffle-a-tuple in-python/](https://www.geeksforgeeks.org/ways-to-shuffle-a-tuple-in-python/)

在编程实践中，洗牌有时会很有帮助。这个过程可以直接在像列表这样可变的数据结构上实现，但是我们知道元组是不可变的，所以不能直接混洗。如果您尝试按照下面的代码进行操作，那么将会出现一个错误。让我们看看下面的例子。

## 蟒蛇 3

```
import random

# Initializing tuple
t = (1,2,3,4,5)

# Trying to shuffle using random.shuffle
random.shuffle(t)
```

**输出:**

```
TypeError: 'tuple' object does not support item assignment

```

那怎么进行呢？因此，有两种方法可以打乱元组，它们在下面提到:

**方法#1:** [**打字**](https://www.geeksforgeeks.org/type-conversion-python/)

这是一个在元组中进行洗牌的简单方法。您可以将元组类型转换为列表，然后对列表执行洗牌操作，然后将列表类型转换回元组。一种方法是使用 random.shuffle()。

## 蟒蛇 3

```
# Python3 code to demonstrate  
# shuffle a tuple  
# using random.shuffle() 
import random 

# initializing tuple
tup = (1,2,3,4,5)

# Printing original tuple
print("The original tuple is : " + str(tup))

# Conversion to list
l = list(tup)

# using random.shuffle() 
# to shuffle a list
random.shuffle(l)

# Converting back to tuple
tup = tuple(l)

# Printing shuffled tuple
print ("The shuffled tuple is : " + str(tup))
```

**输出:**

```
The original tuple is: (1, 2, 3, 4, 5)
The shuffled tuple is: (2, 3, 4, 1, 5)

```

**方法 2:使用** [**随机抽取()**](https://www.geeksforgeeks.org/python-random-sample-function/)

[random.sample()](https://www.geeksforgeeks.org/python-random-sample-function/) 创建一个新对象，即使一个元组作为第一个参数传递，它也会返回一个列表，因此作为最后一步，必须将列表转换回元组，以获得一个混洗的元组作为输出。

## 蟒蛇 3

```
# Python3 code to demonstrate  
# shuffle a tuple  
# using random.sample() 
import random 

# initializing tuple
tup = (1,2,3,4,5)

# Printing original tuple
print("The original tuple is : " + str(tup))

# Using random.sample(), passing the tuple and 
# the length of the datastructure as arguments
# and converting it back to tuple.
tup = tuple(random.sample(t, len(t)))

# Printing shuffled tuple
print ("The shuffled tuple is : " + str(tup))
```

**输出:**

```
The original tuple is: (1, 2, 3, 4, 5)
The shuffled tuple is: (1, 5, 3, 2, 4)

```