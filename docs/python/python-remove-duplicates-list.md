# Python 从列表中删除重复项

> 原文:[https://www . geesforgeks . org/python-remove-duplicates-list/](https://www.geeksforgeeks.org/python-remove-duplicates-list/)

工作很简单。我们需要获取一个列表，其中包含重复的元素，并生成另一个列表，该列表只包含元素，而不包含重复的元素。

**示例:**

```py
Input : [2, 4, 10, 20, 5, 2, 20, 4]
Output : [2, 4, 10, 20, 5]

Input : [28, 42, 28, 16, 90, 42, 42, 28]
Output : [28, 42, 16, 90]
```

我们可以使用不在列表中的[来找出重复的项目。我们创建一个结果列表，只插入那些不在列表中的结果。](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)

## 蟒蛇 3

```py
# Python code to remove duplicate elements
def Remove(duplicate):
    final_list = []
    for num in duplicate:
        if num not in final_list:
            final_list.append(num)
    return final_list

# Driver Code
duplicate = [2, 4, 10, 20, 5, 2, 20, 4]
print(Remove(duplicate))
```

**输出:**

```py
[2, 4, 10, 20, 5]
```

**轻松实现:**

使用 python 标准库中的 set 数据结构(下面给出了 Python 3.x 的实现)可以快速完成上述操作

## 蟒蛇 3

```py
duplicate = [2, 4, 10, 20, 5, 2, 20, 4]
print(list(set(duplicate)))
```

**输出:**

```py
[2, 4, 10, 20, 5] 
```