# Python–使用字典替换数字

> 原文:[https://www . geesforgeks . org/python-替换-数字-使用-字典/](https://www.geeksforgeeks.org/python-substitute-digits-using-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要对列表中每个元素的数字进行替换。这可能会导致数量的变化。这种问题可能发生在数据预处理领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [45，32]，dig_map = {4 : 2，3 : 8，2 : 6，5 : 7}
> 输出 : [27，86]
> 
> **输入** : test_list = [44，44]，dig _ map = { 4:2 }
> T3】输出 : [22，22]

**方法#1:使用循环**
这是解决这个问题的蛮方法。在这种情况下，我们遍历列表中的每个元素，并在将数字转换为字符串后使用映射值重新创建它。

```py
# Python3 code to demonstrate working of 
# Substitute digits using Dictionary
# Using loop 

# initializing list
test_list = [45, 32, 87, 34, 21, 91] 

# printing original list
print("The original list is : " + str(test_list))

# initializing digit mapping
dig_map = {1 : 4, 4 : 2, 3 : 8, 2 : 6, 7 : 5, 9 : 3, 8 : 9, 5 : 7}

# Substitute digits using Dictionary
# Using loop 
temp = []
for idx, ele  in enumerate(test_list):
    sub1 = str(ele)
    if len(sub1) > 1:
        sub2 = ""
        for j in sub1:
            if int(j) in dig_map:
                sub2 += str(dig_map[int(j)])
                test_list[idx] = int(sub2)
    else:
        if ele in dig_map:
            test_list[idx] = dig_map[ele]

# printing result 
print("List after Digit Substitution : " + str(test_list))
```

**Output :**

```py
The original list is : [45, 32, 87, 34, 21, 91]
List after Digit Substitution : [27, 86, 95, 82, 64, 34]

```

**方法 2:使用`join() + list comprehension + str() + int()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 str()和 int()执行相互转换的任务，连接和列表理解用于以速记的形式绑定逻辑。

```py
# Python3 code to demonstrate working of 
# Substitute digits using Dictionary
# Using join() + list comprehension + str() + int()

# initializing list
test_list = [45, 32, 87, 34, 21, 91] 

# printing original list
print("The original list is : " + str(test_list))

# initializing digit mapping
dig_map = {1 : 4, 4 : 2, 3 : 8, 2 : 6, 7 : 5, 9 : 3, 8 : 9, 5 : 7}

# Substitute digits using Dictionary
# Using join() + list comprehension + str() + int()
res = [int(''.join([str(dig_map[int(ele)]) for ele in str(sub)])) for sub in test_list]

# printing result 
print("List after Digit Substitution : " + str(res))
```

**Output :**

```py
The original list is : [45, 32, 87, 34, 21, 91]
List after Digit Substitution : [27, 86, 95, 82, 64, 34]

```