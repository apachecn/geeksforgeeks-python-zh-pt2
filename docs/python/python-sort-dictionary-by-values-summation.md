# Python–按值总和排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-values-summary/](https://www.geeksforgeeks.org/python-sort-dictionary-by-values-summation/)

给字典一个值列表，根据值列表中的值的总和对关键字进行排序。

> **输入** : test_dict = {'Gfg' : [6，7，4]，' best' : [7，6，5]}
> **输出** : {'Gfg': 17，' best': 18}
> **解释**:按和排序，替换。
> 
> **输入** : test_dict = {'Gfg' : [8]，' best' : [5]}
> **输出** : {'best': 5，' Gfg': 8}
> **解释**:按和排序，替换。

**方法一:使用排序()+词典理解+ sum()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们首先使用 sum()对所有列表元素求和，然后下一步是根据使用 sorted()提取的 sum 对所有键进行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionary by Values Summation
# Using dictionary comprehension + sum() + sorted()

# initializing dictionary
test_dict = {'Gfg' : [6, 7, 4], 'is' : [4, 3, 2], 'best' : [7, 6, 5]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# summing all the values using sum()
temp1 = {val: sum(int(idx) for idx in key) 
           for val, key in test_dict.items()}

# using sorted to perform sorting as required
temp2 = sorted(temp1.items(), key = lambda ele : temp1[ele[0]])

# rearrange into dictionary
res = {key: val for key, val in temp2}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [6, 7, 4], 'is': [4, 3, 2], 'best': [7, 6, 5]}
The sorted dictionary : {'is': 9, 'Gfg': 17, 'best': 18}

```

**方法二:使用 map() +词典理解+排序()+ sum()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行映射求和逻辑的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionary by Values Summation
# Using map() + dictionary comprehension + sorted() + sum()

# initializing dictionary
test_dict = {'Gfg' : [6, 7, 4], 'is' : [4, 3, 2], 'best' : [7, 6, 5]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# summing all the values using sum()
# map() is used to extend summation to sorted()
temp = {key: sum(map(lambda ele: ele, test_dict[key])) for key in test_dict}
res = {key: temp[key] for key in sorted(temp, key = temp.get)}        

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [6, 7, 4], 'is': [4, 3, 2], 'best': [7, 6, 5]}
The sorted dictionary : {'is': 9, 'Gfg': 17, 'best': 18}

```