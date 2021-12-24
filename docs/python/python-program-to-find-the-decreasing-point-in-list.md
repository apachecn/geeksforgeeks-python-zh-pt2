# Python 程序在列表中寻找递减点

> 原文:[https://www . geesforgeks . org/python-program-to-find-递减点列表/](https://www.geeksforgeeks.org/python-program-to-find-the-decreasing-point-in-list/)

给定一个列表，获取列表显示第一个负趋势的元素的索引，即下一个元素

> **输入** : test_list = [3，6，8，9，12，5，18，1]
> **输出** : 4
> **解释**:12->5，出现第一个递减点。
> 
> **输入** : test_list = [3，9，12，5，18，1]
> **输出** : 2
> **解释**:12->5 时，出现第一个递减点。

**方法#1:使用循环**

在这种情况下，我们检查下一个元素是否小于当前元素，在第一次发现它的地方，我们中断循环。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Decreasing point in List
# Using loop

# initializing list
test_list = [3, 6, 8, 9, 12, 5, 18, 1]

# printing original list
print("The original list is : " + str(test_list))

res = -1
for idx in range(0, len(test_list) - 1):

    # checking for 1st decreasing element
    if test_list[idx + 1] < test_list[idx]:
        res = idx
        break

# printing result 
print("Decreasing Point : " + str(res))
```

**输出:**

```py
The original list is : [3, 6, 8, 9, 12, 5, 18, 1]
Decreasing Point : 4
```

**方法 2:使用** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+循环**

在这种情况下，我们使用枚举同时检查索引和值，这是一种类似于上面的方法，不同之处在于单独的索引元素访问。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Decreasing point in List
# Using enumerate() + loop

# initializing list
test_list = [3, 6, 8, 9, 12, 5, 18, 1]

# printing original list
print("The original list is : " + str(test_list))

res = -1
for idx, ele in enumerate(test_list):

    # checking for 1st decreasing element
    if test_list[idx + 1] < ele:
        res = idx
        break

# printing result 
print("Decreasing Point : " + str(res))
```

**输出:**

```py
The original list is : [3, 6, 8, 9, 12, 5, 18, 1]
Decreasing Point : 4
```