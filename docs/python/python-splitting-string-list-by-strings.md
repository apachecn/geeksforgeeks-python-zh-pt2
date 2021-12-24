# Python |按字符串拆分字符串列表

> 原文:[https://www . geesforgeks . org/python-拆分-按字符串列出/](https://www.geeksforgeeks.org/python-splitting-string-list-by-strings/)

有时，在使用 Python 字符串时，我们可能会遇到需要对字符串执行拆分的问题。但是我们可能会有一个更复杂的问题，即前后弦，需要对它们进行拆分。这可以是多对进行拆分。让我们讨论一下解决这个特殊问题的方法。

**方法:使用循环+ `index()` +列表切片**
这个任务可以通过以上功能一起执行。在这种情况下，我们只是沿着线对循环，并使用`index()`获得所需的索引。然后，进行列表切片，以构建所需切片的新列表，并附加以形成新的结果列表。

```py
# Python3 code to demonstrate working of
# Splitting string list by strings
# using loop + index() + list slicing

# initialize list
test_list = ['gfg', 'is', 'best', "for", 'CS', 'and', 'Maths' ]

# initialize split list
split_list = [('gfg', 'best'), ('CS', 'Maths')]

# printing original list
print("The original list is : " + str(test_list))

# printing split list 
print("The split list is : " + str(split_list))

# Splitting string list by strings
# using loop + index() + list slicing
for start, end in split_list:
        temp1 = test_list.index(start)
        temp2 = test_list.index(end) + 1
        test_list[temp1 : temp2] = [test_list[temp1 : temp2]]

# printing result
print("The resultant split list is : " + str(test_list))
```

**Output :**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'CS', 'and', 'Maths']
The split list is : [('gfg', 'best'), ('CS', 'Maths')]
The resultant split list is : [['gfg', 'is', 'best'], 'for', ['CS', 'and', 'Maths']]

```