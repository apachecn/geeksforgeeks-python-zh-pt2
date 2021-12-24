# Python–字符串列表中范围最大的元素

> 原文:[https://www . geesforgeks . org/python-ranged-最大字符串元素列表/](https://www.geeksforgeeks.org/python-ranged-maximum-element-in-string-list/)

有时，在处理 Python 数据时，我们会遇到一个问题，即我们有字符串列表形式的数据，我们需要找到该数据中的最大元素，但也是在一定范围的索引中。这是一个非常特殊的问题，但可以应用于数据领域。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = ['34，78，98，23，12 '，' 76，65，54，43，21 ']
> I，j = 1，3
> T5】输出 : 76
> 
> **输入** :
> test_list = ['34，78，98，23，12 '，' 76，65，54，43，21 ']
> I，j = 3，5
> T5】输出 : 98

**方法一:使用`max() + split()` +列表理解**
以上功能的组合用于解决这个问题。在这种情况下，我们对列表中特定范围内的每个字符串元素执行拆分，然后使用 max()在每个列表中查找该范围内的最大元素。首先，在子列表中最大，然后在其他索引中最大。

```
# Python3 code to demonstrate working of 
# Ranged Maximum Element in String Matrix
# Using max() + split() + list comprehension

# initializing list
test_list = ['34, 78, 98, 23, 12',
             '76, 65, 54, 43, 21',
             '82, 45, 32, 45, 32',
             '78, 34, 12, 34, 10']

# printing original list
print("The original list is : " + str(test_list))

# initializing Range 
i, j = 2, 4

# Ranged Maximum Element in String Matrix
# Using max() + split() + list comprehension
res = max([max(idx.split(', ')[i - 1: j]) for idx in test_list])

# printing result 
print("The maximum ranged element : " + str(res)) 
```

**Output :**

> 原始列表为:['34，78，98，23，12 '，' 76，65，54，43，21 '，' 82，45，32，45，32 '，' 78，34，12，34，10 ']
> 最大范围元素:98

**方法 2:使用生成器表达式+ `max()`**
上述功能的组合可以用来解决这个问题。在本文中，我们使用 single max()函数最大限度地提取所有元素，并使用嵌套生成器表达式一次性提取字符串的所有元素。

```
# Python3 code to demonstrate working of 
# Ranged Maximum Element in String Matrix
# Using generator expression + max()

# initializing list
test_list = ['34, 78, 98, 23, 12',
             '76, 65, 54, 43, 21',
             '82, 45, 32, 45, 32',
             '78, 34, 12, 34, 10']

# printing original list
print("The original list is : " + str(test_list))

# initializing Range 
i, j = 2, 4

# Ranged Maximum Element in String Matrix
# Using generator expression + max()
res = max(ele for sub in test_list for ele in sub.split(', ')[i - 1: j])

# printing result 
print("The maximum ranged element : " + str(res)) 
```

**Output :**

> 原始列表为:['34，78，98，23，12 '，' 76，65，54，43，21 '，' 82，45，32，45，32 '，' 78，34，12，34，10 ']
> 最大范围元素:98