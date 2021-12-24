# Python |移除嵌套列表中的所有重复和排列

> 原文:[https://www . geesforgeks . org/python-移除嵌套列表中的所有重复和排列/](https://www.geeksforgeeks.org/python-remove-all-duplicates-and-permutations-in-nested-list/)

给定嵌套列表，任务是移除该嵌套列表中的所有重复和置换。

```
Input:  [[-11, 0, 11], [-11, 11, 0], [-11, 0, 11], 
         [-11, 2, -11], [-11, 2, -11], [-11, -11, 2]]
Output:  {(-11, 0, 11), (-11, -11, 2)}

Input:  [[-1, 5, 3], [3, 5, 0], [-1, 5, 3], 
         [1, 3, 5], [-1, 3, 5], [5, -1, 3]]
Output:  {(1, 3, 5), (0, 3, 5), (-1, 3, 5)}
```

**代码#1 :** 使用地图

```
# Python code to remove all duplicates
# and permutations in nested list

#Initialisation
listOfPermut = [[-11, 0, 11], [-11, 11, 0], [-11, 0, 11], 
                [-11, 2, -11], [-11, -11, 2], [2, -11, -11]]

# Sorting tuple then removing
output = set(map(lambda x: tuple(sorted(x)),listOfPermut))

# printing output
print(output)
```

**Output:**

```
{(-11, 0, 11), (-11, -11, 2)}

```

**代码#2 :**

```
# Python code to remove all duplicates
# and permutations in nested list

#Initialisation
input = [[-11, 0, 11], [-11, 11, 0], [-11, 2, -11],
                      [-11, -11, 2], [2, -11, -11]]

# Sorting tuple then removing
output = set(tuple(sorted(x)) for x in input)

# printing output
print(output)
```

**Output:**

```
{(-11, 0, 11), (-11, -11, 2)}

```