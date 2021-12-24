# Python |合并两个带后缀和前缀的字符串

> 原文:[https://www . geesforgeks . org/python-合并-带后缀和前缀的两个字符串/](https://www.geeksforgeeks.org/python-merging-two-strings-with-suffix-and-prefix/)

给定两个字符串 *A* 和 *B* ，这些字符串包含小写字母。任务是告诉合并字符串的长度。例如，假设 *A 是“abcde”*， *B 是“CDE fg”*，那么合并这两个字符串会得到“abcdefg”。合并操作以这样的方式执行，即连接字符既是 A 的*后缀，也是 B* 的*前缀。
在合并之前，您可以执行以下任一操作:*

1.  反向字符串 A
2.  反向字符串 B

**示例:**

```py
Input :
A = "ababc"
B = "bcabc" 
Output :
Length is 8

the suffix of string A i.e "bc" and prefix of B i.e "bc" is the same
so the merged string will be "ababcabc" and length is 8.

Input :
A = "cdefg"
B = "abhgf"
Output :
Length is 8

the suffix of string A i.e "fg" and prefix of  reversed B i.e "fg" is the same
so the merged string will be "cdefghba" and length is 8

Input :
A = "wxyz"
B = "zyxw"
Output :
Length is 4

```

**下面是上述方法的 Python 代码实现。**

```py
# function to find the length of the
# merged string

def mergedstring(x, y) :

    k = len(y)
    for i in range(len(x)) :

        if x[i:] == y[:k] :
            break
        else:
            k = k-1

    # uncomment the below statement to
    # know what the merged string is
    # print(a + b[k:])
    return len(a + b[k:])

# function to find the minimum length
# among the  merged string
def merger(a, b):
    # reverse b 
    b1 = b[::-1] 

    # function call to find the length
    # of string without reversing string 'B'
    r1 = mergedstring(a, b)

    # function call to find the length
    # of the string by reversing string 'B'
    r2 = mergedstring(a, b1)

    # compare between lengths
    if r1 > r2 :
        print("Length is", r2)
    else :
        print("Length is", r1)

# driver code
a = "abcbc"
b = "bcabc"

merger(a, b)
```

**输出:**

```py
Length is 8

```