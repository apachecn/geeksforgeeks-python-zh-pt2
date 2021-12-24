# 反转矩阵中每第 k 行的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-reverse-ever-kth-row-in-a-matrix/](https://www.geeksforgeeks.org/python-program-to-reverse-every-kth-row-in-a-matrix/)

给定一个矩阵，任务是编写 python 程序来反转每一个 Kth 行。其中，K 是某个跨度值。

> **输入** : test_list = [[5，3，2]，[8，6，3]，[3，5，2]，[3，6]，[3，7，4]，[2，9]]，K = 4
> **输出** : [[5，3，2]，[8，6，3]，[3，5，2]，[6，3]，[3，7，4]，[2，9]]
> **解释**:每隔 4 秒
> 
> **输入** : test_list = [[5，3，2]，[8，6，3]，[3，5，2]，[3，6]，[3，7，4]，[2，9]]，K = 2
> **输出** : [[5，3，2]，[3，6，8]，[3，5，2]，[6，3]，[3，7，4]，[9，2]]
> **解释**:每 2 秒

**方法 1 :** *使用* [*反过来()*](https://www.geeksforgeeks.org/python-list-reverse/#:~:text=reverse()%20is%20an%20inbuilt,objects%20of%20list%20in%20place.&text=Returns%3A,given%20object%20from%20the%20list.) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们对每一行进行迭代，如果找到第 Kt 行，则使用 reverse()对其进行反转。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse Kth rows in Matrix
# Using reversed() + loop

# initializing list
test_list = [[5, 3, 2], [8, 6, 3], [3, 5, 2], 
             [3, 6], [3, 7, 4], [2, 9]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

res = []
for idx, ele in enumerate(test_list):

    # checking for K multiple
    if (idx + 1) % K == 0:

        # reversing using reversed
        res.append(list(reversed(ele)))
    else:
        res.append(ele)

# printing result
print("After reversing every Kth row: " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，2]，[8，6，3]，[3，5，2]，[3，6]，[3，7，4]，[2，9]]
> 
> 每反转第 Kt 行后:[[5，3，2]，[8，6，3]，[2，5，3]，[3，6]，[3，7，4]，[9，2]]

**方法二:** *使用* [*切片*](https://www.geeksforgeeks.org/string-slicing-in-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，使用字符串切片执行反转任务，使用列表理解作为执行迭代任务的简写。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse Kth rows in Matrix
# Using Slicing + list comprehension

# initializing list
test_list = [[5, 3, 2], [8, 6, 3], [3, 5, 2], 
             [3, 6], [3, 7, 4], [2, 9]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# using enumerate() to get index and elements.
# list comprehension to perform of iteration
res = [ele[::-1] if (idx + 1) % K == 0 else ele for idx,
       ele in enumerate(test_list)]

# printing result
print("After reversing every Kth row: " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，2]，[8，6，3]，[3，5，2]，[3，6]，[3，7，4]，[2，9]]
> 
> 每反转第 Kt 行后:[[5，3，2]，[8，6，3]，[2，5，3]，[3，6]，[3，7，4]，[9，2]]