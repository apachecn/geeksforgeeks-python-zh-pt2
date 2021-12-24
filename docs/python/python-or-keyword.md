# Python 或关键字

> 原文:[https://www.geeksforgeeks.org/python-or-keyword/](https://www.geeksforgeeks.org/python-or-keyword/)

**Python OR** 是逻辑运算符关键字。如果至少一个操作数变为真，或运算符返回真**。**

**注:**

*   在 Python 中，or 运算符不返回真或假。
*   Python 中的 or 运算符返回第一个操作数(如果为真)，否则返回第二个操作数。

## Python 或关键字真值表

<figure class="table">

| **输入 1** | **输入 2** | **输出** |
| --- | --- | --- |
| 真实的 | 真实的 | 真实的 |
| 真实的 | 错误的 | 真实的 |
| 错误的 | 真实的 | 真实的 |
| 错误的 | 错误的 | 错误的 |

</figure>

在 python 中或关键字在布尔上下文的两种主要情况下起作用:

## **If 语句**

在 [if 语句](https://www.geeksforgeeks.org/python-if-else/)中，python 使用 or 运算符在一个表达式中连接条件。

**示例:**

## 蟒蛇 3

```py
# initializing variable
a = 55
b = 33

# defining the condition
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")
```

**输出:**

```py
a is greater than b
```

## **同时循环**

使用 python 或运算符的布尔上下文的另一种说法是 [while loop](https://www.geeksforgeeks.org/python-while-loop/) 。通过在循环的头中使用或，您可以测试几个条件并运行主体，直到所有条件都评估为 false。

**示例:**

## 蟒蛇 3

```py
# break the loop as soon it sees 'e'
# or 's'
i = 0
a = 'geeksforgeeks'

while i < len(a):
    if a[i] == 'e' or a[i] == 's':
        i += 1
        break

    print('Current Letter :', a[i])
    i += 1
```

**输出:**

```py
Current Letter : g
```

### **实际应用**

短路求值是编程中一些布尔运算符的语义，其中只有当第一个参数不足以确定输出时，才计算第二个参数。当第一个参数为真时，整体输出变为真。