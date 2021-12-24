# Python 程序用递归求一个数的阶乘

> 原文:[https://www . geesforgeks . org/python-program-to-find-factorial-of-number-in-use-recursion/](https://www.geeksforgeeks.org/python-program-to-find-the-factorial-of-a-number-using-recursion/)

阶乘是正整数 **n** ，用 **n 表示！**。然后所有小于或等于 ***n** 的正整数的乘积。*

![n! = n*(n-1)*(n-2)*(n-3)*....*1](img/f75383c0800f9e4b096761145eb6141a.png "Rendered by QuickLaTeX.com")

**例如:**

![5! = 5*4*3*2*1 = 120](img/ed46f4340be870b53a9518755929a8c2.png "Rendered by QuickLaTeX.com")

在本文中，我们将使用[递归](https://www.geeksforgeeks.org/recursion/)来计算一个数的阶乘。

**示例:**

```
Input: 5
Output: 120

Input: 6
Output: 720

```

**实施:**

如果叫事实(5)，就叫事实(4)、事实(3)、事实(2)、事实(1)。所以它的意思是 通过将值减少 1 直到它达到 1 来不断地呼唤自己。

## 蟒蛇 3

```
# Python 3 program to find  
# factorial of given number 
def factorial(n): 

    # Checking the number
    # is 1 or 0 then
    # return 1
    # other wise return
    # factorial
    if (n==1 or n==0):

        return 1

    else:

        return (n * factorial(n - 1)) 

# Driver Code 
num = 5; 
print("number : ",num)
print("Factorial : ",factorial(num))
```

**输出:**

```
Number :  5
Factorial :  120

```