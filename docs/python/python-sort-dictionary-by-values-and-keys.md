# Python–按值和键对字典进行排序

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-value-and-key/](https://www.geeksforgeeks.org/python-sort-dictionary-by-values-and-keys/)

给定一个字典，根据下降值排序，如果值相似，则按字典顺序按键排序。

> **输入**:test _ dict = {“gfg”:1、“is”:1、“best”:1、“for”:1、“极客”:1}
> **输出**:{“best”:1、“is”:1、“for”:1、“极客”:1、“gfg”:1 }
> **解释**:所有值相等，遂按字典顺序排序键。
> 
> **输入**:test _ dict = {“gfg”:5、“is”:4、“best”:3、“for”:2、“极客”:1}
> **输出**:{“gfg”:5、“is”:4、“best”:3、“for”:2、“极客”:1}
> **解释**:所有值都不一样，遂降序排序。

**方法:使用排序()+条目()+词典理解+ lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 sorted()执行排序任务，字典理解用于重新构建字典，items()用于提取要排序的项目。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Dictionary by Values and Keys
# Using sorted() + items() + dictionary comprehension + lambda

# initializing dictionary
test_dict = {"Gfg" : 1, "is" :  3, "Best" : 2, "for" : 3, "Geeks" : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# - sign for descended values, omit if low-high sorting required
res = {val[0] : val[1] for val in sorted(test_dict.items(), key = lambda x: (-x[1], x[0]))}

# printing result 
print("Sorted dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 1, 'is': 3, 'Best': 2, 'for': 3, 'Geeks': 2}
Sorted dictionary : {'for': 3, 'is': 3, 'Best': 2, 'Geeks': 2, 'Gfg': 1}

```