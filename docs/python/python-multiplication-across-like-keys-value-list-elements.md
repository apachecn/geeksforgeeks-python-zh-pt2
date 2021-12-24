# Python–跨相似关键字值列表元素的乘法

> 原文:[https://www . geesforgeks . org/python-乘法-跨类-键-值-列表-元素/](https://www.geeksforgeeks.org/python-multiplication-across-like-keys-value-list-elements/)

给定两个带有值列表的字典，像键乘法一样按元素执行。

> **输入**:test _ dict 1 = {“Gfg”:[4，6]，“Best”:[8，6]，“is”:[9，3]}，
> test _ dict 2 = {“Gfg”:[8，4]，“Best”:[6，3]，“is”:[9，8]}
> **输出**:{‘Gfg’:[32，24]，‘Best’:[48，18]，‘is]:[81，24]
> 
> **输入**:test _ dict 1 = {“Gfg”:[4，6]，【Best】:[8，6]}，
> test _ dict 2 = {“Gfg”:[8，4]，【Best】:[6，3]}
> **输出**:{‘Gfg’:[32，24]，‘Best’:[48，18]}
> **解释** : 4 * 8 = 32，6 * 4 = 24 等等

**方法:使用词典理解+ zip()**

这是执行这项任务的方法之一。在本例中，我们使用 zip()执行组合键的任务，并再次使用 zip()组合相似的值。词典理解用于构建新的列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Multiplication across Like Keys Value list elements
# Using dictionary comprehension + zip()

# initializing dictionaries
test_dict1 = {"Gfg" : [4, 6, 7], "Best" : [8, 6, 4], "is" : [9, 3, 4]}
test_dict2 = {"Gfg": [8, 4, 3], "Best" : [6, 3, 1], "is" : [9, 8, 2]}

# printing original lists
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Using zip() to perform link keys and values 
res = {key: [ele1 * ele2 for (ele1, ele2) in zip(test_dict1[key], val2)] 
       for (key, val2) in zip(test_dict1.keys(), test_dict2.values())}

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary 1 is : {'Gfg': [4, 6, 7], 'Best': [8, 6, 4], 'is': [9, 3, 4]}
The original dictionary 2 is : {'Gfg': [8, 4, 3], 'Best': [6, 3, 1], 'is': [9, 8, 2]}
The constructed dictionary : {'Gfg': [32, 24, 21], 'Best': [48, 18, 4], 'is': [81, 24, 8]}

```