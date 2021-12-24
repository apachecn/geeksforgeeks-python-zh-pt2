# Python 程序查找给定列表中的所有强名称

> 原文:[https://www . geesforgeks . org/python-program-to-find-all-strong-numbers-in-给定列表/](https://www.geeksforgeeks.org/python-program-to-find-all-strong-numbers-in-given-list/)

给定一个列表，编写一个 Python 程序，在给定的数字列表中找到所有的[强数字](https://www.geeksforgeeks.org/program-to-check-strong-number/)。

一个**强数**是一个等于其位数阶乘之和的数。

**示例:**

```py
Input : [1, 2, 5, 145, 654, 34] 
Output : [1, 2, 145]

Input : [15, 58, 75, 675, 145, 2]
Output : [145, 2]

```

**说明:**

*   我们在这里定义了 2 个函数:第一个是`factorial()`，第二个是`strong_number()`。
*   一旦调用`strong_number()`，列表就被传递给函数并存储在形式参数列表中。
*   对于列表中每个元素的循环迭代，`temp` 是一个临时变量，对其进行计算，然后对剩余的 *temp mod 10* 调用`factorial()`函数，并将其传递给`factorial` 函数。
*   现在当`temp` 等于 0 时，退出 while 循环，检查 sum 是否等于 x。如果*为真*，则使用为列表预定义的`append()`功能将其添加到列表中，该功能用于在列表中添加元素，如果没有强数字，则返回空列表。

下面是 Python 实现:

```py
# Python program to find all 
# Strong Numbers in given list
def factorial(number):
    if(number == 0 or number == 1):
        fact = 1
    else:
        fact = number * factorial(number - 1)
    return fact

def strong_number(list):
    new_list =[]

    for x in list:
        temp = x
        sum = 0
        while(temp):
            rem = temp % 10
            sum += factorial(rem)
            temp = temp // 10
        if(sum == x):
            new_list.append(x)
        else:
            pass  

    return new_list

# Driver Code
val_list = [1, 2, 5, 145, 654, 34]
strong_num_list = strong_number(val_list)
print(strong_num_list)
```

**Output:**

```py
[1, 2, 145]

```