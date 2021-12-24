# Python 程序使用 lambda

按照列对列表进行排序

> 原文:[https://www . geesforgeks . org/python-program-to-sort-list-按列排序-using-lambda/](https://www.geeksforgeeks.org/python-program-to-sort-the-list-according-to-the-column-using-lambda/)

给定一个列表，任务是使用 lambda 方法根据列对列表进行排序。

**示例:**

> **输入:**
> 数组= [[1，3，3]，[2，1，2]，[3，2，1]]
> **输出:**
> 特定于列 0 的排序数组，[[1，3，3]，[2，1，2]，[3，2，1]]
> 特定于列 1 的排序数组，[[2，1，2]，[3，2，1]，[1，3，3]]【T8]特定于列 2 的排序数组，[[T7
> 
> **输入:**
> 数组= [['java '，1995]，['c++ '，1983]，['python '，1989]]
> T4】输出:
> 特定于列 0 的排序数组，['c++ '，1983]，['java '，1995]，['python '，1989]]
> 特定于列 1 的排序数组，['c++ '，1983]，['python '，1989

**进场:**

*   `sorted()`Python 中的内置函数从一个可迭代表中给出一个新的排序列表。
*   用于指定在进行比较之前对每个列表元素调用的函数的关键参数。
*   [lambda](https://www.geeksforgeeks.org/python-lambda/) 作为函数迭代每个元素。
*   `key = lambda x:x[i]`这里我是对整个列表进行排序的列。

下面是实现。

```
# Python code to sorting list 
# according to the column

# sortarray function is defined
def sortarray(array):

    for i in range(len(array[0])):

        # sorting array in ascending 
        # order specific to column i,
        # here i is the column index
        sortedcolumn = sorted(array, key = lambda x:x[i])

        # After sorting array Column 1
        print("Sorted array specific to column {}, \
        {}".format(i, sortedcolumn))

# Driver code 
if __name__ == '__main__': 

    # array of size 3 X 2 
    array = [['java', 1995], ['c++', 1983],
             ['python', 1989]]

    # passing array in sortarray function
    sortarray(array)
```

**Output:**

> 特定于列 0 的排序数组，[['c++ '，1983]，['java '，1995]，['python '，1989]]
> 特定于列 1 的排序数组，['c++ '，1983]，['python '，1989]，['java '，1995]]