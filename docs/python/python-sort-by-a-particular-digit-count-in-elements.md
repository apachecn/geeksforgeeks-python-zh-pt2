# Python–按元素中特定的位数排序

> 原文:[https://www . geesforgeks . org/python-按特定数字排序-元素计数/](https://www.geeksforgeeks.org/python-sort-by-a-particular-digit-count-in-elements/)

给定一个元素列表，在每个元素中按 K 位排序。

**示例:**

> **输入**:test _ list =【4322，2122，123，1344】，K = 2
> **输出**:【1344，123，4322，2122】
> **解释** : 0 < 1 < 2 < 3，按每个元素中 2 的计数排序。
> 
> **输入**:test _ list =【4322，2122，1344】，K = 2
> **输出**:【1344，4322，2122】
> **解释** : 0 < 2 < 3，按每个元素中 2 的计数排序。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**str()**](https://www.geeksforgeeks.org/python-str-function/)**+**[**计数()**](https://www.geeksforgeeks.org/python-string-count/)

在本文中，我们使用 sort()执行排序任务，使用 count()执行查找频率的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort by digit count in elements
# Using list comprehension + count() + str()

def count_dig(ele):

    # returning digit count
    return str(ele).count(str(K))

# initializing list
test_list = [4322, 2122, 123, 1344]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# calling external sort
test_list.sort(key = count_dig)

# printing result 
print("Sorted list : " + str(test_list))
```

**Output**

```
The original list is : [4322, 2122, 123, 1344]
Sorted list : [1344, 123, 4322, 2122]
```

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+str()+count()+**[**lambda**](https://www.geeksforgeeks.org/python-lambda/)

在本例中，我们使用 sorted()执行排序任务，并使用 lambda 函数而不是外部函数来获取排序逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort by digit count in elements
# Using sorted() + str() + count() + lambda

# initializing list
test_list = [4322, 2122, 123, 1344]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# sorting using sorted()
# not inplace sort.
res = sorted(test_list, key = lambda ele : str(ele).count(str(K)))

# printing result 
print("Sorted list : " + str(res))
```

**Output**

```
The original list is : [4322, 2122, 123, 1344]
Sorted list : [1344, 123, 4322, 2122]
```