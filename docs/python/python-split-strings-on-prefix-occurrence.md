# Python–前缀出现时拆分字符串

> 原文:[https://www . geesforgeks . org/python-拆分-前缀字符串-出现/](https://www.geeksforgeeks.org/python-split-strings-on-prefix-occurrence/)

给定一个字符串列表，对出现的前缀执行字符串拆分。

> **输入** : test_list = [“极客 forgeeks”、“best”、“极客”、“and”]，pref =“极客”
> **输出**:[“‘极客 forgeeks’、‘best’”、[“极客”、“and”]]
> **解释**:出现字符串“极客”时进行拆分。
> 
> **输入** : test_list = [“好”、“果实”、“善良”、“传播”]，pref =“好”
> **输出** : [[“好”、“果实”]，[“善良”、“传播”]
> **解释**:出现字符串“好”时进行拆分。

**方法#1:使用循环+ startswith()**

在本文中，我们迭代 List 的每个元素，并通过检查前缀来检查是否必须使用 startswith()来更改新列表，如果遇到前缀，则创建新列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split Strings on Prefix Occurrence
# Using loop + startswith()

# initializing list
test_list = ["geeksforgeeks", "best", "geeks", "and", "geeks", "love", "CS"]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix
pref = "geek"

res = []
for val in test_list:

    # checking for prefix
    if val.startswith(pref):

        # if pref found, start new list
        res.append([val])
    else:

        # else append in current list
        res[-1].append(val)

# printing result
print("Prefix Split List : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'best', 'geeks', 'and', 'geeks', 'love', 'CS']
Prefix Split List : [['geeksforgeeks', 'best'], ['geeks', 'and'], ['geeks', 'love', 'CS']]
```

**方法 2:使用 loop+zip _ long()+starts with()**

在这种情况下，我们压缩所有元素及其后续的元素子列表，并使用 startswith()检查前缀，如果找到，结果将被追加。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split Strings on Prefix Occurrence
# Using loop + zip_longest() + startswith()
from itertools import zip_longest

# initializing list
test_list = ["geeksforgeeks", "best", "geeks", "and", "geeks", "love", "CS"]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix
pref = "geek"

res, temp = [], []

for x, y in zip_longest(test_list, test_list[1:]):
    temp.append(x)

    # if prefix is found, split and start new list
    if y and y.startswith(pref):
        res.append(temp)
        temp = []
res.append(temp)

# printing result
print("Prefix Split List : " + str(res))
```

**Output**

```
The original list is : ['geeksforgeeks', 'best', 'geeks', 'and', 'geeks', 'love', 'CS']
Prefix Split List : [['geeksforgeeks', 'best'], ['geeks', 'and'], ['geeks', 'love', 'CS']]
```