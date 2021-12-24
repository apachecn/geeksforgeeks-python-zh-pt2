# Python–匹配成对的支架

> 原文:[https://www . geesforgeks . org/python-匹配对括号/](https://www.geeksforgeeks.org/python-matching-pairs-of-brackets/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们需要将所有元素与合适的结束括号配对，并且可能会有与配对相关联的数据。这种问题是堆栈数据结构的经典应用，可以跨多个领域使用。让我们讨论一下完成这项任务的具体方法。

> **输入** : test_list = [('('，1)，('('，2)，(')'，3)，(')'，4)]
> **输出** : [(2，3)，(1，4)]
> 
> **输入** : test_list = [('('，1)，(')'，4)]
> **输出** : [(1，4)]

**方法:使用栈 DS + loop**
以上功能的组合可以用来解决这个问题。在这种情况下，我们用每个开括号做一个新的对，当相应的闭括号用后进先出法来时，我们用那个闭括号做一个对。

```
# Python3 code to demonstrate working of 
# Matching Pairs of Brackets
# Using stack DS + loop

# initializing list
test_list = [('(', 7), ('(', 9), (')', 10), (')', 11), ('(', 15), (')', 100)]

# printing original list
print("The original list is : " + str(test_list))

# Matching Pairs of Brackets
# Using stack DS + loop
stck = []
res = []
for ele1, ele2 in test_list:
    if '(' in ele1:
        stck.append((ele1, ele2))
    elif ')' in ele1:
        res.append((stck.pop()[1], ele2))

# printing result 
print("The paired elements : " + str(res)) 
```

**Output :**

```
The original list is : [('(', 7), ('(', 9), (')', 10), (')', 11), ('(', 15), (')', 100)]
The paired elements : [(9, 10), (7, 11), (15, 100)]

```