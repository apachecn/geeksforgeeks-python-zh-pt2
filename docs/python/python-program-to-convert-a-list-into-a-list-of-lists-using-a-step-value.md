# 使用步长值将列表转换为列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-list-to-list-list-使用步长值/](https://www.geeksforgeeks.org/python-program-to-convert-a-list-into-a-list-of-lists-using-a-step-value/)

给定一个列表，这里的任务是编写一个 python 程序，该程序可以通过使用这里用 k 表示的步长值将列表拆分成列表列表

> **输入:** test_list = [5，6，3，2，7，1，9，10，8]，K = 3
> 
> **输出:** [[5，2，9]，[6，7，10]，[3，1，8]]
> 
> **说明:** 5、2、9 分别是第 0、3、6 元素，因此(区别 3)归在一起。
> 
> **输入:** test_list = [5，6，3，2，7，1]，K = 3
> 
> **输出:** [[5，2]，[6，7]，[3，1]]
> 
> **说明:** 5 和 2 分别是第 0 和第 3 个元素，因此(差异 3)组合在一起。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*切片*](https://www.geeksforgeeks.org/string-slicing-in-python/)

在这种情况下，循环用于根据需要跳过数字，并且使用切片提取每个后续跳过的切片列表，并将其附加到结果中。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [5, 6, 3, 2, 7, 1, 9, 10, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing skips
K = 3

res = []
for idx in range(0, K):

    # 3rd arg. of slicing skips by K
    res.append(test_list[idx::K])

# printing result
print("Stepped splitted List : " + str(res))
```

**输出:**

> 原来的名单是:[5，6，3，2，7，1，9，10，8]
> 
> 分步拆分列表:[[5，2，9]，[6，7，10]，[3，1，8]]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*切片*](https://www.geeksforgeeks.org/string-slicing-in-python/)

与上述方法类似，唯一的区别是使用列表理解来完成迭代任务，而不是使用循环来代替简写。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [5, 6, 3, 2, 7, 1, 9, 10, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing skips
K = 3

# list comprehension used as one liner
res = [test_list[idx::K] for idx in range(0, K)]

# printing result
print("Stepped splitted List : " + str(res))
```

**输出:**

> 原来的名单是:[5，6，3，2，7，1，9，10，8]
> 
> 分步拆分列表:[[5，2，9]，[6，7，10]，[3，1，8]]