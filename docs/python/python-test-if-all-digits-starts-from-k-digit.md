# Python–测试所有数字是否从% K 位开始

> 原文:[https://www . geesforgeks . org/python-test-if-all-digits-start-from-k-digit/](https://www.geeksforgeeks.org/python-test-if-all-digits-starts-from-k-digit/)

有时我们可能会遇到一个问题，如果一个列表包含% K 的数字，我们需要查找它。这个特殊的实用程序在日常编程中有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `map()`**
我们可以通过将元素转换为字符串，然后测试字符串的起始元素来解决这个问题，如果它们是% K，我们可以返回 true，然后转换为 set，并测试结果的大小是否为 1。转换是通过映射完成的，set 函数将字符串的第一个元素转换为 set 并列出理解检查。

```
# Python3 code to demonstrate 
# Test if all digits starts from % K digit
# using list comprehension + map() 

# initializing list 
test_list = [65, 3, 92, 332] 

# printing original list 
print("The original list : " + str(test_list)) 

# initializing K 
K = 3

# using list comprehension + map() 
# Test if all digits starts from % K digit
res = len(set( not(int(sub[0]) % K) for sub in map(str, test_list))) == 1

# print result 
print("Does each element start with % K digit ? " + str(res)) 
```

**Output :**

```
The original list : [65, 3, 92, 332]
Does each element start with % K digit ? True

```