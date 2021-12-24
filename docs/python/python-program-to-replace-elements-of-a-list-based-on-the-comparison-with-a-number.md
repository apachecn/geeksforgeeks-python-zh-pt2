# Python 程序根据与数字的比较来替换列表中的元素

> 原文:[https://www . geeksforgeeks . org/python-基于与数字比较的列表元素替换程序/](https://www.geeksforgeeks.org/python-program-to-replace-elements-of-a-list-based-on-the-comparison-with-a-number/)

给定一个列表，这里的任务是编写一个 Python 程序，在将元素与这里使用 k 描述的另一个数字进行比较后，替换元素。

对于本文中描述的示例，任何大于 K 的数字都将被替换为高值，任何小于或等于 K 的数字都将被替换为低值。

> **输入:** test_list = [7，4，3，2，6，8，9，1]，low = 2，high = 9，K = 5
> 
> **输出:**【9，2，2，2，9，9，9，2】
> 
> **说明:**K 以下的元素被 2 取代，其余的被 9 取代。
> 
> **输入:** test_list = [7，4，3，2，6，8，9，1]，low =2，high = 8，K = 5
> 
> **输出:**【8，2，2，2，8，8，8，2】
> 
> **说明:**K 以下的元素被 2 取代，其余的被 8 取代。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在本文中，我们使用条件语句执行替换，并使用循环执行迭代。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [7, 4, 3, 2, 6, 8, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# initializing low and high Replacement Replacement
low, high = 2, 9

res = []
for ele in test_list:

    # conditional tests
    if ele > K:
        res.append(high)
    else:
        res.append(low)

# printing result
print("List after replacement ? : " + str(res))
```

**输出:**

> 原来的名单是:[7，4，3，2，6，8，9，1]
> 
> 更换后列表？: [9, 2, 2, 2, 9, 9, 9, 2]

**方法二:** [*使用列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

与上面的方法类似，唯一的区别是这是一个单一的线性解决方案和一个紧凑的使用列表理解的替代方案。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [7, 4, 3, 2, 6, 8, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# initializing low and high Replacement Replacement
low, high = 2, 9

# list comprehension for shorthand solution
res = [high if ele > K else low for ele in test_list]

# printing result
print("List after replacement ? : " + str(res))
```

**输出:**

> 原来的名单是:[7，4，3，2，6，8，9，1]
> 
> 更换后列表？: [9, 2, 2, 2, 9, 9, 9, 2]