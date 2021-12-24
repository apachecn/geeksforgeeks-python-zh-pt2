# Python–测试列表是否为回文

> 原文:[https://www . geesforgeks . org/python-test-if-list-is-回文/](https://www.geeksforgeeks.org/python-test-if-list-is-palindrome/)

给定一个列表，检查它是否是回文。

> **输入**:test _ List =【4，5，4】
> **输出** : True
> **说明** : List 前后相同。
> 
> **输入**:test _ List =【4，5，5】
> **输出** : True
> **说明** : List 前后不一样。

**方法一:使用** [**列表切片**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们首先提取并反转列表的后半部分，然后比较是否相等，如果发现相等，则得出它的回文。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if list is Palindrome
# Using list slicing

# initializing list
test_list = [1, 4, 5, 4, 1]

# printing original list
print("The original list is : " + str(test_list))

# Reversing the list
reverse = test_list[::-1]

# checking if palindrome
res = test_list == reverse

# printing result 
print("Is list Palindrome : " + str(res))
```

**Output**

```
The original list is : [1, 4, 5, 4, 1]
Is list Palindrome : True

```

**方法 2:使用** [**反转()**](https://www.geeksforgeeks.org/python-reversed-function/)

在这种情况下，我们只需反转列表，并检查原始列表和反转列表是否相似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if list is Palindrome
# Using reversed()

# initializing list
test_list = [1, 4, 5, 4, 1]

# printing original list
print("The original list is : " + str(test_list))

# reversing list
rev_list = list(reversed(test_list))

# checking for Palindrome
res = rev_list == test_list

# printing result 
print("Is list Palindrome : " + str(res))
```

**Output**

```
The original list is : [1, 4, 5, 4, 1]
Is list Palindrome : True

```