# Python 中什么时候用 yield 代替 return？

> 原文:[https://www . geesforgeks . org/use-yield-keyword-代替-return-keyword-python/](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)

yield 语句暂停函数的执行，并将一个值发送回调用方，但保留足够的状态，使函数能够从停止的地方恢复。恢复后，该函数将在最后一次产量运行后立即继续执行。这允许它的代码随着时间产生一系列值，而不是一次计算它们，然后像列表一样发送回来。

我们用一个例子来看看:

```py
# A Simple Python program to demonstrate working
# of yield

# A generator function that yields 1 for the first time,
# 2 second time and 3 third time
def simpleGeneratorFun():
    yield 1
    yield 2
    yield 3

# Driver code to check above generator function
for value in simpleGeneratorFun(): 
    print(value)
```

输出:

```py
1
2
3
```

**Return** 将指定的值发送回调用者，而 **Yield** 可以产生一系列的值。当我们想要迭代一个序列，但不想将整个序列存储在内存中时，应该使用 yield。

产量用于 Python **生成器**。生成器函数的定义类似于普通函数，但是每当它需要生成一个值时，它都使用 yield 关键字，而不是 return。如果 def 的主体包含 yield，则该函数自动成为生成器函数。

```py
# A Python program to generate squares from 1
# to 100 using yield and therefore generator

# An infinite generator function that prints
# next square number. It starts with 1
def nextSquare():
    i = 1

    # An Infinite loop to generate squares 
    while True:
        yield i*i                
        i += 1  # Next execution resumes 
                # from this point     

# Driver code to test above generator 
# function
for num in nextSquare():
    if num > 100:
         break    
    print(num)
```

输出:

```py
1
4
9
16
25
36
49
64
81
100
```

本文由 **Arpit Agarwal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论