# Python–将首字母渲染为字典键

> 原文:[https://www . geesforgeks . org/python-render-声母-as-dictionary-key/](https://www.geeksforgeeks.org/python-render-initials-as-dictionary-key/)

给定字符串列表，转换为以键作为初始值的字典。在单词首字母相似的情况下不起作用。

> **输入**:test _ list =[“geeksforgeeks”，“is”，“best”]
> **输出**:{“g”:“geeksforgeeks”，“I”:“is”，“b”:“best”}
> **解释**:从初始字符构造的键。
> **输入**:test _ list =[“geeksforgeeks”，“best”]
> **输出**:{ ' g ':“geeksforgeeks”，“b”:“best”}
> **解释**:从初始字符构造的键。

**方法#1:使用循环**

在这种情况下，我们通过使用字符串元素访问获取初始元素，并将值呈现为列表元素来创建每个字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Render Initials as Dictionary Key
# Using loop

# initializing list
test_list = ["geeksforgeeks", "is", "best"]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
for ele in test_list:

    # assigning initials as key
    res[ele[0]] = ele

# printing result 
print("Constructed Dictionary : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'is', 'best']
Constructed Dictionary : {'g': 'geeksforgeeks', 'i': 'is', 'b': 'best'}

```

**方法二:利用词典理解**

在这种情况下，我们使用与上述方法类似的速记方法创建字典，为实际问题提供一种线性替代方法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Render Initials as Dictionary Key
# Using dictionary comprehension 

# initializing list
test_list = ["geeksforgeeks", "is", "best"]

# printing original list
print("The original list is : " + str(test_list))

# constructing dictionary
res = {ele[0] : ele for ele in test_list}

# printing result 
print("Constructed Dictionary : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'is', 'best']
Constructed Dictionary : {'g': 'geeksforgeeks', 'i': 'is', 'b': 'best'}

```