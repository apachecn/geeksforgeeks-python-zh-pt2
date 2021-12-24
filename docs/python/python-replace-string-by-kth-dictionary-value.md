# Python–用第 k 个字典值替换字符串

> 原文:[https://www . geesforgeks . org/python-replace-string by-kth-dictionary-value/](https://www.geeksforgeeks.org/python-replace-string-by-kth-dictionary-value/)

给定字符串列表，用映射列表的 Kth 值替换映射的值。

> **输入**:test _ list =[“Gfg”，“is”，“Best”]，subs _ dict = {“Gfg”:[5，6，7]，“is”:[7，4，2]}，K = 0
> **输出** : [5，7，“Best”]
> **解释**:“Gfg”和“is”替换为 5，7 作为字典值列表中的第 0 个索引。
> 
> **输入**:test _ list =[“Gfg”、“is”、“Best”]，subs _ dict = {“Gfg”:[5，6，7]，“Best”:[7，4，2]}，K = 0
> **输出** : [5，“is”，7]
> **解释**:“Gfg”和“Best”替换为 5，7 作为字典值列表中的第 0 个索引。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在本文中，我们在列表理解中的单行内执行任务迭代和条件替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace String by Kth Dictionary value  
# Using list comprehension

# initializing list
test_list = ["Gfg", "is", "Best"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {
    "Gfg" : [5, 6, 7], 
    "is" : [7, 4, 2], 
}

# initializing K 
K = 2

# using list comprehension to solve
# problem using one liner
res = [ele if ele not in subs_dict else subs_dict[ele][K]
                                     for ele in test_list]

# printing result 
print("The list after substitution : " + str(res))
```

**Output**

```
The original list : ['Gfg', 'is', 'Best']
The list after substitution : [7, 2, 'Best']

```

**方法二:使用 get() +列表理解**

上述功能的组合可以用来解决这个问题。在本文中，我们使用列表理解进行迭代，并使用 get()检查键的存在和替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace String by Kth Dictionary value  
# Using get() + list comprehension

# initializing list
test_list = ["Gfg", "is", "Best"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {
    "Gfg" : [5, 6, 7], 
    "is" : [7, 4, 2], 
}

# initializing K 
K = 2

# using list comprehension to solve problem using one liner
# get() to perform presence checks and assign default value
res = [subs_dict.get(ele, ele) for ele in test_list]
res = [ele[K] if isinstance(ele, list) else ele for ele in res] 

# printing result 
print("The list after substitution : " + str(res))
```

**Output**

```
The original list : ['Gfg', 'is', 'Best']
The list after substitution : [7, 2, 'Best']

```