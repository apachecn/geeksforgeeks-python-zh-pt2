# Python 程序使用递归求嵌套列表的总和

> 原文:[https://www . geesforgeks . org/python-program-to-find-total-sum-of-a-nested-list-use-recursion/](https://www.geeksforgeeks.org/python-program-to-find-the-total-sum-of-a-nested-list-using-recursion/)

给出了一个嵌套列表。任务是使用递归打印这个列表的总和。嵌套列表是其元素也可以是列表的列表。

**例:**

```py
Input: [1,2,[3]]
Output: 6

Input: [[4,5],[7,8,[20]],100]
Output: 144

Input: [[1,2,3],[4,[5,6]],7]
Output: 28
```

**递归:**在递归中，函数会反复调用自己。当一个问题可以分成相同形式的更小的子问题时，通常使用这种技术。

**实施:**

遍历列表，每当我们发现列表中的一个元素也是一个列表时，这意味着我们也必须用这个元素列表(可以嵌套)执行相同的求和任务。所以我们找到了一个子问题，我们可以调用同一个函数来执行这个任务，只需将参数更改为这个子列表。当元素不是列表时，只需将其值添加到全局总变量中。

T2T4

```py
# Python Program to find sum
# of nested list using Recursion

def sum_nestedlist( l ):

    # specify that global variable is
    # referred to here in this function
    total = 0

    for j in range(len(l)):

        if type(l[j]) == list :

            # call the same function if
            # the element is a list
            sum_nestedlist(l[j])
        else:

            # if it's a single element
            # and not a list, add it to total
            total += l[j]  

    return total

print(sum_nestedlist([[1,2,3],[4,[5,6]],7]))
```

T5

**输出:**

```py
144
```