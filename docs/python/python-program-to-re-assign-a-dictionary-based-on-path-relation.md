# Python 程序根据路径关系重新分配字典

> 原文:[https://www . geesforgeks . org/python-程序-重新分配-基于字典的路径关系/](https://www.geeksforgeeks.org/python-program-to-re-assign-a-dictionary-based-on-path-relation/)

给定一个字典，任务是制定一个 python 程序，使用它的键和值之间的路径关系来重新分配它，即一个键的值是另一个键的值。

**示例:**

> **输入** : test_dict = {3 : 4，5 : 6，4 : 8，6 : 9，8 : 10}
> **输出** : {3: 10，5: 9，4: 10，6: 9，8: 10}
> **解释**:键 3 有值 4。键 4 的值为 8。键 8 的值为 10。没有键 10，因此在新字典中，键将具有值 10。
> 
> 同样，键 5 的值为 6。键 6 的值为 9。没有键 9，因此在新字典中，键 5 的值为 9。

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*键()*](https://www.geeksforgeeks.org/python-dictionary/)

在这种情况下，我们对每个关键字进行迭代，并通过使用外部函数来重复检查每个值是否是字典中其他项目的关键字，从而找到其深度。

## 蟒蛇 3

```py
def find_depth(ele, dicti):

    # finding depth
    for idx in range(len(list(dicti.keys()))):

        # assigning value as key if found
        if ele in list(dicti.keys()):
            ele = dicti[ele]
    return ele

# initializing dictionary
test_dict = {3: 4, 5: 6, 4: 8, 6: 9, 8: 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = dict()

# iterating for each key
for key, val in list(test_dict.items()):
    test_dict.pop(key)
    res[key] = find_depth(val, test_dict)

# printing result
print("The reassigned dictionary : " + str(res))
```

**输出:**

> 原始词典是:{3: 4，5: 6，4: 8，6: 9，8: 10}
> 
> 重新分配的词典:{3: 10，5: 9，4: 10，6: 9，8: 10}