# Python–替换分隔符

> 原文:[https://www.geeksforgeeks.org/python-replace-delimiter/](https://www.geeksforgeeks.org/python-replace-delimiter/)

给定字符串列表和替换分隔符，替换每个字符串中的当前分隔符。

> **输入**:test _ list =[“a，t”，“g，f，g”，“w，e”，“d，o”]，repl_delim = ' '
> **输出**:[“a t”，“g f g”，“w e”，“d o”]
> **说明:**每个字符串处逗号替换为空格。
> 
> **输入** : test_list = ["g#f#g"]，repl_delim = '，'
> **输出** : ["g，f，g"]
> **解释**:每个字符串处用逗号代替 hash。

**方法#1:使用`replace()` +循环**
以上功能的结合提供了一种蛮力的方法来解决这个问题。在这种情况下，循环用于遍历每个字符串，并使用 replace()执行替换。

```py
# Python3 code to demonstrate working of 
# Replace delimiter
# Using loop + replace()

# initializing list
test_list = ["a, t", "g, f, g", "w, e", "d, o"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing replace delimiter
repl_delim = '#'

# Replace delimiter
res = []
for ele in test_list:

    # adding each string after replacement using replace()
    res.append(ele.replace(", ", repl_delim))

# printing result 
print("Replaced List : " + str(res))
```

**Output :**

```py
The original list is : ['a, t', 'g, f, g', 'w, e', 'd, o']
Replaced List : ['a#t', 'g#f#g', 'w#e', 'd#o']

```

**方法 2:使用列表理解+ `replace()`**
以上功能的组合可以为这个问题提供一个线性。这类似于上面的方法，只是封装在列表理解中。

```py
# Python3 code to demonstrate working of 
# Replace delimiter
# Using list comprehension + replace()

# initializing list
test_list = ["a, t", "g, f, g", "w, e", "d, o"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing replace delimiter
repl_delim = '#'

# Replace delimiter
# iterating inside comprehension, performing replace using replace()
res = [sub.replace(', ', repl_delim) for sub in test_list]

# printing result 
print("Replaced List : " + str(res))
```

**Output :**

```py
The original list is : ['a, t', 'g, f, g', 'w, e', 'd, o']
Replaced List : ['a#t', 'g#f#g', 'w#e', 'd#o']

```