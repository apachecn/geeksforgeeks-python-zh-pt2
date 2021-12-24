# Python–随机数求和

> 原文:[https://www . geesforgeks . org/python-随机数-求和/](https://www.geeksforgeeks.org/python-random-numbers-summation/)

有时，在制作游戏或赌博程序时，我们会遇到用随机数创建列表并进行求和的任务。这个任务通常必须使用循环执行，将随机数一个接一个地追加，然后执行求和。但是总是要求以最简洁的方式执行此操作。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `randrange() + sum()`**
执行这个特定任务的幼稚方法可以使用列表理解来缩短。randrange 函数用于执行生成随机数的任务。执行求和的任务是使用 sum()完成的。

```
# Python3 code to demonstrate 
# Random Numbers Summation
# using list comprehension + randrange() + sum()
import random

# using list comprehension + randrange() + sum()
# Random Numbers Summation
res = sum([random.randrange(1, 50, 1) for i in range(7)])

# printing result
print ("Random number summation list is : " + str(res))
```

**Output :**

```
Random number summation list is : 187

```