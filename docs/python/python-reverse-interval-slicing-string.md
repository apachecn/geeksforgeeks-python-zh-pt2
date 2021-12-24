# Python |反向区间切片串

> 原文:[https://www . geesforgeks . org/python-反向-区间-切片-字符串/](https://www.geeksforgeeks.org/python-reverse-interval-slicing-string/)

有时，在处理字符串时，我们可能会遇到需要执行字符串切片的问题。在这种情况下，我们可以有一个变种，其中我们需要执行反向切片太间隔。这种应用程序可以在日常编程中使用。让我们讨论执行这项任务的某些方法。
**方法#1:使用字符串切片(1)**
这个任务可以使用字符串切片来执行，那太嵌套了一个。在这种情况下，第一个切片执行间隔，第二个切片执行反向。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse Interval Slicing String
# Using String Slicing 1

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing Interval
K = 2

# Reverse Interval Slicing String
# Using String Slicing 1
res = test_str[::K][::-1]

# printing result
print("The reverse Interval Slice : " + str(res))
```

**Output : **

```py
The original string is : geeksforgeeks
The reverse Interval Slice : segoseg
```

**方法 2:使用字符串切片(2)**
这是可以执行此任务的另一种方式。在这种情况下，我们采用与上面类似的方法，但是采用不同的切片方式。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reverse Interval Slicing String
# Using String Slicing 2

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing Interval
K = 2

# Reverse Interval Slicing String
# Using String Slicing 1
res = test_str[::-1][::K]

# printing result
print("The reverse Interval Slice : " + str(res))
```

**Output : **

```py
The original string is : geeksforgeeks
The reverse Interval Slice : segoseg
```