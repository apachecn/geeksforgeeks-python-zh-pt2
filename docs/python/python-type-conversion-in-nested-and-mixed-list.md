# Python–嵌套和混合列表中的类型转换

> 原文:[https://www . geesforgeks . org/python-类型转换-嵌套和混合列表/](https://www.geeksforgeeks.org/python-type-conversion-in-nested-and-mixed-list/)

在使用 Python 列表时，由于其异构性，我们可能会遇到一个问题，即需要将列表中每个嵌套元素的数据类型转换为特定类型。在混合列表中，这变得复杂。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_list = [('7 '，['8 '，(' 5 '，)]]
> **输出** : [(7，[8，(5，])]
> 
> **输入** : test_list = ['6']
> **输出** : [6]

**方法:使用递归+ `isinstance()`**
以上函数的组合可以用来解决这个问题。在这种情况下，我们使用 isinstance()来获取列表元素的数据类型，如果是它的容器，则递归内部元素来执行转换。

```
# Python3 code to demonstrate working of 
# Type conversion in Nested and Mixed List
# Using recursion + isinstance()

# helper_fnc
def change_type(sub):
    if isinstance(sub, list):
        return [change_type(ele) for ele in sub]
    elif isinstance(sub, tuple):
        return tuple(change_type(ele) for ele in sub)
    else:
        return int(sub)

# initializing list
test_list = ['6', '89', ('7', ['8', '10']), ['11', '15']]

# printing original list
print("The original list is : " + str(test_list))

# Type conversion in Nested and Mixed List
# Using recursion + isinstance()
res = change_type(test_list)

# printing result 
print("Data after type conversion : " + str(res)) 
```

**Output :**

```
The original list is : ['6', '89', ('7', ['8', '10']), ['11', '15']]
Data after type conversion : [6, 89, (7, [8, 10]), [11, 15]]

```