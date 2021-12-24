# 理解 Python 3 中的布尔逻辑

> 原文:[https://www . geesforgeks . org/understanding-boolean-logic-in-python-3/](https://www.geeksforgeeks.org/understanding-boolean-logic-in-python-3/)

布尔是简单易用的概念，存在于每种编程语言中。布尔表示“真”或“假”的概念。在编写算法或任何程序时，经常会出现我们希望在不同情况下执行不同代码的情况。Booleans 帮助我们的代码做到了简单有效。更常见的情况是，某种比较操作会返回一个布尔值。
有两个布尔关键字:真和假
[**运算符:**](https://www.geeksforgeeks.org/python-operators/) 运算符是 Python 中用于执行算术或逻辑计算的特殊符号。要对其进行运算的值称为操作数，而运算则由运算符(如++、-、/、*、%等)表示。)

## 比较运算符

比较运算符用于比较值。它在计算条件后返回真或假。

<figure class="table">

| 操作员 | 意义 | 例子 |
| --- | --- | --- |
| > | 大于–如果左操作数大于右操作数，则为真 | x > y |
| < | 小于–如果左操作数小于右操作数，则为真 | x < y |
| == | 等于–如果两个操作数相等，则为真 | x == y |
| ！= | 不等于–如果操作数不相等，则为真 | x！= y |
| >= | 大于或等于–如果左操作数大于或等于右操作数，则为真 | x >= y |
| <= | 小于或等于–如果左操作数小于或等于右操作数，则为真 | x <= y |

</figure>

## 逻辑运算符

有三个逻辑运算符:和，或，不是

<figure class="table">

| 操作员 | 意义 | 例子 |
| --- | --- | --- |
| 和 | 如果两个操作数都为真，则为真 | x 和 y |
| 或者 | 如果任一操作数为真，则为真 | x 或 y |
| 不 | 如果操作数为假，则为真。 | 不是 x |

</figure>

## 真值表

真值表是一个小表，允许我们给出逻辑运算符的结果。
**和表:**它需要两个操作数。

<figure class="table">

| a | b | a 和 b |
| --- | --- | --- |
| 错误的 | 错误的 | 错误的 |
| 错误的 | 真实的 | 错误的 |
| 真实的 | 错误的 | 错误的 |
| 真实的 | 真实的 | 真实的 |

</figure>

**或表:**它需要两个操作数。

<figure class="table">

| a | b | a 或 b |
| --- | --- | --- |
| 错误的 | 错误的 | 错误的 |
| 错误的 | 真实的 | 真实的 |
| 真实的 | 错误的 | 真实的 |
| 真实的 | 真实的 | 真实的 |

</figure>

**不是表:**它只取一个操作数。

<figure class="table">

| a | 一个也不 |
| --- | --- |
| 错误的 | 真实的 |
| 真实的 | 错误的 |

</figure>

**示例 1 :** 检查列表是否为空。我们将在 bool()函数中传递列表。当列表为空时，返回 False，如果列表不为空，则返回 True。

## 蟒蛇 3

```
def check_Empty(list_name):
    print(bool(list_name))

if __name__ == "__main__":
    # making an empty list
    my_list =[]

    # calling our function
    check_Empty(my_list)

    # making an non-empty list
    my_list1 =[1, 2, 3]

    # calling our function
    check_Empty(my_list1)
```

**输出:**

```
False
True
```

**示例 2 :** 使用 while 循环打印一个数字范围，while 循环将运行，直到条件为真。

## 蟒蛇 3

```
def print_range_numbers(n):
    i = 1

    # will execute until condition is True
    while  i <= n:
        print(i)
        i = i + 1

if __name__ == "__main__":
    n = 3

    # calling our function
    print_range_numbers(n)
```

**输出:**

```
1
2
3
```

**例 3 :** 借助布尔运算，我们可以绑定我们的程序。

## 蟒蛇 3

```
def myFunction() :
    return True

if __name__ == "__main__":
    if myFunction():
        # prints YES if myFunction() returns True
        print("YES !")

    else:
        # prints NO if myFunction() returns False
        print("NO !")
```

**输出:**

```
YES !
```

**例 4 :** 借助条件句检查两个数中较大的一个。借助布尔运算，我们可以比较结果并据此执行

## 蟒蛇 3

```
def check_greater(num_1, num_2):
    if num_2 > num_1:

        # after evaluating condition if it return True
        # then the following line of code get executed
        print("num_2 is greater than num_1")

    else:
        print("num_2 is not greater than num_1")

if __name__ == "__main__":
    num_1 = 3
    num_2 = 5

    # passing it to our function
    check_greater(num_1, num_2)
```

**输出:**

```
num_2 is greater than num_1
```