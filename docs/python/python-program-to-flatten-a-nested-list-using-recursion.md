# 使用递归展平嵌套列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-扁平化-嵌套-列表-使用-递归/](https://www.geeksforgeeks.org/python-program-to-flatten-a-nested-list-using-recursion/)

给定一个嵌套列表，任务是编写一个 python 程序来使用递归展平嵌套列表。

**示例:**

> **输入:** [[8，9]，[10，11，'极客']，[13]]
> 
> **输出:**【8，9，10，11，‘极客’，13】
> 
> **输入:**[(A '，' B '，' C']，['D '，' E '，' F']]
> 
> **输出:** ['A '，' B '，' C '，' D '，' E '，' F '

**分步方法:**

*   首先，我们尝试将一个变量初始化为链表。
*   然后，我们的下一个任务是将我们的列表作为一个参数传递给一个递归函数来展平列表。
*   在那个递归函数中，如果我们发现列表是空的，那么我们就返回列表。
*   否则，我们以递归形式调用该函数及其子列表作为参数，直到列表变平。
*   最后，我们将打印扁平列表作为输出。

**下面是一些基于上述方法的 python 程序:**

**例 1:**

## 蟒蛇 3

```py
# Python program to flatten a nested list

# explicit function to flatten a
# nested list
def flattenList(nestedList):

    # check if list is empty
    if not(bool(nestedList)):
        return nestedList

     # to check instance of list is empty or not
    if isinstance(nestedList[0], list):

        # call function with sublist as argument
        return flattenList(*nestedList[:1]) + flattenList(nestedList[1:])

    # call function with sublist as argument
    return nestedList[:1] + flattenList(nestedList[1:])

# Driver Code
nestedList = [[8, 9], [10, 11, 'geeks'], [13]]
print('Nested List:\n', nestedList)

print("Flattened List:\n", flattenList(nestedList))
```

**输出:**

```py
Nested List:
 [[8, 9], [10, 11, 'geeks'], [13]]
Flattened List:
 [8, 9, 10, 11, 'geeks', 13]
```

**例 2:**

## 蟒蛇 3

```py
# Python program to flatten a nested list

# explicit function to flatten a
# nested list
def flattenList(nestedList):

    # check if list is empty
    if not(bool(nestedList)):
        return nestedList

     # to check instance of list is empty or not
    if isinstance(nestedList[0], list):

        # call function with sublist as argument
        return flattenList(*nestedList[:1]) + flattenList(nestedList[1:])

    # call function with sublist as argument
    return nestedList[:1] + flattenList(nestedList[1:])

# Driver Code
nestedList = [['A', 'B', 'C'], ['D', 'E', 'F']]
print('Nested List:\n', nestedList)

print("Flattened List:\n", flattenList(nestedList))
```

**输出:**

```py
Nested List:
 [['A', 'B', 'C'], ['D', 'E', 'F']]
Flattened List:
 ['A', 'B', 'C', 'D', 'E', 'F']
```

**例 3:**

## 蟒蛇 3

```py
# Python program to flatten a nested list

# explicit function to flatten a
# nested list
def flattenList(nestedList):

    # check if list is empty
    if not(bool(nestedList)):
        return nestedList

     # to check instance of list is empty or not
    if isinstance(nestedList[0], list):

        # call function with sublist as argument
        return flattenList(*nestedList[:1]) + flattenList(nestedList[1:])

    # call function with sublist as argument
    return nestedList[:1] + flattenList(nestedList[1:])

# Driver Code
nestedList = [[1], [2], [3], [4], [5]]
print('Nested List:\n', nestedList)

print("Flattened List:\n", flattenList(nestedList))
```

**输出:**

```py
Nested List:
 [[1], [2], [3], [4], [5]]
Flattened List:
 [1, 2, 3, 4, 5]
```