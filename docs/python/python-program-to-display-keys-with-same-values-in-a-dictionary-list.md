# Python 程序在字典列表中显示具有相同值的键

> 原文:[https://www . geesforgeks . org/python-程序到显示-字典列表中值相同的键/](https://www.geeksforgeeks.org/python-program-to-display-keys-with-same-values-in-a-dictionary-list/)

给定一个包含所有字典元素的列表，任务是编写一个 Python 程序来提取所有字典中具有相似值的键。

**示例:**

> **输入**:test _ list =[{“Gfg”:5，“is”:8，“best”:0 }、{“Gfg”:5，“is”:1，“best”:0 }、{“Gfg”:5，“is”:0，“best”:0 }]
> **输出**:[‘Gfg’，‘best’]
> **解释**:所有 Gfg 值都是 5，best 在所有字典中都有 0 作为它的所有值。
> 
> **输入**:test _ list =[{“Gfg”:5，“is”:8、“best”:1 }、{“Gfg”:5、“is”:1、“best”:0 }、{“Gfg”:5、“is”:0、“best”:0 }]
> **输出**:[‘Gfg’]
> **解释**:所有 Gfg 值均为 5。

**方法 1 :** *使用* [*键()*](https://www.geeksforgeeks.org/python-dictionary/) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在本文中，我们使用循环遍历列表中的所有元素，并使用 key()提取密钥。对于每个关键字，比较每个字典的关键字，如果发现相似，则将关键字添加到结果中。

## 蟒蛇 3

```
# initializing Matrix
test_list = [{"Gfg": 5, "is": 8, "best": 0},
             {"Gfg": 5, "is": 1, "best": 0},
             {"Gfg": 5, "is": 0, "best": 0}]

# printing original list
print("The original list is : " + str(test_list))

# getting keys
keys = list(test_list[0].keys())

res = []
# iterating each dictionary for similar key's value
for key in keys:
    flag = 1
    for ele in test_list:

        # checking for similar values
        if test_list[0][key] != ele[key]:
            flag = 0
            break

    if flag:
        res.append(key)

# printing result
print("Similar values keys : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 5，' is': 8，' best': 0}，{'Gfg': 5，' is': 1，' best': 0}，{'Gfg': 5，' is': 0，' best': 0}]
> 
> 相似的值键:['Gfg '，' best']

**方法二:** *使用*[*all()*](https://www.geeksforgeeks.org/any-all-in-python/)*[*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*键()*](https://www.geeksforgeeks.org/python-dictionary/)*

*在这种情况下，避免了内部循环，并用 all()替换，all()检查所有具有相似值的键，然后提取该键。*

## *蟒蛇 3*

```
*# initializing Matrix
test_list = [{"Gfg": 5, "is": 8, "best": 0},
             {"Gfg": 5, "is": 1, "best": 0},
             {"Gfg": 5, "is": 0, "best": 0}]

# printing original list
print("The original list is : " + str(test_list))

# getting keys
keys = list(test_list[0].keys())

res = []

# iterating each dictionary for similar key's value
for key in keys:

    # using all to check all keys with similar values
    flag = all(test_list[0][key] == ele[key] for ele in test_list)

    if flag:
        res.append(key)

# printing result
print("Similar values keys : " + str(res))*
```

***输出:***

> *原始列表为:[{'Gfg': 5，' is': 8，' best': 0}，{'Gfg': 5，' is': 1，' best': 0}，{'Gfg': 5，' is': 0，' best': 0}]*
> 
> *相似的值键:['Gfg '，' best']*