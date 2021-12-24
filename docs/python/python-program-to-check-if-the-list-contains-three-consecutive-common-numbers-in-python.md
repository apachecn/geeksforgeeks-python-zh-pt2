# Python 程序检查列表是否包含 Python 中连续的三个常用数字

> 原文:[https://www . geesforgeks . org/python-程序检查列表中是否包含三个连续的 python 通用数字/](https://www.geeksforgeeks.org/python-program-to-check-if-the-list-contains-three-consecutive-common-numbers-in-python/)

我们的任务是打印 Python 列表中连续出现 3 次的元素。

**示例:**

```
Input : [4, 5, 5, 5, 3, 8]

Output : 5

Input : [1, 1, 1, 64, 23, 64, 22, 22, 22]

Output : 1, 22

```

**进场:**

1.  创建列表。
2.  为范围大小–2 创建一个循环。
3.  检查该元素是否等于下一个元素。
4.  再次检查下一个元素是否等于下一个元素。
5.  如果两个条件都满足，则打印元素。

**例 1:**3 个连续出现的元素只出现一次。

```
# creating the array
arr = [4, 5, 5, 5, 3, 8]

# size of the list
size = len(arr)

# looping till length - 2
for i in range(size - 2):

    # checking the conditions
    if arr[i] == arr[i + 1] and arr[i + 1] == arr[i + 2]:

        # printing the element as the 
        # conditions are satisfied 
        print(arr[i])
```

**输出:**

```
5
```

**例 2:**3 个连续出现的元素多次出现。

```
# creating the array
arr = [1, 1, 1, 64, 23, 64, 22, 22, 22]

# size of the list
size = len(arr)

# looping till length - 2
for i in range(size - 2):

    # checking the conditions
    if arr[i] == arr[i + 1] and arr[i + 1] == arr[i + 2]:

        # printing the element as the 
        # conditions are satisfied 
        print(arr[i])
```

**输出:**

```
1
22

```