# 从 Python 列表中删除元素的所有出现

> 原文:[https://www . geesforgeks . org/从 python 列表中删除所有出现的元素/](https://www.geeksforgeeks.org/remove-all-the-occurrences-of-an-element-from-a-list-in-python/)

任务是执行删除列表中给定项目/元素的所有出现的操作。

**示例:**

> **输入:**
> 1 1 2 3 4 5 1 2
> 1
> T5】输出:
> 2 3 4 5 2
> 
> **说明:**输入列表为[1，1，2，3，4，5，1，2]，需要移除的项目为 1。
> 删除项目后，输出列表为[2，3，4，5，2]
> 
> **输入:**
> 5 6 7 8 9 10
> 7
> T5】输出:
> 5 6 8 9 10

在本文中，我们将看到如何以 3 种方式执行这个任务:

1.  使用列表理解
2.  使用过滤器()和 __ne__
3.  使用移除()

**方法 1 :** 使用列表理解
列表理解可以用来执行这个任务，在这个任务中，我们只需要检查匹配并重建没有目标元素的列表。我们可以为列表中满足特定条件的元素创建一个子列表。

```py
# Python 3 code to demonstrate
# the removal of all occurrences of a 
# given item using list comprehension

def remove_items(test_list, item):

    # using list comprehension to perform the task
    res = [i for i in test_list if i != item]

    return res

# driver code
if __name__=="__main__":

    # initializing the list
    test_list = [1, 3, 4, 6, 5, 1]

    # the item which is to be removed
    item = 1

    # printing the original list
    print ("The original list is : " + str(test_list))

    # calling the function remove_items()
    res = remove_items(test_list, item)

    # printing result
    print ("The list after performing the remove operation is : " + str(res))
```

**输出**

```py
The original list is : [1, 3, 4, 6, 5, 1]
The list after performing the remove operation is : [3, 4, 6, 5]

```

**方法 2 :** 使用过滤器()和 __ne__
我们过滤列表中那些不等于 __ne__ 的项目。

```py
# Python 3 code to demonstrate
# the removal of all occurrences of
# a given item using filter() and __ne__

def remove_items(test_list, item):

    # using filter() + __ne__ to perform the task
    res = list(filter((item).__ne__, test_list))

    return res

# driver code
if __name__=="__main__":

    # initializing the list
    test_list = [1, 3, 4, 6, 5, 1]

    # the item which is to be removed
    item = 1

    # printing the original list
    print ("The original list is : " + str(test_list))

    # calling the function remove_items()
    res = remove_items(test_list, item)

    # printing result
    print ("The list after performing the remove operation is : " + str(res))
```

**输出**

```py
The original list is : [1, 3, 4, 6, 5, 1]
The list after performing the remove operation is : [3, 4, 6, 5]

```

**方法 3 :** 使用 remove()
在这个方法中，我们遍历列表中的每个项目，当我们找到要移除的项目的匹配项时，我们将在列表中调用 remove()函数。

```py
# Python 3 code to demonstrate
# the removal of all occurrences of
# a given item using remove()

def remove_items(test_list, item):

    # remove the item for all its occurrences
    for i in test_list:
        if(i == item):
            test_list.remove(i)

    return test_list

# driver code
if __name__=="__main__":

    # initializing the list
    test_list = [1, 3, 4, 6, 5, 1]

    # the item which is to be removed
    item = 1

    # printing the original list
    print ("The original list is : " + str(test_list))

    # calling the function remove_items()
    res = remove_items(test_list, item)

    # printing result
    print ("The list after performing the remove operation is : " + str(res))
```

**输出**

```py
The original list is : [1, 3, 4, 6, 5, 1]
The list after performing the remove operation is : [3, 4, 6, 5]

```