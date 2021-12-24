# Python–测试列表元素是否在其他列表的最小/最大范围内

> 原文:[https://www . geesforgeks . org/python-测试列表中的元素是否在其他列表的最小-最大范围内/](https://www.geeksforgeeks.org/python-test-if-elements-of-list-are-in-min-max-range-from-other-list/)

给定两个列表，任务是编写一个 Python 程序，如果第二个列表中的所有元素都在第一个列表的最小值和最大值范围内，则返回 true。

**示例:**

> **输入** : test_list = [5，6，3，7，8，10，9]，range_list = [4，7，9，6]
> **输出** : True
> **说明**:列表 1 中的 Min 和 max 为 3 和 10，其他列表中所有元素都在范围内。
> 
> **输入** : test_list = [5，6，3，7，8，10，9]，range_list = [4，7，9，16]
> **输出** : False
> **说明**:列表 1 中的 Min 和 max 为 3 和 10，其他列表中所有元素不在范围内。

**方法#1:使用循环+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，我们对第二个列表中的所有元素进行迭代，并对每个元素进行比较，如果任何元素小于最小值或大于最大值，结果将被标记为 off，并返回 false。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Min/Max range test from other list
# Using loop + min() + max()

# initializing list
test_list = [5, 6, 3, 7, 8, 10, 9]

# printing original lists
print("The original list is : " + str(test_list))

# initializing range_list
range_list = [4, 7, 9, 6]

res = True
for ele in range_list:

    # flag off list in case of any off range element
    if ele  max(test_list):
        res = False
        break

# printing result
print("Are all elements in min/max range? : " + str(res))
```

**Output**

```py
The original list is : [5, 6, 3, 7, 8, 10, 9]
Are all elements in min/max range? : True
```

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

在本例中，我们使用 all()检查所有元素是否在范围内，min()和 max()用于获取最大和最小元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Min/Max range test from other list
# Using all() + min() + max()

# initializing list
test_list = [5, 6, 3, 7, 8, 10, 9]

# printing original lists
print("The original list is : " + str(test_list))

# initializing range_list
range_list = [4, 7, 9, 6]

# checking for all values in range using all()
res = all(ele >= min(test_list) and ele <= max(test_list)
          for ele in range_list)

# printing result
print("Are all elements in min/max range? : " + str(res))
```

**Output**

```py
The original list is : [5, 6, 3, 7, 8, 10, 9]
Are all elements in min/max range? : True
```