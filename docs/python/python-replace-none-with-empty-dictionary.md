# Python–用空字典替换无

> 原文:[https://www . geesforgeks . org/python-以空字典替换无/](https://www.geeksforgeeks.org/python-replace-none-with-empty-dictionary/)

给定字典，用空字典替换每个嵌套中的无值。

> **输入**:test _ dict = {“Gfg”:{ 1:None，7 : None}，“is”:None，“Best”:[1，{ 5 : None }，9，3]}
> **输出** : {'Gfg': {1: {}，7: {}}，' is ' { }，' Best': [1，{5: {}，9，3]}
> **解释**:所有 None 值均被空字典替换。
> 
> **输入**:test _ dict = {“Gfg”:{ 7:None }、“is”:None、“Best”:[1、{ 5 : None }、9、3]}
> **输出**:{“Gfg”:{ 7:{ }、“is”:{ }、“Best”:[1、{5: {}、9、3]}
> **解释**:所有 None 值都被空字典替换。

**方法:使用递归+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)

在本文中，我们使用 isinstance()检查字典实例，并调用递归进行嵌套字典替换。这还会检查列表元素形式的嵌套实例，并使用 isinstance()检查列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace None with Empty Dictionary
# Using recursion + isinstance()

# helper function to perform task

def replace_none(test_dict):

    # checking for dictionary and replacing if None
    if isinstance(test_dict, dict):

        for key in test_dict:
            if test_dict[key] is None:
                test_dict[key] = {}
            else:
                replace_none(test_dict[key])

    # checking for list, and testing for each value
    elif isinstance(test_dict, list):
        for val in test_dict:
            replace_none(val)

# initializing dictionary
test_dict = {"Gfg": {1: None, 7: 4}, "is": None,
             "Best": [1, {5: None}, 9, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# calling helper fnc
replace_none(test_dict)

# printing result
print("The converted dictionary : " + str(test_dict))
```

**输出:**

> 原始字典为:{'Gfg': {1: None，7: 4}，' is': None，' Best': [1，{5: None}，9，3]}
> 转换后的字典为:{'Gfg': {1: {}，7: 4}，' is': {}，' Best': [1，{5: {}，9，3]}