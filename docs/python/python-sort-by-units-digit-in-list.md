# Python–按列表中的单位数字排序

> 原文:[https://www . geesforgeks . org/python-按单位排序-列表中的数字/](https://www.geeksforgeeks.org/python-sort-by-units-digit-in-list/)

给定整数列表，按单位数字排序。

> **输入**:test _ list =【76，434，23，22342】
> **输出**:【22342，23，434，76】
> **解释** : 2 < 3 < 4 < 6，按单位位数排序。
> 
> **输入**:test _ list =【76，4349，23，22342】
> **输出**:【22342，23，76，4349】
> **解释** : 2 < 3 < 6 < 9，按单位位数排序。

**方法#1:使用 sort() + str()**

在本例中，我们使用 *sort()* 执行排序，使用 *str()* 将整数转换为字符串，然后按最后一位数字排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Units Digit in List
# Using sort() + str()

# helpr_fnc to sort

def unit_sort(ele):

    # get last element
    return str(ele)[-1]

# initializing lists
test_list = [76, 434, 23, 22342]

# printing original lists
print("The original list is : " + str(test_list))

# inplace sort by unit digits
test_list.sort(key=unit_sort)

# printing result
print("The unit sorted list : " + str(test_list))
```

**输出:**

```
The original list is : [76, 434, 23, 22342]
The unit sorted list : [22342, 23, 434, 76]

```

**方法 2:使用排序的()+ lambda + str()**

在这种情况下，我们使用 *sorted()* 执行排序任务，使用 lambda 函数来避免外部函数调用。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Units Digit in List
# Using sorted() + lambda + str()

# initializing lists
test_list = [76, 434, 23, 22342]

# printing original lists
print("The original list is : " + str(test_list))

# inplace sort by unit digits
res = sorted(test_list, key=lambda sub: str(sub)[-1])

# printing result
print("The unit sorted list : " + str(res))
```

**输出:**

```
The original list is : [76, 434, 23, 22342]
The unit sorted list : [22342, 23, 434, 76] 

```