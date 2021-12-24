# Python 程序检查数字是否是回文(单行)

> 原文:[https://www . geesforgeks . org/python-program-to-check-number-is-回文-one-liner/](https://www.geeksforgeeks.org/python-program-to-check-if-number-is-palindrome-one-liner/)

有时，我们有一个检查数字是否是回文的应用程序，这在日常编程或竞争性编程中很常见，很容易反转一个数字并检查它，但有时为了可读性和减少代码行，我们需要在单行逻辑中执行。让我们讨论一下实现这一点的某些方法。

> 输入:test_number = 12321
> 输出:真
> 
> 输入:test_number = 1234
> 输出:False

**方法#1:使用`math.log()` +递归+列表理解**
以上三个函数的组合可以很容易地执行这个特定的任务，log 函数提取数字的个数，以 10 为幂得到该迭代的个数进行比较。重复该过程以测试回文。

```
# Python3 code to demonstrate
# checking a number is palindrome
# using math.log() + recursion + list comprehension
import math

# the recursive function to reverse
def rev(num):
    return int(num != 0) and ((num % 10) * \
             (10**int(math.log(num, 10))) + \
                          rev(num // 10))

# initializing number 
test_number = 9669669

# printing the original number 
print ("The original number is : " + str(test_number))

# using math.log() + recursion + list comprehension
# for checking a number is palindrome
res = test_number == rev(test_number)

# printing result
print ("Is the number palindrome ? : " + str(res))
```

**Output:**

```
The original number is : 9669669
Is the number palindrome ? : True

```

**方法 2:使用`str()` +串切片**
这也可以通过将数字转换为串，然后使用串切片方法将其反转并进行比较来完成，其真相会返回给它答案。

```
# Python3 code to demonstrate
# checking a number is palindrome
# using str() + string slicing

# initializing number 
test_number = 9669669

# printing the original number 
print ("The original number is : " + str(test_number))

# using str() + string slicing
# for checking a number is palindrome
res = str(test_number) == str(test_number)[::-1]

# printing result
print ("Is the number palindrome ? : " + str(res))
```

**Output:**

```
The original number is : 9669669
Is the number palindrome ? : True

```

我们也可以把输入读成字符串，然后简单地检查回文。

```
num = input("Enter a number")
if num == num[::-1]:
    print("Yes its a palindrome")
else:
    print("No, its not a palindrome")
```