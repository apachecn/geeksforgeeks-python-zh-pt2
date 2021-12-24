# Python–替换字典中的单词

> 原文:[https://www . geesforgeks . org/python-replace-word-from-dictionary/](https://www.geeksforgeeks.org/python-replace-words-from-dictionary/)

给定字符串，从查找字典中替换它的单词。

> **输入** : test_str = '极客最适合极客'，repl_dict = {“极客”:“所有 CS 野心家”}
> **输出**:极客最适合所有 CS 野心家
> **解释**:“极客”一词替换为查找值。
> 
> **输入** : test_str = '极客最适合极客的极客锻链'，repl_dict = {“好”:“所有 CS 野心家”}
> **输出**:极客最适合极客的极客锻链
> **解释**:无查找值，结果不变。

**方法#1:使用 split() + get() + join()**

在本文中，我们首先使用 split()拆分列表，然后使用 get()查找，如果找到，则使用 join()替换并连接回字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace words from Dictionary
# Using split() + join() + get()

# initializing string
test_str = 'geekforgeeks best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# lookup Dictionary
lookp_dict = {"best" : "good and better", "geeks" : "all CS aspirants"}

# performing split()
temp = test_str.split()
res = []
for wrd in temp:

    # searching from lookp_dict
    res.append(lookp_dict.get(wrd, wrd))

res = ' '.join(res)

# printing result 
print("Replaced Strings : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks best for geeks
Replaced Strings : geekforgeeks good and better for all CS aspirants

```

**方法 2:使用列表理解+连接()**

与上述方法类似，区别只是 1 行，而不是 3-4 步。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace words from Dictionary
# Using list comprehension + join()

# initializing string
test_str = 'geekforgeeks best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# lookup Dictionary
lookp_dict = {"best" : "good and better", "geeks" : "all CS aspirants"}

# one-liner to solve problem
res = " ".join(lookp_dict.get(ele, ele) for ele in test_str.split())

# printing result 
print("Replaced Strings : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks best for geeks
Replaced Strings : geekforgeeks good and better for all CS aspirants

```