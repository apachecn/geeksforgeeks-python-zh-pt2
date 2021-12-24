# Python–按元素中的最大数字排序

> 原文:[https://www . geesforgeks . org/python-按元素中最大位数排序/](https://www.geeksforgeeks.org/python-sort-by-maximum-digit-in-element/)

给定一个元素列表，按列表中元素的最大位数排序。

> **输入**:test _ list =【234，92，8，721】
> **输出**:【234，721，8，92】
> **解释** : 4 < 7 < 8 < 9，按最大位数排序。
> 
> **输入**:test _ list =【92，8，721】
> **输出**:【721，8，92】
> **解释** : 7 < 8 < 9，按最大位数排序。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+sort()**

在本例中，我们使用 sort()执行就地排序任务，并使用 max()提取最大元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort by Maximum digit in Element
# Using max() + sort()

def max_dig(ele):

    # getting maximum digit by magnitude
    return max(str(ele))

# initializing list
test_list = [234, 92, 15, 8, 721]

# printing original list
print("The original list is : " + str(test_list))

# calling sort fnc. to sort with key
test_list.sort(key = max_dig)

# printing result 
print("Sorted List : " + str(test_list))
```

**Output**

```py
The original list is : [234, 92, 15, 8, 721]
Sorted List : [234, 15, 721, 8, 92]

```

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+max()**

在这种情况下，我们使用 sorted()执行非就地排序，并避免使用外部函数使用 lambda 函数来获取最大位数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort by Maximum digit in Element
# Using sorted() + lambda + max()

# initializing list
test_list = [234, 92, 15, 8, 721]

# printing original list
print("The original list is : " + str(test_list))

# lambda fnc. used to get maximum Element logic
res = sorted(test_list, key = lambda ele : max(str(ele)))

# printing result 
print("Sorted List " + str(res))
```

**Output**

```py
The original list is : [234, 92, 15, 8, 721]
Sorted List [234, 15, 721, 8, 92]

```