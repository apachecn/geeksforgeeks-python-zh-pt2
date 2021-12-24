# Python–将列表值键合并到矩阵中

> 原文:[https://www . geesforgeks . org/python-merge-list-value-key-to-matrix/](https://www.geeksforgeeks.org/python-merge-list-value-keys-to-matrix/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要执行字典中某些键的合并。在这种情况下，我们倾向于形成一个结果奇异键矩阵。这种问题在数据领域也有应用。让我们讨论一下执行这项任务的具体方法。

> **输入**:test _ dict = { ' mathematics ':[1，2]，' gfg': [4，5]，' CS': [6]}
> **输出** : {'merge_key': [[4，5]，[6]，[1，2]]}
> 
> **输入**:test _ dict = { ' mathematics ':[1]，' gfg': [4]，' CS': [9]}
> **输出** : {'merge_key': [[4]，[9]，[1]]}

**方法:使用 loop + `pop()`**
这个任务可以使用蛮力方式来执行。在这种情况下，我们迭代键并使用 pop 移除键，在合并成矩阵后重新初始化它们。

```
# Python3 code to demonstrate working of 
# Merge List value Keys to Matrix
# Using loop + pop()

# initializing dictionary
test_dict = {'gfg' : [4, 5, 6], 
             'is' : [8, 8, 9],
             'CS' : [1, 3, 8], 
             'Maths' : [1, 2]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing list 
que_list = ['gfg', 'CS', 'Maths']

# Merge List value Keys to Matrix
# Using loop + pop()
new_data = [test_dict.pop(ele) for ele in que_list]
test_dict["merge_key"] = new_data

# printing result 
print("The dictionary after merging : " + str(test_dict)) 
```

**Output :**

> 原字典:{'is': [8，8，9]，' gfg': [4，5，6]，' mathematics ':[1，2]，' CS': [1，3，8]}
> 合并后的字典:{'is': [8，8，9]，' merge_key': [[4，5，6]，[1，3，8]，[1，2]]}