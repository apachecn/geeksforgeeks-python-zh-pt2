# Python 程序查找当前时间和给定时间的差异

> 原文:[https://www . geesforgeks . org/python-program-查找当前时间和给定时间之间的差异/](https://www.geeksforgeeks.org/python-program-to-find-difference-between-current-time-and-given-time/)

给定两个时间`h1:m1`和`h2:m2`，以 24 小时制表示小时和分钟。当前时钟时间由`h1:m1`给出。任务是计算分钟内两次的差值，并以`h:m`格式打印两次的差值。

**示例:**

> **输入:** h1=7，m1=20，h2=9，m2=45
> **输出:** 2 : 25
> 当前时间为 7 : 20，给定时间为 9 : 45。
> 两者相差 145 分钟。
> 转换为 h : m 格式后结果为 2 : 25。
> 
> **输入:** h1=15，m1=23，h2=18，m2 = 54
> T3】输出: 3 : 31
> 当前时间为 15 : 23，给定时间为 18 : 54。
> 两者相差 211 分钟。
> 转换为 h : m 格式后结果为 3 : 31。
> 
> **输入:** h1=16，m1=20，h2=16，m2=20
> **输出:**两次相同
> 当前时间为 16 : 20，给定时间也为 16 : 20。
> 两者相差 0 分钟。
> 由于差异为 0，我们打印“两者时间相同”。

**进场:**

*   将两个时间都转换为分钟
*   在几分钟内找出差异
*   如果差值为 0，则打印“两者时间相同”
*   否则将差异转换为 h : m 格式并打印

下面是实现。

```
# Python program to find the
# difference between two times

# function to obtain the time
# in minutes form
def difference(h1, m1, h2, m2):

    # convert h1 : m1 into
    # minutes
    t1 = h1 * 60 + m1

    # convert h2 : m2 into
    # minutes 
    t2 = h2 * 60 + m2

    if (t1 == t2): 
        print("Both are same times")
        return 
    else:

        # calculating the difference
        diff = t2-t1

    # calculating hours from
    # difference
    h = (int(diff / 60)) % 24

    # calculating minutes from 
    # difference
    m = diff % 60

    print(h, ":", m)

# Driver's code
if __name__ == "__main__":

    difference(7, 20, 9, 45)
    difference(15, 23, 18, 54)
    difference(16, 20, 16, 20)

# This code is contributed by SrujayReddy
```

**输出:**

```
2 : 25
3 : 31
Both are same times

```