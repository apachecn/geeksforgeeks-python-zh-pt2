# Python–根据值列表中的最大/最小元素对字典进行排序

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-max-min-in-element-in-value-list/](https://www.geeksforgeeks.org/python-sort-dictionary-by-max-min-element-in-value-list/)

给定字典，根据字典值列表中存在的最大或最小元素执行排序。

> **输入**:test _ dict = {“Gfg”:[6，4]，“best”:[8，4]，“for”:[7，13]，“geeks”:[15，5]}
> **输出**:{“geeks”:[15，5]，“for”:[7，13]，“best”:[8，4]，“Gfg”:[6，4]}
> **解释**:最大值为 15，出现在“中
> 
> **输入**:test _ dict = {“Gfg”:[6，4]，“最佳”:[8，4]}
> **输出** : {“最佳”:[8，4]，“Gfg”:[6，4]}
> **解释**:最大值为 8，出现在“最佳”键中，因此位于第 1 个位置，以此类推。

**方法一:使用排序()+ max() +词典理解+逆向+ lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 sorted()执行排序任务，使用 max()提取最大值，使用 reverse 获取最大值元素 1st，使用 lambda 函数将 max()逻辑扩展到 sorted 函数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort dictionary by max / min element in value list
# Using sorted() + max() + dictionary comprehension + reverse + lambda

# initializing dictionary
test_dict = {"Gfg" : [6, 4], "is" : [10, 3], "best" : [8, 4],
             "for" : [7, 13], "geeks" : [15, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# lambda function driving maximum operation on sorted()
# dictionary comprehension used to reconstruct dictionary
res = {key: test_dict[key] for key in sorted(test_dict, key = lambda ele: max(test_dict[ele]),
       reverse = True)}

# printing result 
print("Reverse Sorted dictionary on basis of max values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [6, 4], 'is': [10, 3], 'best': [8, 4], 'for': [7, 13], 'geeks': [15, 5]}
Reverse Sorted dictionary on basis of max values : {'geeks': [15, 5], 'for': [7, 13], 'is': [10, 3], 'best': [8, 4], 'Gfg': [6, 4]}

```

**方法二:使用排序()+ min() +词典理解+逆向+ lambda**

这与上述函数的方法类似，唯一的区别是我们根据字典值中的最高最小值进行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort dictionary by max / min element in value list
# Using sorted() + min() + dictionary comprehension + reverse + lambda

# initializing dictionary
test_dict = {"Gfg" : [6, 4], "is" : [10, 3], "best" : [8, 4],
             "for" : [7, 13], "geeks" : [15, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# lambda function driving minimum operation on sorted()
# dictionary comprehension used to reconstruct dictionary
res = {key: test_dict[key] for key in sorted(test_dict, key = lambda ele: min(test_dict[ele]),
       reverse = True)}

# printing result 
print("Reverse Sorted dictionary on basis of min values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [6, 4], 'is': [10, 3], 'best': [8, 4], 'for': [7, 13], 'geeks': [15, 5]}
Reverse Sorted dictionary on basis of min values : {'for': [7, 13], 'geeks': [15, 5], 'Gfg': [6, 4], 'best': [8, 4], 'is': [10, 3]}

```