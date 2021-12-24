# Python–测试所有列表元素中的后数字匹配

> 原文:[https://www . geesforgeks . org/python-test-后数字-全列表匹配-元素/](https://www.geeksforgeeks.org/python-test-rear-digit-match-in-all-list-elements/)

有时我们可能会遇到一个问题，如果一个列表包含以相同数字结尾的数字，我们需要查找它。这个特殊的工具在日常编程中有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `map()`**
我们可以通过将元素转换为字符串，然后测试字符串的结束元素来解决这个问题，如果它们相等，我们可以返回 true，然后转换为 set 并测试结果的大小是否为 1。转换是通过映射完成的，set 函数将字符串的最后一个元素转换为 set 并列出理解检查。

```
# Python3 code to demonstrate
# Test rear digit match
# using list comprehension + map()

# initializing list 
test_list = [45, 545, 2345, 8765]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + map()
# Test rear digit match
res = len(set(sub[-1] for sub in map(str, test_list))) == 1

# print result
print("Does each element end with same digit ? " + str(res))
```

**Output :**

```
The original list : [45, 545, 2345, 8765]
Does each element end with same digit ? True

```