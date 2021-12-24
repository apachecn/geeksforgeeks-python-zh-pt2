# Python |测试字符串是否单调

> 原文:[https://www . geesforgeks . org/python-test-if-string-单调/](https://www.geeksforgeeks.org/python-test-if-string-is-monotonous/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们有一个字符串，我们希望检查一个字符串是连续增加还是减少。这类问题在数据和日常编程中都有应用。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`map() + split()` +列表理解**
以上功能的组合可以用来执行此任务。在这种情况下，我们将字符串拆分为列表，用 delim 分隔，然后针对列表问题测试中的单调，我们使用列表理解。

```py
# Python3 code to demonstrate working of 
# Test if String is Monotonous
# Using list comprehension + map() + split()

# initializing string
test_str = "6, 5, 4, 3, 2, 1"

# printing original string
print("The original string is : " + test_str)

# initializing delim 
delim = ", "

# Test if String is Monotonous
# Using list comprehension + map() + split()
temp = list(map(int, test_str.split(delim)))
direc = temp[-1] > temp[0] or -1
res = temp == list(range(temp[0], temp[-1] + direc, direc))

# printing result 
print("Is string Monotonous ? : " + str(res)) 
```

**Output :**

```py
The original string is : 6, 5, 4, 3, 2, 1
Is string Monotonous ? : True

```