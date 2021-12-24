# Python |测试字符串是否是另一个

的子集

> 原文:[https://www . geesforgeks . org/python-test-if-string-is-subset-other/](https://www.geeksforgeeks.org/python-test-if-string-is-subset-of-another/)

有时，在处理字符串时，我们会遇到一个问题，即我们需要测试一个字符串是否是另一个字符串的子序列。这在许多领域都可能有应用，包括数据科学和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用 all()**
这是我们解决这个问题的方法之一。在本例中，我们使用 all()来检查一个字符串的所有字符是否都存在于另一个字符串中。

```
# Python3 code to demonstrate working of 
# Test if string is subset of another
# Using all()

# initializing strings
test_str1 = "geeksforgeeks"
test_str2 = "gfks"

# printing original string
print("The original string is : " + test_str1)

# Test if string is subset of another
# Using all()
res = all(ele in test_str1 for ele in test_str2)

# printing result 
print("Does string contains all the characters of other list? : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
Does string contains all the characters of other list? : True

```