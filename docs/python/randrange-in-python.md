# Python 中的 randrange()

> 原文:[https://www.geeksforgeeks.org/randrange-in-python/](https://www.geeksforgeeks.org/randrange-in-python/)

生成随机数一直是一个重要的应用，在日常生活中有很多用途。Python 提供了一个功能，可以从指定的范围生成随机数，还允许包含步骤的房间，在**随机**模块中称为**随机范围()**。本文将进一步讨论这个函数。

```py
Syntax : 
random.randrange(start(opt),stop,step(opt))
Parameters :
start(opt) : Number consideration for generation starts from this,
default value is 0\. This parameter is optional.
stop : Numbers less than this are generated. This parameter is mandatory.
step(opt) : Step point of range, this won't be included. This is optional.
Default value is 1.
Return Value : 
This function generated the numbers in the sequence start-stop skipping step.
Exceptions :
Raises ValueError if stop <= start and number is non- integral.

```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# randrange()

import random

# Using randrange() to generate numbers from 0-100
print ("Random number from 0-100 is : ",end="")
print (random.randrange(100))

# Using randrange() to generate numbers from 50-100
print ("Random number from 50-100 is : ",end="")
print (random.randrange(50,100))

# Using randrange() to generate numbers from 50-100
# skipping 5
print ("Random number from 50-100 skip 5 is : ",end="")
print (random.randrange(50,100,5))
```

输出:

```py
Random number from 0-100 is : 26
Random number from 50-100 is : 58
Random number from 50-100 skip 5 is : 90

```

**Exceptions**

**1。值错误–浮点值**

## 蟒蛇 3

```py
# Python code to demonstrate the Exception of
# randrange(), ValueError, Float value

import random

# Using randrange() to generate numbers from 14.5-100
# Raises Exception
print ("Random number from 14.5-100 is : ",end="")
print (random.randrange(14.5,100))
```

输出:

```py
Random number from 14.5-100 is : 

```

运行时错误:

```py
Traceback (most recent call last):
  File "/home/5e40f42505a6926d0c75a09bec1279d9.py", line 9, in 
    print (random.randrange(14.5,100))
  File "/usr/lib/python3.5/random.py", line 182, in randrange
    raise ValueError("non-integer arg 1 for randrange()")
ValueError: non-integer arg 1 for randrange()

```

2.**值错误–启动> =停止**

## 蟒蛇 3

```py
# Python code to demonstrate the Exception of
# randrange(), ValueError, start >= start

import random

# Using randrange() to generate numbers from 500-100
# Raises Exception
print ("Random number from 500-100 is : ",end="")
print (random.randrange(500,100))
```

输出:

```py
Random number from 500-100 is : 

```

运行时错误:

```py
Traceback (most recent call last):
  File "/home/ea327cf3f1dd801a66a185d101c5cb13.py", line 9, in 
    print (random.randrange(500,100))
  File "/usr/lib/python3.5/random.py", line 196, in randrange
    raise ValueError("empty range for randrange() (%d,%d, %d)" % (istart, istop, width))
ValueError: empty range for randrange() (500,100, -400)

```

**Practical Application**

生成随机数一直是一个重要的应用，并且已经在**许多赌场游戏中使用，对于许多像 ludo 等使用骰子概念的儿童游戏**的赌博。**下面的代码描述了一个简短的游戏，关于谁先赢 100 场。每个玩家可以得到 1-10 个数字的骰子，也就是说，每回合可以得到 1-10 个数字。**。

## 蟒蛇 3

```py
# Python code to demonstrate the Application of
# randrange()

import random

sum = 0
sum1 = 0
count = 0
flag = 0

while(1):

    # generate random number at each turn 1-10
    r1 = random.randrange(1,10)
    r2 = random.randrange(1,10)

    # adding to account of players
    sum = sum + r1
    sum1 = sum1 + r2
    count = count+1

    print ("Total score of Player 1 after turn %d is :  %d " % (count,sum))

    # break when player 1 reaches 100
    if(sum>=100):
      flag=1
      break
    print ("Total score of Player 2 after turn %d is :  %d" % (count,sum1))

    # break when player 2 reaches 100
    if(sum1>=100):
      flag=2
      break

if(flag==1):
   print("\nPlayer 1 wins the game")
else :
   print("\nPlayer 2 wins the game")  
```

**Output**

```py
Total score of Player 1 after turn 1 is :  8 
Total score of Player 2 after turn 1 is :  4
Total score of Player 1 after turn 2 is :  13 
Total score of Player 2 after turn 2 is :  8
Total score of Player 1 after turn 3 is :  22 
Total score of Player 2 after turn 3 is :  16
Total score of Player 1 after turn 4 is :  28 
Total score of Player 2 after turn 4 is :  22
Total score of Player 1 after turn 5 is :  33 
Total score of Player 2 after turn 5 is :  27
Total score of Player 1 after turn 6 is :  35 
Total score of Player 2 after turn 6 is :  33
Total score of Player 1 after turn 7 is :  36 
Total score of Player 2 after turn 7 is :  42
Total score of Player 1 after turn 8 is :  38 
Total score of Player 2 after turn 8 is :  50
Total score of Player 1 after turn 9 is :  45 
Total score of Player 2 after turn 9 is :  55
Total score of Player 1 after turn 10 is :  48 
Total score of Player 2 after turn 10 is :  61
Total score of Player 1 after turn 11 is :  54 
Total score of Player 2 after turn 11 is :  64
Total score of Player 1 after turn 12 is :  57 
Total score of Player 2 after turn 12 is :  70
Total score of Player 1 after turn 13 is :  66 
Total score of Player 2 after turn 13 is :  73
Total score of Player 1 after turn 14 is :  72 
Total score of Player 2 after turn 14 is :  75
Total score of Player 1 after turn 15 is :  79 
Total score of Player 2 after turn 15 is :  76
Total score of Player 1 after turn 16 is :  81 
Total score of Player 2 after turn 16 is :  77
Total score of Player 1 after turn 17 is :  89 
Total score of Player 2 after turn 17 is :  81
Total score of Player 1 after turn 18 is :  95 
Total score of Player 2 after turn 18 is :  90
Total score of Player 1 after turn 19 is :  97 
Total score of Player 2 after turn 19 is :  99
Total score of Player 1 after turn 20 is :  102 

Player 1 wins the game

```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。