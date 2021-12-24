# 在 Python 中从列表中移除多个元素

> 原文:[https://www . geesforgeks . org/remove-从 python 列表中删除多个元素/](https://www.geeksforgeeks.org/remove-multiple-elements-from-a-list-in-python/)

给定一个数字列表，编写一个 Python 程序，根据给定的条件从列表中移除多个元素。

**示例:**

```
Input: [12, 15, 3, 10]
Output: Remove = [12, 3], New_List = [15, 10]

Input: [11, 5, 17, 18, 23, 50]
Output: Remove = [1:5], New_list = [11, 50]
```

基于我们对数据的了解，在 Python 中可以从列表中删除多个元素。比如，我们只知道要删除的值，或者也知道这些值的索引。让我们看看基于不同场景的不同示例。

**示例#1:** 假设我们要删除列表中可被 2 整除或所有偶数整除的每个元素。

## 蟒蛇 3

```
# Python program to remove multiple
# elements from a list

# creating a list
list1 = [11, 5, 17, 18, 23, 50]

# Iterate each element in list
# and add them in variable total
for ele in list1:
    if ele % 2 == 0:
        list1.remove(ele)

# printing modified list
print("New list after removing all even numbers: ", list1)
```

**输出:**

```
New list after removing all even numbers:  [11, 5, 17, 23]
```

**示例#2:** 使用列表理解
移除列表中的所有偶数元素等于仅包括所有非偶数元素(即奇数元素)。

## 蟒蛇 3

```
# Python program to remove multiple
# elements from a list

# creating a list
list1 = [11, 5, 17, 18, 23, 50]

# will create a new list,
# excluding all even numbers
list1 = [ elem for elem in list1 if elem % 2 != 0]

print(*list1)
```

**输出:**

```
11 5 17 23
```

**示例#3:** 使用列表切片移除相邻元素
在 Python 代码下面，从索引 1 到 4 移除值。

## 蟒蛇 3

```
# Python program to remove multiple
# elements from a list

# creating a list
list1 = [11, 5, 17, 18, 23, 50]

# removes elements from index 1 to 4
# i.e. 5, 17, 18, 23 will be deleted
del list1[1:5]

print(*list1)
```

**输出:**

```
11 50
```

**示例#4:** 使用列表理解
假设要删除的元素是已知的，而不是那些元素的索引。在这种情况下，我们可以直接消除这些元素，而不用考虑索引，我们将在下一个示例中看到索引。

## 蟒蛇 3

```
# Python program to remove multiple
# elements from a list

# creating a list
list1 = [11, 5, 17, 18, 23, 50]

# items to be removed
unwanted_num = {11, 5}

list1 = [ele for ele in list1 if ele not in unwanted_num]

# printing modified list
print("New list after removing unwanted numbers: ", list1)
```

**输出:**

```
New list after removing unwanted numbers:  [17, 18, 23, 50]
```

**示例#5:** 当元素的索引已知时。
虽然元素的索引是已知的，但是随机删除元素会改变索引的值。因此，总是建议首先删除最大的索引。使用这种策略，较小值的索引不会改变。我们可以对列表进行逆序排序，并按降序删除列表中的元素。

## 蟒蛇 3

```
# Python program to remove multiple
# elements from a list

# creating a list
list1 = [11, 5, 17, 18, 23, 50]

# given index of elements
# removes 11, 18, 23
unwanted = [0, 3, 4]

for ele in sorted(unwanted, reverse = True):
    del list1[ele]

# printing modified list
print (*list1)
```

**输出:**

```
5 17 50
```