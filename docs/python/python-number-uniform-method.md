# Python 随机模块中的统一()方法

> 原文:[https://www.geeksforgeeks.org/python-number-uniform-method/](https://www.geeksforgeeks.org/python-number-uniform-method/)

uniform()是 Python 3 中随机库中指定的方法。

如今，一般来说，日复一日的任务中，总是需要生成一定范围内的随机数。正常的编程结构需要一个方法而不仅仅是一个单词来完成这个特殊的任务。在 python 中，有一个内置的方法“ **uniform()** ”可以轻松地执行这个任务，并且只使用一个单词。该方法在**随机**模块中定义

> 语法:**统一(int x，int y)**
> 
> **参数:**
> **x** 指定生成所需随机数的下限。
> **y** 指定生成所需随机数的上限。
> 
> **返回:**返回生成的下限和上限之间的浮点随机数

**代码#1 :** 代码生成浮点数。

```py
# Python3 code to demonstrate
# the working of uniform()

# for using uniform()
import random

# initializing bounds 
a = 4
b = 9

# printing the random number
print("The random number generated between 4 and 9 is : ", end ="")
print(random.uniform(a, b))
```

输出:

```py
The random number generated between 4 and 9 is : 7.494931618830411

```

**应用:**
可以想到这个功能有很多可能的应用，其中值得注意的是在赌场游戏、彩票或定制游戏中生成随机数。
下面是根据接近某个数值决定胜负的游戏。

**代码#2 :** 制服的应用()-一个游戏

```py
# Python3 code to demonstrate
# the application of uniform()

# for using uniform()
import random, math

# initializing player numbers
player1 = 4.50
player2 = 3.78
player3 = 6.54

# generating winner random number
winner = random.uniform(2, 9)

# finding closest 
diffa = math.fabs(winner - player1)
diffb = math.fabs(winner - player2)
diffc = math.fabs(winner - player3)

# printing winner
if(diffa < diffb and diffa < diffc):
    print("The winner of game is : ", end ="")
    print("Player1")

if(diffb < diffc and diffb < diffa):
    print("The winner of game is : ", end ="")
    print("Player2")

if(diffc < diffb and diffc < diffa):
    print("The winner of game is : ", end ="")
    print("Player3")
```

输出:

```py
The winner of game is : Player2

```