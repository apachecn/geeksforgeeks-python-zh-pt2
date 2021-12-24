# Python–数值字符串中的最大对求和

> 原文:[https://www . geesforgeks . org/python-最大值对-数字字符串求和/](https://www.geeksforgeeks.org/python-maximum-pair-summation-in-numeric-string/)

有时，我们可能会遇到这样的问题，即我们需要从字符串中获取 2 个数字的最大和，但有一个限制，即这些数字必须连续。这种类型的问题可能在竞争性编程时出现。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`max() + zip()` +列表理解**
这个问题可以通过以上三个函数的组合来解决，其中 max 函数可以用来获取最大值，zip 和列表理解完成将逻辑扩展到整个列表的任务。

```
# Python3 code to demonstrate
# Maximum Pair Summation in String
# using zip() + max() + list comprehension

# initializing string 
test_string = '6543452345456987653234'

# printing original string 
print("The original string : " + str(test_string))

# using zip() + max() + list comprehension
# Maximum Pair Summation in String
test_string = list(test_string)
res = max(int(a) + int(b) for a, b in zip(test_string, test_string[1:]))

# print result
print("The maximum consecutive sum is : " + str(res))
```

**Output :**

```
The original string : 6543452345456987653234
The maximum consecutive sum is : 17

```