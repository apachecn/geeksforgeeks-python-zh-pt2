# Python |将列表中的连续字符串配对

> 原文:[https://www . geesforgeks . org/python-对列表中的连续字符串/](https://www.geeksforgeeks.org/python-pair-the-consecutive-character-strings-in-a-list/)

有时在编程时，我们会面临一个问题，即我们需要执行连续的元素连接。这个问题可能发生在学校编程或竞争性编程的时候。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `zip()`**
结合以上功能可以解决这个问题。在本文中，我们使用列表理解来迭代列表，并使用 zip()来形成对。

```
# Python3 code to demonstrate working of
# Consecutive element pairing in list
# using list comprehension + zip()

# initialize list 
test_list = ["G", "F", "G", "I", "S", "B", "E", "S", "T"]

# printing original list 
print("The original list : " + str(test_list))

# Consecutive element pairing in list
# using list comprehension + zip()
res = [i + j for i, j in zip(test_list, test_list[1:])]

# printing result
print("List after Consecutive concatenation is : " + str(res))
```

**Output :**

> 原列表:['G '，' F '，' G '，' I '，' S '，' B '，' E '，' S '，' T']
> 连续串联后的列表为:['GF '，' FG '，' GI '，' is '，' SB '，' BE '，' ES '，' st '