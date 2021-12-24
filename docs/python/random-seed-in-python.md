# Python 中的 random.seed()

> 原文:[https://www.geeksforgeeks.org/random-seed-in-python/](https://www.geeksforgeeks.org/random-seed-in-python/)

**`random()`** 功能是用 Python 生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

`random()`函数为某些值生成数字。这个值也叫*种子*值。

**种子功能是如何工作的？**
Seed 函数用于保存随机函数的状态，这样它就可以在同一台机器或不同机器上多次执行代码时生成相同的随机数(对于特定的 Seed 值)。种子值是生成器生成的前一个数值。第一次当没有以前的值时，它使用当前系统时间。

**使用`random.seed()`功能**

在这里，我们将看到如何使用相同的种子值每次生成相同的随机数。

**例 1:**

```py
# random module is imported
import random 
for i in range(5):

    # Any number can be used in place of '0'.
    random.seed(0)

    # Generated random number will be between 1 to 1000.
    print(random.randint(1, 1000))  

```

**Output:**

```py
865
865
865
865
865

```

**例 2:**

```py
# importing random module
import random

random.seed(3)

# print a random number between 1 and 1000.
print(random.randint(1, 1000))

# if you want to get the same random number again then,
random.seed(3) 
print(random.randint(1, 1000))

# If seed function is not used

# Gives totally unpredictable responses.
print(random.randint(1, 1000))
```

**Output:**

```py
244
244
607

```

执行上述代码时，上述两个 print 语句将生成响应 *244* ，但第三个 print 语句给出了不可预测的响应。

**随机种子()的用途**

1.  这用于生成伪随机加密密钥。加密密钥是计算机安全的重要组成部分。这些是用于保护数据免受未经授权的互联网访问的密钥。
2.  在使用随机数进行测试的情况下，它使代码的优化变得容易。代码的输出有时取决于输入。因此，使用随机数测试算法可能会很复杂。种子函数还用于一次又一次地生成相同的随机数，简化了算法测试过程。