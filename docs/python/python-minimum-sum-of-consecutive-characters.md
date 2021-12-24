# Python |连续字符的最小和

> 原文:[https://www . geesforgeks . org/python-最小连续字符总和/](https://www.geeksforgeeks.org/python-minimum-sum-of-consecutive-characters/)

有时，我们可能会遇到这样的问题，即我们需要从列表中获取 2 个数字的最小和，但有一个限制，即这些数字必须连续。这种类型的问题可能在竞争性编程时出现。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`min() + zip()` +列表理解**
这个问题可以通过以上三个函数的组合来解决，其中 min 函数可以用来得到最小值，zip 和列表理解完成将逻辑扩展到整个列表的任务。

```
# Python3 code to demonstrate
# Minimum Sum of Consecutive Characters
# using zip() + min() + list comprehension

# initializing string 
test_string = '6543452345456987653234'

# printing original string 
print("The original string : " + str(test_string))

# using zip() + min() + list comprehension
# Minimum Sum of Consecutive Characters
test_string = list(test_string)
res = min(int(a) + int(b) for a, b in zip(test_string, test_string[1:]))

# print result
print("The minimum consecutive sum is : " + str(res))
```

**Output :**

```
The original string : 6543452345456987653234
The minimum consecutive sum is : 5

```