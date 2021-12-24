# Python 程序获取列表中符号变化的索引

> 原文:[https://www . geesforgeks . org/python-program-to-get-indexs-of-sign-change-in-a-list/](https://www.geeksforgeeks.org/python-program-to-get-indices-of-sign-change-in-a-list/)

给定 List，任务是编写一个 python 程序，从中提取发生符号移位的所有索引。

> **输入:** test_list = [7，6，-3，-4，-7，8，3，-6，7，8]
> 
> **输出**:【1，4，6，7】
> 
> **说明:** 6 - > -3，在第一指数，-7 - > 8 在第四指数等等都是班次。
> 
> **输入:** test_list = [7，6，-3，-4，-7，8，3，6，7，8]
> 
> **输出:**【1，4】
> 
> **说明:** 6 - > -3，在第一指数，-7 - > 8 在第四指数是班次。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*条件语句*](https://www.geeksforgeeks.org/python-if-else/)

在本文中，我们使用条件语句检查当前元素和下一个元素的符号是否相反。循环用于遍历所有元素。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [7, 6, -3, -4, -7, 8, 3, -6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

res = []
for idx in range(0, len(test_list) - 1):

    # checking for successive opposite index
    if test_list[idx] > 0 and test_list[idx + 1] < 0 or test_list[idx] < 0 and test_list[idx + 1] > 0:
        res.append(idx)

# printing result
print("Sign shift indices : " + str(res))
```

**输出:**

> 原始列表是:[7，6，-3，-4，-7，8，3，-6，7，8]
> 
> 符号移位索引:[1，4，6，7]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

类似于上述方法，但这提供了一个使用列表理解的线性选择。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [7, 6, -3, -4, -7, 8, 3, -6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension to provide one liner alternative
res = [idx for idx in range(0, len(test_list) - 1) if test_list[idx] >
       0 and test_list[idx + 1] < 0 or test_list[idx] < 0 and test_list[idx + 1] > 0]

# printing result
print("Sign shift indices : " + str(res))
```

**输出:**

> 原始列表是:[7，6，-3，-4，-7，8，3，-6，7，8]
> 
> 符号移位索引:[1，4，6，7]