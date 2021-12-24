# 不使用递归展平列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-flat-a-list-无需使用递归/](https://www.geeksforgeeks.org/python-program-to-flatten-a-list-without-using-recursion/)

任务是将一个嵌套列表转换成 Python 中的单个列表，也就是说，无论 Python 列表中有多少个嵌套级别，都必须移除所有嵌套，以便将其转换成一个包含最外面括号内所有列表的所有值但内部没有任何括号的单个列表。换句话说，列表中的元素可以是数字或列表。它需要被转换成一个列表，列表中的每个元素只是一个数字。

**示例:**

> **输入:** [1，2，[3，4，[5，6]，7]，[[[8，9]，10]]，[11，[12，13]]
> **输出:** [1，2，3，4，5，6，7，8，9，11，12，13]
> 
> **输入:** [1，[2，3]]
> 
> **输出:**【1，2，3】

有两种方法可以在不递归的情况下做到这一点。

**方法 1:使用**T2 堆叠

**进场:**

*   初始化:在堆栈中推送主列表
*   制作一个空列表来存储最终结果(结果变量)
*   循环直到堆栈不为空
    1.  弹出堆栈中最后添加的元素并存储它(当前变量)
    2.  如果弹出的元素是列表，而不是将该列表的所有元素推入堆栈
    3.  如果弹出的元素不是列表，则在结果中追加该元素
*   反转结果列表，以原始列表的顺序获得最终输出

**下面是实现:**

## 蟒蛇 3

```
# Input list
l = [1, 2, [3, 4, [5, 6], 7],
     [[[8, 9], 10]],
     [11, [12, 13]]]

# Function to flatten the the list

def flatten(input_list):
    # Final list to be returned
    result = []

    # Creating stack and adding 
    # all elements into it
    stack = [input_list]

    # Iterate stack till it
    # does not get empty
    while stack:

        # Get the last element of the stack
        current = stack.pop(-1)

        # If the last element is a list,
        # add all the elements of that list in stack
        if isinstance(current, list):
            stack.extend(current)

        # Else add that element in the result
        else:
            result.append(current)

    # Reverse the result to get the
    # list in original order
    result.reverse()

    return result

# output list
ans = flatten(l)
print(ans)
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
```

**方法 2:使用库**

包迭代实用程序也可以用来展平列表。

## 蟒蛇 3

```
from iteration_utilities import deepflatten

l = [1, 2, [3, 4, [5, 6], 7], 
     [[[8, 9], 10]], [11, [12, 13]]]

ans = list(deepflatten(l))
print(ans)
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
```