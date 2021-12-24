# Python 程序求最小转数获取实际字符串

> 原文:[https://www . geesforgeks . org/python-程序-查找-最小旋转数-获取-实际-字符串/](https://www.geeksforgeeks.org/python-program-to-find-minimum-number-of-rotations-to-obtain-actual-string/)

给定两个字符串 s1 和 s2。任务是找出给定字符串 s1 的最小字符串旋转次数，以获得实际的字符串 s2。

**示例:**

```py
Input : eeksg, geeks
Output: 1 
Explanation: g is rotated left to obtain geeks.

Input : eksge, geeks
Output: 2
Explanation : e and g are left rotated to obtain geeks.

```

**进场:**

*   使用字符串切片来旋转字符串。
*   对字符串执行右旋转`str1=str1[1:len(str1)]+str1[0]`以获得实际字符串。
*   对字符串执行左旋转`m=m[len(m)-1]+m[:len(m)-1]`以获得实际字符串。
*   打印左(x)和右(y)旋转的最小值。

**时间复杂度:** `O(n)`

下面是实现:

```py
def findRotations(str1, str2):

    # To count left rotations 
    # of string
    x = 0

    # To count right rotations
    # of string
    y = 0
    m = str1

    while True:

        # left rotating the string
        m = m[len(m)-1] + m[:len(m)-1] 

        # checking if rotated and 
        # actual string are equal.
        if(m == str2):
            x += 1
            break

        else:
            x += 1
            if x > len(str2) :
                break

    while True:

        # right rotating the string
        str1 = str1[1:len(str1)]+str1[0] 

        # checking if rotated and actual
        # string are equal.
        if(str1 == str2):
            y += 1
            break

        else:
            y += 1
            if y > len(str2):
                break

    if x < len(str2):

        # printing the minimum
        # number of rotations.
        print(min(x,y))

    else:
        print("given strings are not of same kind")

# Driver code
findRotations('sgeek', 'geeks')
```

**Output:**

```py
1

```