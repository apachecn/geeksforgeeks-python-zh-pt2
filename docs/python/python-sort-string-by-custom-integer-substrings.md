# Python–按自定义整数子字符串对字符串进行排序

> 原文:[https://www . geesforgeks . org/python-sort-string-by-custom-integer-substrings/](https://www.geeksforgeeks.org/python-sort-string-by-custom-integer-substrings/)

给定一个字符串列表，根据列表中出现的子字符串对字符串进行排序。

> **输入** : test_list =【“擅长 4”、“7 点醒来”、“工作到 6 点”、“11 点睡觉”】，subord _ list =【“11 点”、“7 点”、“4 点”、“6 点”】
> **输出**:【“11 点睡觉”、“7 点醒来”、“擅长 4 点”、“工作到 6 点”】
> **解释**:按子串有无排序的字符串。
> 
> **输入** : test_list =【“擅长 9”、“7 点醒来”、“工作到 6 点”、“11 点睡觉”】，subord _ list =【“11 点”、“7 点”、“9 点”、“6 点”】
> **输出**:【“11 点睡觉”、“7 点醒来”、“擅长 9 点”、“工作到 6 点”】
> **解释**:按子串有无排序的字符串。

**方法#1:使用 sorted()+zip()+lambda+regex()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用正则表达式()执行按子字符串排序的任务，并使用 sorted()，zip()产生最终结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort String by Custom Substrings
# Using sorted() + zip() + lambda + regex()
import re

# initializing list
test_list = ["Good at 4", "Wake at 7", "Work till 6", "Sleep at 11"]

# printing original list
print("The original list : " + str(test_list))

# initializing substring list
subord_list = ["6", "7", "4", "11"]

# creating inverse mapping with index
temp_dict = {val: key for key, val in enumerate(subord_list)}

# custom sorting
temp_list = sorted([[ele, temp_dict[re.search("(\d+){content}quot;, ele).group()]] \
                for ele in test_list], key = lambda x: x[1])
# compiling result
res = [ele for ele in list(zip(*temp_list))[0]]

# printing result
print("The sorted list : " + str(res))
```

**Output**

```py
The original list : ['Good at 4', 'Wake at 7', 'Work till 6', 'Sleep at 11']
The sorted list : ['Work till 6', 'Wake at 7', 'Good at 4', 'Sleep at 11']
```

**方法 2:使用 sorted()+zip()+comparator+regex()**

这是执行这项任务的另一种方式。在这种类似功能被用作上述方法的情况下，区别在于比较器函数被馈送给 sorted()而不是 lambda 来进行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort String by Custom Substrings
# Using sorted() + comparator + regex()
import re

# helper function to solve problem
def hlper_fnc(ele):
    temp = re.search("(\d+){content}quot;, ele).group()
    return temp_dict[temp] if temp in temp_dict else int(temp)

# initializing list
test_list = ["Good at 4", "Wake at 7", "Work till 6", "Sleep at 11"]

# printing original list
print("The original list : " + str(test_list))

# initializing substring list
subord_list = ["6", "7", "4", "11"]

# creating inverse mapping with index
temp_dict = {val: key for key, val in enumerate(test_list)}

# sorting using comparator
test_list.sort(key = lambda ele: hlper_fnc(ele))

# printing result
print("The sorted list : " + str(test_list))
```

**Output**

```py
The original list : ['Good at 4', 'Wake at 7', 'Work till 6', 'Sleep at 11']
The sorted list : ['Good at 4', 'Work till 6', 'Wake at 7', 'Sleep at 11']
```