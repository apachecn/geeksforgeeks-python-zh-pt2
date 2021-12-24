# 通过第一列元素合并矩阵的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-按第一列元素合并矩阵/](https://www.geeksforgeeks.org/python-program-to-merge-a-matrix-by-the-elements-of-first-column/)

给定一个矩阵，基于第一列中的元素执行合并。

> **输入** : test_list = [[4，“极客”]，[3，“Gfg”]，[4，“cs”]，[4，“CS”]，[3，“best”]
> **输出** : [[4，‘极客’，‘CS’，‘CS’，[3，‘Gfg’，‘best’]
> **解释** : 4 与极客配对，CS 与 CS 遂合并为 1 行。
> 
> **输入** : test_list = [[4，“极客”]，[3，“Gfg”]，[4，“CS”]，[5，“CS”]，[3，“best”]
> **输出** : [[4，‘极客’，‘CS’，‘CS’，[3，‘Gfg’，‘best’，[5，‘CS’]
> **解释** : 4 与极客配对，CS 因此合并为 1 行。

**方法一:**使用[设置默认值()](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/)和[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，分组任务是使用 setdefault()完成的，它将 key 作为第一列元素，将其余元素作为列表的值。列表理解用于从构建的字典中获取所有值。

## 蟒蛇 3

```py
# initializing list
test_list = [[4, "geeks"], [3, "Gfg"], [4, "CS"], 
             [4, "cs"], [3, "best"]]

# printing original list
print("The original list is : " + str(test_list))

res = {}
for key, val in test_list:

    # setdefault used to merge similar values
    res.setdefault(key, []).append(val)

# getting all values
res = [[key] + val for key, val in res.items()]

# printing result
print("Merged Matrix : " + str(res))
```

**输出:**

> 原列表为:[[4，'极客']，[3，' Gfg']，[4，' CS']，[4，' cs']，[3，'最佳']]
> 合并矩阵:[[4，'极客'，' CS '，' cs']，[3，' Gfg '，'最佳']]

**方法 2 :** 使用[值()](https://www.geeksforgeeks.org/python-dictionary-values/)和[设置默认值()](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/)

这里，我们使用 values()提取值，剩下的所有操作都以类似于上面解释的方式执行。这个程序从列表中省略了第一个基于分组的列元素。

## 蟒蛇 3

```py
# initializing list
test_list = [[4, "geeks"], [3, "Gfg"], [4, "CS"],
             [4, "cs"], [3, "best"]]

# printing original list
print("The original list is : " + str(test_list))

res = {}
for key, val in test_list:

    # setdefault used to merge similar values
    res.setdefault(key, []).append(val)

# fetch values using value()
res = list(res.values())

# printing result
print("Merged Matrix : " + str(res))
```

**输出:**

> 原列表为:[[4，'极客']，[3，' Gfg']，[4，' CS']，[4，' cs']，[3，' best']]
> 合并矩阵:['极客'，' CS '，' cs']，['Gfg '，' best']]