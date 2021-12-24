# Python 程序将字典中具有相似值的键分组

> 原文:[https://www . geesforgeks . org/python-程序到组-字典中值相似的键/](https://www.geeksforgeeks.org/python-program-to-group-keys-with-similar-values-in-a-dictionary/)

给定一个以值为列表的字典。用相似的值将所有键组合在一起。

> **输入**:test _ dict = {“Gfg”:[5，6]，“is”:[8，6，9]，“best”:[10，9]，“for”:[5，2]，“极客”:[19]}
> **输出**:[' Gfg '，' is '，' for']，['is '，' Gfg '，' best']，['best '，' is '，['for '，' Gfg ']
> **解释** : Gfg
> 
> **输入**:test _ dict = {“Gfg”:[6]，“is”:[8，6，9]，“best”:[10，9]，“for”:[5，2]}
> **输出** : [['Gfg '，' is']，['is '，' Gfg '，' best '，' is ']
> **解释** : Gfg 有 6 个，is 有 6 个，遂分组。

**方法:使用 loop + any() + len()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 any()检查每个键是否匹配任何值，len()用于检查匹配的键是否超过 1。迭代部分使用循环进行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group keys with similar values in Dictionary
# Using loop + any() + len()

# initializing dictionary
test_dict = {"Gfg": [5, 6], "is": [8, 6, 9], 
             "best": [10, 9], "for": [5, 2], 
             "geeks": [19]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = []
for key in test_dict:
    chr = [key]
    for ele in test_dict:

        # check with other keys 
        if key != ele:

            # checking for any match in values
            if any(i == j for i in test_dict[key] for j in test_dict[ele]):
                chr.append(ele)
    if len(chr) > 1:
        res.append(chr)

# printing result 
print("The dictionary after values replacement : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': [5，6]，' is': [8，6，9]，' best': [10，9]，' for': [5，2]，' geeks': [19]}
> 
> 值替换后的字典:[['Gfg '，' is '，' for']，['is '，' Gfg '，' best']，['best '，' is']，['for '，' Gfg']]