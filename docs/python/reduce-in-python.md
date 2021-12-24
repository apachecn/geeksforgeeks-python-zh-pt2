# Python 中的 reduce()

> 原文:[https://www.geeksforgeeks.org/reduce-in-python/](https://www.geeksforgeeks.org/reduce-in-python/)

**reduce(fun，seq)** 函数用于**将参数中传递的特定函数应用于所传递序列中提到的所有列表元素**。该功能在**功能工具**模块中定义。

**工作:**

*   The first step is to select two elements of the sequence and get the result.
*   The next step is to apply the same function to the previously obtained result, and the number is just after the second element, and the result is stored again.
*   This process continues until there are no more elements in the container.
*   Return the final return result and print it on the console.

## 蟒 3

```
# python code to demonstrate working of reduce()

# importing functools for reduce()
import functools

# initializing list
lis = [1, 3, 5, 6, 2, ]

# using reduce to compute sum of list
print("The sum of the list elements is : ", end="")
print(functools.reduce(lambda a, b: a+b, lis))

# using reduce to compute maximum element from list
print("The maximum element of the list is : ", end="")
print(functools.reduce(lambda a, b: a if a > b else b, lis))
```

**输出**

```
The sum of the list elements is : 17
The maximum element of the list is : 6
```