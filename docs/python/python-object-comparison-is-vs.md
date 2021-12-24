# Python 对象比较:“是”vs“= =”

> 原文:[https://www . geesforgeks . org/python-object-comparison-is-vs/](https://www.geeksforgeeks.org/python-object-comparison-is-vs/)

在 Python 中，“is”和“==”都用于对象比较。运算符“==”比较两个对象的值，而“is”检查两个对象是否相同(换句话说，对同一对象的两个引用)。

```
# Python program to demonstrate working of 
# "=="

# Two different objects having same values
x1 = [10, 20, 30]
x2 = [10, 20, 30]

# Comparison using "==" operator
if  x1 == x2:
    print("Yes")
else:
    print("No")
```

**Output:**

```
Yes

```

“==”运算符不会告诉我们 x1 和 x2 实际上是否指的是同一个对象。我们用“是”来表示这个目的。

```
# Python program to demonstrate working of 
# "is"

# Two different objects having same values
x1 = [10, 20, 30]
x2 = [10, 20, 30]

# We get "No" here
if  x1 is x2:
    print("Yes")
else:
    print("No")

# It creates another reference x3 to same list.
x3 = x1

# So we get "Yes" here
if  x1 is x3:
    print("Yes")
else:
    print("No")

# "==" would also produce yes anyway
if  x1 == x3:
    print("Yes")
else:
    print("No")
```

**Output:**

```
No
Yes
Yes

```

```
x1 = [10, 20, 30]

# Here a new list x2 is created using x1
x2 = list(x1)

# The "==" operator would produce "Yes"
if  x1 == x2:
    print("Yes")
else:
    print("No")

# But "is" operator would produce "No"
if  x1 is x2:
    print("Yes")
else:
    print("No")
```

**Output:**

```
Yes
No

```

 **结论:**

*   如果两个变量指向同一个对象，则“is”返回 True。
*   " == "如果两个变量具有相同的值(或内容)，则返回 True。

* * *