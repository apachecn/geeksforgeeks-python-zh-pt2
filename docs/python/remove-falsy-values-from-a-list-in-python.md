# 从 Python 中的列表中移除虚假值

> 原文:[https://www . geesforgeks . org/remove-falsy-values-from-in-list-python/](https://www.geeksforgeeks.org/remove-falsy-values-from-a-list-in-python/)

**先决条件:**[**Python 中的真值 vs 假值**](https://www.geeksforgeeks.org/truthy-vs-falsy-values-in-python/)

在 Python 中，计算结果为 False 的值被视为 Falsy 值。空列表、空字典、空元组、空集、空字符串、无、假、0 等值被视为 Falsy 值。所以我们的任务是从列表中删除所有的虚假值。

**示例:**

```py
Input:  [10,20,30,0,False,40,0]
Output:  [10,20,30,40]

Input: [False,None,1,2,3,"Geeks"]
Output: [1,2,3,"Geeks"]

Input: [[],(),"GeeksForGeeks",26,27]
Output: ["GeeksForGeeks",26,27]
```

**方法 1 :**

我们可以创建一个包含非 Falsy 值的新列表。我们将遍历列表，并检查给定值是 Truthy 还是 Falsy。如果是 Truthy，我们会将其添加到新列表中。现在要检查给定值是 Truthy 还是 Falsy，可以使用 [bool()](https://www.geeksforgeeks.org/bool-in-python/) 方法。如果该值为真，则该方法返回真，否则返回假。

## 蟒蛇 3

```py
# Python Program to remove falsy values
# from List

# Function returning the updated list 
def Remove_Falsy(List):
    List1 = []
    for i in List:
        if(bool(i)):
            List1.append(i)
    return List1;

# Original List
List1 = [10, 20, 30, 0, False, 40, 0]
List2 = [False, None, 1, 2, 3, "Geeks"]
List3 = [[], (), "GeeksForGeeks", 26, 27]

# printing the updated list after removing Falsy values
print("List1[] = ", Remove_Falsy(List1))
print("List2[] = ", Remove_Falsy(List2))
print("List3[] = ", Remove_Falsy(List3))
```

**输出:**

```py
List1[] =  [10, 20, 30, 40]
List2[] =  [1, 2, 3, 'Geeks']
List3[] =  ['GeeksForGeeks', 26, 27]
```

**方法二:**

我们可以使用[过滤器()](https://www.geeksforgeeks.org/filter-in-python/)方法过滤掉虚假值。在方法–**过滤器(函数，序列)**中，我们将使用 [bool()](https://www.geeksforgeeks.org/bool-in-python/) 方法作为过滤器方法中的参数。它会根据真实或虚假的价值回归真实或虚假。

## 蟒蛇 3

```py
# Python Program to remove falsy values
# from List

# Function returning the updated list 
def Remove_Falsy(List):
    return list(filter(bool,List))

# Original List
List1 = [ 10, 20, 30, 0, False, 40, 0]
List2 = [ False, None, 1, 2, 3, "Geeks"]
List3 = [ [], (), "GeeksForGeeks", 26, 27]

# printing the updated list after removing Falsy values
print("List1[] = ", Remove_Falsy(List1))
print("List2[] = ", Remove_Falsy(List2))
print("List3[] = ", Remove_Falsy(List3))
```

**输出:**

```py
List1[] =  [10, 20, 30, 40]
List2[] =  [1, 2, 3, 'Geeks']
List3[] =  ['GeeksForGeeks', 26, 27]
```