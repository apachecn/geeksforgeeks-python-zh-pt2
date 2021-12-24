# Python 程序打印数字图案

> 原文:[https://www . geesforgeks . org/python-程序到打印数字模式/](https://www.geeksforgeeks.org/python-program-to-print-digit-pattern/)

程序必须接受一个整数 **N** 作为输入。程序必须打印出示例输入/输出中所示的所需图案。

**示例:**

> **输入:** 41325
> **输出:**
> | * * *
> | *
> | * * *
> | * *
> | * * *
> **说明:**对于给定的整数，打印相当于整数中每个数字的*数。这里第一个数字是 4，所以在第一行打印四个。第二个数字是 1，所以打印一个*。以此类推，最后一位，即第五位数字是 5，因此在第五行打印五个。
> 
> **输入:** 60710
> **输出:**
> | * * * * *
> |
> | * * * * * * *
> | *
> |

**接近**
读取输入
对于整数中的每个数字，打印相应的*s 数
如果数字为 0，则打印 no *s 并跳到下一行

```
# function to print the pattern
def pattern(n):

    # traverse through the elements
    # in n assuming it as a string
    for i in n:

        # print | for every line
        print("|", end = "")

        # print i number of * s in 
        # each line
        print("*" * int(i))

# get the input as string        
n = "41325"
pattern(n)
```

**Output:**

```
|****
|*
|***
|**
|*****

```

 **以整数为输入的交替解:**

```
n = 41325
x = []
while n>0:
    x.append(n%10)
    n //= 10
for i in range(len(x)-1,-1,-1):
    print('|'+x[i]*'*')

# code contributed by Baivab Dash
```

**Output:**

```
|****
|*
|***
|**
|*****

```