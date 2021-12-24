# Python–无频率排序矩阵

> 原文:[https://www . geesforgeks . org/python-sort-matrix-by-none-frequency/](https://www.geeksforgeeks.org/python-sort-matrix-by-none-frequency/)

给定一个矩阵，按照无元素频率排序。

> **输入**:test _ list =[[无，无，3，无]，[12，4，5]，[无，3，4]]
> **输出** : [[12，4，5]，[无，3，4]，[无，无，3，无]]
> **解释**:分别为 0，1，3 计数为无。
> 
> **输入**:test _ list =[[无，无，3，无]，[无，3，4]]
> **输出** : [[12，4，5]，[无，无，3，无]]
> **解释**:分别为 0，3 计无。

**方法#1:使用 sort()**

在本文中，我们使用 sort()执行排序，并在每行中使用外部函数提取无元素频率的任务。这将执行就地排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Matrix by None frequency
# Using sort()

# external sort function
def get_None_freq(row):

    # getting length of None characters
    return len([ele for ele in row if not ele])

# initializing list
test_list = [[None, None, 4], [None, None, 3, None],
             [12, 4, 5], [None, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# sorting using sort()
test_list.sort(key = get_None_freq)

# printing result 
print("List after sorting : " + str(test_list))
```

**输出:**

> 原列表为:[[无，无，4]，[无，无，3，无]，[12，4，5]，[无，3，4]]
> 排序后的列表:[[12，4，5]，[无，3，4]，[无，无，4]，[无，无，3，无]]

**方法 2:使用排序的()+λ**

在这种情况下，用 lambda 函数代替外部函数来解决这个问题。sorted()用于执行排序任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Matrix by None frequency
# Using sorted() + lambda

# initializing list
test_list = [[None, None, 4], [None, None, 3, None],
             [12, 4, 5], [None, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# sorting using sorted()
# lambda function for None frequency logic
res = sorted(test_list, key=lambda row: len([ele for ele in row if not ele]))

# printing result
print("List after sorting : " + str(res))
```

**输出:**

> 原列表为:[[无，无，4]，[无，无，3，无]，[12，4，5]，[无，3，4]]
> 排序后的列表:[[12，4，5]，[无，3，4]，[无，无，4]，[无，无，3，无]]