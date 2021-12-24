# Python 程序拆分字符串并转换成字典

> 原文:[https://www . geesforgeks . org/python-程序对字符串进行拆分并将其转换为字典/](https://www.geeksforgeeks.org/python-program-to-split-the-string-and-convert-it-to-dictionary/)

给定一个分隔符(在代码中表示为 **delim** )分隔的字符串，以字典的形式对拆分进行排序。

**示例:**

> **输入**:test _ str = ' gfg * is * best * for * geeks '，delim = " *
> **输出** : {0: 'gfg '，1: 'is '，2: 'best '，3: 'for '，4: 'geeks'}
> 
> **输入** : test_str = 'gfg*is*best '，delim =“*”
> T3】输出 : {0: 'gfg '，1: 'is '，2: 'best'}

**方法 1:使用 split() +循环**

这是执行这项任务的一种粗暴的方式。在这种情况下，使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 将分割的部分存储在临时列表中，然后根据临时列表创建新字典。

## 蟒蛇 3

```
# Using split() + loop

# initializing string
test_str = 'gfg_is_best_for_geeks'

# printing original string
print("The original string is : "
      + str(test_str))

# initializing delim
delim = "_"

# splitting using split()
temp = test_str.split(delim)

res = dict()

# using loop to reform dictionary with splits
for idx, ele in enumerate(temp):
    res[idx] = ele

# printing result
print("Dictionary after splits ordering : "
      + str(res))
```

**输出:**

> 原始字符串为:gfg_is_best_for_geeks
> 拆分排序后的字典:{ 0:“gfg”，1:“is”，2:“best”，3:“for”，4:“geeks”}

**方法二:使用词典理解+拆分()+枚举()**

这是一种速记方法，在它的帮助下可以完成这项任务。在这种情况下，我们使用单行词典([词典理解](https://www.geeksforgeeks.org/python-dictionary-comprehension/))和[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/)来帮助排序来执行词典重建任务。

## 蟒蛇 3

```
# Using dictionary comprehension + split() + enumerate()

# initializing string
test_str = 'gfg_is_best_for_geeks'

# printing original string
print("The original string is : "
      + str(test_str))

# initializing delim
delim = "_"

# using one liner to rearrange dictionary
res = {idx: ele for idx, ele in
       enumerate(test_str.split(delim))}

# printing result
print("Dictionary after splits ordering : "
      + str(res))
```

**输出:**

> 原始字符串为:gfg_is_best_for_geeks
> 拆分排序后的字典:{ 0:“gfg”，1:“is”，2:“best”，3:“for”，4:“geeks”}