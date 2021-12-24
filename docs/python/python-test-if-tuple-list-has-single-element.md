# Python–测试元组列表是否有单个元素

> 原文:[https://www . geesforgeks . org/python-test-if-tuple-list-has-single-element/](https://www.geeksforgeeks.org/python-test-if-tuple-list-has-single-element/)

给定一个元组列表，检查它是否只由一个元素组成，使用了多次。

> **输入** : test_list = [(3，3，3)，(3，3)，(3，3，3)，(3，3)]
> **输出** : True
> **解释**:所有元素等于 3。
> 
> **输入** : test_list = [(3，3，3)，(3，3)，(3，4，3)，(3，3)]
> **输出** : False
> **解释**:所有元素不等于任何特定元素。

**方法#1:使用循环**

在这种情况下，我们检查所有元素，并将它们与元组列表中初始元组的初始元素进行比较，如果有任何元素不同，结果将被标记为关闭。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if tuple list has Single element
# Using loop 

# initializing list
test_list = [(3, 3, 3), (3, 3), (3, 3, 3), (3, 3)]

# printing original list
print("The original list is : " + str(test_list))

# checking for similar elements in list 
res = True 
for sub in test_list:
    flag = True 
    for ele in sub:

        # checking for element to be equal to initial element
        if ele != test_list[0][0]:
            flag = False 
            break 
    if not flag:
        res = False 
        break

# printing result 
print("Are all elements equal : " + str(res))
```

**输出:**

```
The original list is : [(3, 3, 3), (3, 3), (3, 3, 3), (3, 3)]
Are all elements equal : True
```

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用 all()执行检查所有元素是否相同的任务，列表理解用于执行遍历元组列表中所有元组的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if tuple list has Single element
# Using all() + list comprehension

# initializing list
test_list = [(3, 3, 3), (3, 3), (3, 3, 3), (3, 3)]

# printing original list
print("The original list is : " + str(test_list))

# checking for single element using list comprehension
res = all([all(ele == test_list[0][0] for ele in sub) for sub in test_list])

# printing result
print("Are all elements equal : " + str(res))
```

**输出:**

```
The original list is : [(3, 3, 3), (3, 3), (3, 3, 3), (3, 3)]
Are all elements equal : True
```