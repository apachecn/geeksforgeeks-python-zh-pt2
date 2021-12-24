# Python |去掉列表中的方括号

> 原文:[https://www . geesforgeks . org/python-从列表中删除方括号/](https://www.geeksforgeeks.org/python-remove-square-brackets-from-list/)

有时，在显示列表内容时，不希望出现方括号，无论是左方括号还是右方括号。为此，当我们需要打印整个列表而不访问循环的元素时，我们需要一个方法来执行。让我们讨论一下执行这项任务的速记方法。

**方法:使用`str()` +列表切片**
可以应用的速记，不需要访问列表的每个元素，就是将整个列表转换成字符串，然后使用列表切片剥离列表的首个和最后一个字符。如果列表包含字符串，这将不起作用。在这种情况下，可以使用`join()`连接每个元素，正如许多其他文章中所讨论的那样。

```
# Python3 code to demonstrate working of
# Remove square brackets from list
# using str() + list slicing

# initialize list
test_list = [5, 6, 8, 9, 10, 21]

# printing original list
print("The original list is : " + str(test_list))

# Remove square brackets from list
# using str() + list slicing
res = str(test_list)[1:-1]

# printing result
print("List after removing square brackets : " + res)
```

**Output :**

```
The original list is : [5, 6, 8, 9, 10, 21]
List after removing square brackets : 5, 6, 8, 9, 10, 21

```