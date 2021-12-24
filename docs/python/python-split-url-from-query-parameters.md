# Python |从查询参数中拆分网址

> 原文:[https://www . geesforgeks . org/python-split-URL-from-query-parameters/](https://www.geeksforgeeks.org/python-split-url-from-query-parameters/)

有时候，在 web 开发中，我们可能会遇到这样一个任务，我们可能需要从 URL 中分离出查询参数，这是由“？”完成的性格。这在网络开发以及其他涉及网址的领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`split()`**
这是我们可以解决这个问题的方法之一。我们分开了？并返回结果的第一部分。

```
# Python3 code to demonstrate working of 
# Split URL from Query Parameters
# Using split()

# initializing string
test_str = 'www.geeksforgeeks.org?is = best'

# printing original string
print("The original string is : " + str(test_str))

# Split URL from Query Parameters
# Using split()
res = test_str.split('?')[0]

# printing result 
print("The base URL is : " + res) 
```

**Output :**

```
The original string is : www.geeksforgeeks.org?is=best
The base URL is : www.geeksforgeeks.org

```