# Python 中的随机数

> 原文:[https://www.geeksforgeeks.org/random-numbers-in-python/](https://www.geeksforgeeks.org/random-numbers-in-python/)

Python 定义了一组函数，用于通过**随机模块生成或操纵随机数。** 随机模块中的函数依赖于伪随机数生成器函数 **random()** 、，后者生成 0.0 到 1.0 之间的随机浮点数。这些特定类型的功能用于许多游戏、彩票或任何需要生成随机数的应用程序。

## 随机数运算

**1。**[**choice()**](https://www.geeksforgeeks.org/python-numbers-choice-function/)**:-choice()是Python 编程语言中的一个内置函数，它从列表、元组或字符串中返回一个随机项。**

****例:****

## **蟒蛇 3**

```py
# Python3 program to demonstrate the use of
# choice() method

# import random
import random

# prints a random value from the list
list1 = [1, 2, 3, 4, 5, 6]
print(random.choice(list1))

# prints a random item from the string
string = "striver"
print(random.choice(string))
```

****输出:****

```py
5
t
```

****2。** [**随机范围(beg，end，step)**](https://www.geeksforgeeks.org/randrange-in-python/) :-随机模块提供了一个可以从指定范围生成随机数的功能，还允许包含步骤的房间，称为 **随机范围()。****

****示例:****

## **计算机编程语言**

```py
# Python code to demonstrate the working of
# choice() and randrange()

# importing "random" for random operations
import random

# using choice() to generate a random number from a
# given list of numbers.
print("A random number from list is : ", end="")
print(random.choice([1, 4, 8, 10, 3]))

# using randrange() to generate in range from 20
# to 50\. The last parameter 3 is step size to skip
# three numbers when selecting.
print("A random number from range is : ", end="")
print(random.randrange(20, 50, 3))
```

****输出:****

```py
A random number from list is : 4
A random number from range is : 41
```

****3。random()** :-此方法用于生成一个小于 1 且大于等于 0 的**浮点数。****

****4。**[**seed()**](https://www.geeksforgeeks.org/random-seed-in-python/):-Seed 函数用于保存随机函数的状态，以便它可以在同一台机器或不同机器上多次执行代码时生成一些随机数(对于特定的 Seed 值)。种子值是生成器生成的前一个数值。第一次当没有以前的值时，它使用当前系统时间。**

****例:****

## **计算机编程语言**

```py
# Python code to demonstrate the working of
# random() and seed()

# importing "random" for random operations
import random

# using random() to generate a random number
# between 0 and 1
print("A random number between 0 and 1 is : ", end="")
print(random.random())

# using seed() to seed a random number
random.seed(5)

# printing mapped random number
print("The mapped random number with 5 is : ", end="")
print(random.random())

# using seed() to seed different random number
random.seed(7)

# printing mapped random number
print("The mapped random number with 7 is : ", end="")
print(random.random())

# using seed() to seed to 5 again
random.seed(5)

# printing mapped random number
print("The mapped random number with 5 is : ", end="")
print(random.random())

# using seed() to seed to 7 again
random.seed(7)

# printing mapped random number
print("The mapped random number with 7 is : ", end="")
print(random.random())
```

****输出:****

> **0 和 1 之间的一个随机数是:0。58860 . 88888888861**
> 
> **带有 5 的映射随机数是:0。58860 . 88888888861**
> 
> **带有 7 的映射随机数是:0。33230.27643333336**
> 
> **带有 5 的映射随机数是:0。58860 . 88888888861**
> 
> **带有 7 的映射随机数是:0。33230.27643333336**

****5。** [**洗牌()**](https://www.geeksforgeeks.org/random-shuffle-function-in-python/) :- 用于洗牌一个序列(列表)。洗牌意味着改变序列元素的位置。这里，洗牌操作是就位。**

****例:****

## **蟒蛇 3**

```py
# import the random module
import random

# declare a list
sample_list = ['A', 'B', 'C', 'D', 'E']

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

****输出:****

```py
Original list : 
['A', 'B', 'C', 'D', 'E']

After the first shuffle : 
['A', 'B', 'E', 'C', 'D']

After the second shuffle : 
['C', 'E', 'B', 'D', 'A']
```

****6。** [**制服(a，b)**](https://www.geeksforgeeks.org/python-number-uniform-method/) :-此函数用于在其参数中提到的数字之间生成一个**浮点随机数。**需要两个参数，下限(包含在生成中)和上限(不包含在生成中)。****** 

## **计算机编程语言**

```py
# Python code to demonstrate the working of
# shuffle() and uniform()

# importing "random" for random operations
import random

# Initializing list
li = [1, 4, 5, 10, 2]

# Printing list before shuffling
print("The list before shuffling is : ", end="")
for i in range(0, len(li)):
    print(li[i], end=" ")
print("\r")

# using shuffle() to shuffle the list
random.shuffle(li)

# Printing list after shuffling
print("The list after shuffling is : ", end="")
for i in range(0, len(li)):
    print(li[i], end=" ")
print("\r")

# using uniform() to generate random floating number in range
# prints number between 5 and 10
print("The random floating point number between 5 and 10 is : ", end="")
print(random.uniform(5, 10))
```

****输出:****

> **洗牌前的名单是:1 4 5 10 2**
> 
> **洗牌后的名单是:2 1 4 5 10**
> 
> **介于 5 和 10 之间的随机浮点数是:5。58860 . 88888888861**

**这篇文章是曼吉特·辛格写的。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**