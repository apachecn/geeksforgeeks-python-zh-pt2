# Python–用字典映射矩阵

> 原文:[https://www . geesforgeks . org/python-mapping-matrix-with-dictionary/](https://www.geeksforgeeks.org/python-mapping-matrix-with-dictionary/)

给定一个矩阵，将其值映射到字典值。

> **输入** : test_list = [[4，2，1]，[1，2，3]]，sub_dict = {1 : "gfg "，2: "best "，3 : "CS "，4 : "Geeks"}
> **输出** : [['Geeks '，' best '，' gfg']，['gfg '，' best '，' CS ']
> **解释**:使用字典替换矩阵元素。
> 
> **输入** : test_list = [[4，2，1]]，sub_dict = {1 : "gfg "，2: "best "，4 : "Geeks"}
> **输出** : [['Geeks '，' best '，' gfg ']
> **解释**:矩阵元素使用字典替换。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在本文中，我们从字典中迭代矩阵和映射的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Mapping Matrix with Dictionary
# Using loop

# initializing list
test_list = [[4, 2, 1], [1, 2, 3], [4, 3, 1]]

# printing original list
print("The original list : " + str(test_list))

# initializing dictionary
sub_dict = {1 : "gfg", 2: "best", 3 : "CS", 4 : "Geeks"}

# Using loop to perform required mapping
res = []
for sub in test_list:
    temp = []
    for ele in sub:

        # mapping values from dictionary
        temp.append(sub_dict[ele])
    res.append(temp)

# printing result 
print("Converted Mapped Matrix : " + str(res))
```

**Output**

```
The original list : [[4, 2, 1], [1, 2, 3], [4, 3, 1]]
Converted Mapped Matrix : [['Geeks', 'best', 'gfg'], ['gfg', 'best', 'CS'], ['Geeks', 'CS', 'gfg']]

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。这只是上述方法的简写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Mapping Matrix with Dictionary
# Using list comprehension

# initializing list
test_list = [[4, 2, 1], [1, 2, 3], [4, 3, 1]]

# printing original list
print("The original list : " + str(test_list))

# initializing dictionary
sub_dict = {1 : "gfg", 2: "best", 3 : "CS", 4 : "Geeks"}

# Using list comprehension to perform required mapping
# in one line 
res = [[sub_dict[val] for val in sub] for sub in test_list]

# printing result 
print("Converted Mapped Matrix : " + str(res))
```

**Output**

```
The original list : [[4, 2, 1], [1, 2, 3], [4, 3, 1]]
Converted Mapped Matrix : [['Geeks', 'best', 'gfg'], ['gfg', 'best', 'CS'], ['Geeks', 'CS', 'gfg']]

```