# 从列表中移除回文元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-remove-回文-elements-from-list/](https://www.geeksforgeeks.org/python-program-to-remove-palindromic-elements-from-a-list/)

给定一个列表，这里的任务是编写 Python 程序，可以删除列表中存在回文等价元素的所有元素。

**示例:**

> **输入** : test_list = [54，67，12，45，98，76，9]
> 
> **输出**:【12，98】
> 
> **说明:** 67 有 76 为回文元素，两者均省略。
> 
> **输入:** test_list = [54，67，12，45，98，76，9，89]
> 
> **输出:**【12】
> 
> **说明:** 98 有 89 作为回文元素，两者均省略。

**方法一:** *使用*[*str()*](https://www.geeksforgeeks.org/python-str-function/)*[*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*int()*](https://www.geeksforgeeks.org/python-int-function/)*

*在这种情况下，首先使用 str()将元素转换为字符串，使用 int()将元素反转并重新转换为整数，并检查回文的出现，如果存在，则从结果中省略元素及其回文。*

***示例:***

## *蟒蛇 3*

```
*# initializing list
test_list = [54, 67, 12, 45, 98, 76, 9]

# printing original list
print("The original list is : " + str(test_list))

# reversing and comparing for presence using in operator
res = [ele for ele in test_list if int(str(ele)[::-1]) not in test_list]

# printing result
print("List after palindromic removals ? : " + str(res))*
```

***输出:***

> *原来的名单是:[54，67，12，45，98，76，9]*
> 
> *回文删除后的列表？: [12, 98]*

***方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/) *、* [*str()*](https://www.geeksforgeeks.org/python-str-function/) 和 [*int()*](https://www.geeksforgeeks.org/python-int-function/)*

*在本文中，我们使用 filter()执行过滤每个元素的任务。str()和 int()用于与上述方法相同的函数。*

***示例:***

## *蟒蛇 3*

```
*# initializing list
test_list = [54, 67, 12, 45, 98, 76, 9]

# printing original list
print("The original list is : " + str(test_list))

# reversing and comparing for presence using in operator
res = list(filter(lambda ele: int(str(ele)[::-1]) not in test_list, test_list))

# printing result
print("List after palindromic removals ? : " + str(res))*
```

***输出:***

> *原来的名单是:[54，67，12，45，98，76，9]*
> 
> *回文删除后的列表？: [12, 98]*