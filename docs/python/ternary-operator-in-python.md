# Python 中的三元运算符

> 原文:[https://www.geeksforgeeks.org/ternary-operator-in-python/](https://www.geeksforgeeks.org/ternary-operator-in-python/)

三元运算符也称为条件表达式，是基于条件为真或假来计算某个值的运算符。在 [2.5](https://mail.python.org/pipermail/python-dev/2005-September/056846.html) 版本中添加到 Python 中。
它只是允许在一个**单行**中测试一个条件，替换多行 if-else 使代码紧凑。

**语法:**

```
[on_true] if [expression] else [on_false] 
```

*   **使用三元运算符的简单方法:**

## 计算机编程语言

```
# Program to demonstrate conditional operator
a, b = 10, 20

# Copy value of a in min if a < b else copy b
min = a if a < b else b

print(min)
```

**输出:**

```
10
```

*   **使用元组、字典**、**和λ**的直接方法

## 计算机编程语言

```
# Python program to demonstrate ternary operator
a, b = 10, 20

# Use tuple for selecting an item
# (if_test_false,if_test_true)[test]
# if [a<b] is true it return 1, so element with 1 index will print
# else if [a<b] is false it return 0, so element with 0 index will print
print( (b, a) [a < b] )

# Use Dictionary for selecting an item
# if [a < b] is true then value of True key will print
# elif [a<b] is false then value of False key will print
print({True: a, False: b} [a < b])

# lamda is more efficient than above two methods
# because in lambda  we are assure that
# only one expression will be evaluated unlike in
# tuple and Dictionary
print((lambda: b, lambda: a)[a < b]())
```

**输出:**

```
10
10
10
```

*   **三元运算符可以写成嵌套 if-else:**

## 计算机编程语言

```
# Python program to demonstrate nested ternary operator
a, b = 10, 20

print ("Both a and b are equal" if a == b else "a is greater than b"
        if a > b else "b is greater than a")
```

上述方法可以写成:

## 计算机编程语言

```
# Python program to demonstrate nested ternary operator
a, b = 10, 20

if a != b:
    if a > b:
        print("a is greater than b")
    else:
        print("b is greater than a")
else:
    print("Both a and b are equal")
```

**输出:**

```
 b is greater than a
```

*   **在三进制运算符中使用打印功能如下:-**

示例:使用 python3 中的三进制运算符在 2 中查找较大的数字

## 蟒蛇 3

```
a=5
b=7

# [statement_on_True] if [condition] else [statement_on_false]

print(a,"is greater") if (a>b) else print(b,"is Greater")
```

**输出:**

```
7 is Greater
```

### **要点:**

*   首先计算给定的条件(a < b)，然后根据条件返回的布尔值返回 a 或 b
*   运算符中参数的顺序不同于其他语言，如 C/C++(参见 [C/C++三元运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/))。
*   在所有 Python 操作中，条件表达式的优先级最低。

**在 2.5 之前使用的方法，当****三元运算符不存在时**
在类似于下面给出的表达式中，解释器检查表达式是否为真，然后计算 on_true，否则计算 on_false。

**语法:**

```
'''When condition becomes true, expression [on_false]
   is not executed and value of "True and [on_true]"
   is returned.  Else value of "False or [on_false]"
   is returned.
   Note that "True and x" is equal to x. 
   And "False or x" is equal to x. '''
[expression] and [on_true] or [on_false] 
```

**示例:**

## 计算机编程语言

```
# Program to demonstrate conditional operator
a, b = 10, 20

# If a is less than b, then a is assigned
# else b is assigned (Note : it doesn't
# work if a is 0.
min = a < b and a or b

print(min)
```

**输出:**

```
10
```

**注意:**这个方法唯一的缺点就是 **on_true 不能为零或者 False** 。如果发生这种情况，将始终计算 on_false。原因是，如果表达式为真，解释器将检查 on_true，如果为 0 或 false，这将迫使解释器检查 on_false，以给出整个表达式的最终结果。

本文由 **Mayank Rawat** 供稿， [Shubham Bansal](https://www.facebook.com/banalshubham) 改进。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。