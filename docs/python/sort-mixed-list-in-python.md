# Python 中混合列表排序

> 原文:[https://www.geeksforgeeks.org/sort-mixed-list-in-python/](https://www.geeksforgeeks.org/sort-mixed-list-in-python/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要对混合数据类型的特定列表进行排序。它包含整数和字符串，我们需要对它们进行相应的排序。让我们讨论一下解决这个问题的某些方法。

**方法 1:使用`sort()` +比较器**

这个问题可以使用 Python 提供的排序功能来解决。我们可以构造自己的自定义比较器来完成混合排序的任务。

```
# Python3 code to demonstrate working of
# Sort Mixed List
# using sort() + comparator

# comparator function for sort
def mixs(num):
    try:
        ele = int(num)
        return (0, ele, '')
    except ValueError:
        return (1, num, '')

# initialize list 
test_list = [4, 'gfg', 2, 'best', 'is', 3]

# printing original list 
print("The original list : " + str(test_list))

# Sort Mixed List
# using sort() + comparator
test_list.sort(key = mixs)

# printing result
print("List after mixed sorting : " + str(test_list))
```

**Output :**

```
The original list : [4, 'gfg', 2, 'best', 'is', 3]
List after mixed sorting : [2, 3, 4, 'best', 'gfg', 'is']

```

**方法 2:使用`sorted() + key + lambda + isdigit()`**

上述功能的组合也可用于解决这个问题。在这种情况下，我们只是使用 sorted()对列表进行排序，使用 key 函数使用 lambda 函数使用 isdigit()对数字进行分隔。

```
# Python3 code to demonstrate working of
# Sort Mixed List
# using sorted() + key + lambda + isdigit()

# initialize list 
test_list = ['4', 'gfg', '2', 'best', 'is', '3']

# printing original list 
print("The original list : " + str(test_list))

# Sort Mixed List
# using sorted() + key + lambda + isdigit()
res = sorted(test_list, key = lambda ele: (0, int(ele))
                        if ele.isdigit() else (1, ele))

# printing result
print("List after mixed sorting : " + str(res))
```

**Output :**

```
The original list : ['4', 'gfg', '2', 'best', 'is', '3']
List after mixed sorting : ['2', '3', '4', 'best', 'gfg', 'is']

```