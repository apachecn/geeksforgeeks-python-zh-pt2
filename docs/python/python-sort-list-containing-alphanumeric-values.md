# Python |包含字母数字值的排序列表

> 原文:[https://www . geesforgeks . org/python-sort-list-包含-字母数字-值/](https://www.geeksforgeeks.org/python-sort-list-containing-alphanumeric-values/)

给定一个包含两个字母数字值的列表，编写一个 Python 程序对给定的列表进行排序，使字母值总是排在数字值之后。

**示例:**

```
Input : ['k', 5, 'e', 3, 'g', 7, 0, 't']
Output : [0, 3, 5, 7, 'e', 'g', 'k', 't']

Input : [1, 'c', 3, 2, 'a', 'b']
Output : [1, 2, 3, 'a', 'b', 'c']

```

**方法 1 :** 使用*排序()*方法

要使用 Python `sort()`方法，我们需要首先将所有列表值转换为*字符串*类型。现在有两种方法可以将值转换为字符串。

*   **方法一:**列表理解
    Python 列表理解可以简单的将列表的每个元素转换成字符串类型。我们对它进行排序，因为现在所有的值都是 str 类型，所以我们将最终的列表更改回它的原始形式。

    ```
    # Python3 program to Sort list 
    # containing alpha and numeric values

    def sort(lst):
        lst = [str(i) for i in lst]
        lst.sort()
        lst = [int(i) if i.isdigit() else i for i in lst ]
        return lst

    # Driver code
    lst = ['k', 5, 'e', 3, 'g', 7, 0, 't']
    print(sort(lst))
    ```

    **输出:**

    ```
    [0, 3, 5, 7, 'e', 'g', 'k', 't']

    ```

*   **Method #2 :** Using key function

    Key 函数用作排序比较的键，在我们的例子中等于 *str* 。

    ```
    # Python3 program to Sort list 
    # containing alpha and numeric values
    def sort(lst):

        lst.sort(key = str)
        return lst

    # Driver code
    lst = ['k', 5, 'e', 3, 'g', 7, 0, 't']
    print(sort(lst))
    ```

    **Output:**

    ```
    [0, 3, 5, 7, 'e', 'g', 'k', 't']

    ```

**进场 2 :** *整理()*

或者，您也可以出于同样的目的使用 Python 的内置函数 *sorted()* 。 *sort()* 和 *sorted()* 最简单的区别是: *sort()* 不返回值，而 *sorted()* 返回可迭代列表。现在又有两种使用 *sorted()* 的方式。

*   **方法#1 :** 使用按键功能

    ```
    # Python3 program to Sort list 
    # containing alpha and numeric values

    def sort(lst):

        return sorted(lst, key = str)

    # Driver code
    lst = ['k', 5, 'e', 3, 'g', 7, 0, 't']
    print(sort(lst))
    ```

    **输出:**

    ```
    [0, 3, 5, 7, 'e', 'g', 'k', 't']

    ```

*   **方法# 2:***λ*

    ```
    # Python3 program to Sort list 
    # containing alpha and numeric values

    def sort(lst):

        return sorted(lst, key = lambda x: (isinstance(x, str), x))

    # Driver code
    lst = ['k', 5, 'e', 3, 'g', 7, 0, 't']
    print(sort(lst))
    ```

    **输出:**

    ```
    [0, 3, 5, 7, 'e', 'g', 'k', 't']

    ```