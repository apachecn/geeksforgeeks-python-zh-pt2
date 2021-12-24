# Python–匹配列表元素中的第 Kth 个数字

> 原文:[https://www . geesforgeks . org/python-match-kth-number-in-list-elements/](https://www.geeksforgeeks.org/python-match-kth-number-digit-in-list-elements/)

有时我们可能会遇到这样一个问题，如果一个列表包含 Kth 索引中具有相同数字的数字，我们需要查找它。这个特殊的工具在日常编程中有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `map()`**
我们可以通过将元素转换为字符串，然后测试字符串的第 Kth 元素来解决这个问题，如果它们相等，我们可以返回 true，然后转换为 set，并测试结果的大小是否为 1。转换是通过映射完成的，set 函数转换为 set 并列出对字符串中 Kth 元素的理解检查。

```py
# Python3 code to demonstrate
# Kth Number digit match
# using list comprehension + map()

# initializing list 
test_list = [467, 565, 2645, 8668]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 1

# using list comprehension + map()
# Kth Number digit match
res = len(set(sub[K] for sub in map(str, test_list))) == 1

# print result
print("Does each element of index K have same digit ? " + str(res))
```

**Output :**

```py
The original list : [467, 565, 2645, 8668]
Does each element of index K have same digit ? True

```