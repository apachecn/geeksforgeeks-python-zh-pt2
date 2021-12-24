# Python–在字典中将值列表重新初始化为 K

> 原文:[https://www . geeksforgeeks . org/python-reinitialize-value-list-to-k-in-dictionary/](https://www.geeksforgeeks.org/python-reinitialize-value-lists-to-k-in-dictionary/)

有时，在使用 Python 字典值时，我们会遇到一个问题，需要将字典中所有键的所有值列表重新初始化为常数 k。这种问题在使用数据的域中可能会有应用，如机器学习和数据科学。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_dict = {'Gfg' : [[4，5]，[8，9，20]，[1，3，4，'哎呀']}
> **输出** : {'Gfg': [[4，4]，[4，4，4，4]，[4，4，4]]}
> **输入** : test_dict = {'Gfg ':“最佳”}
> **输出** : {'Gfg '

**方法:使用递归+ type() +字典理解+ items() + loop**
以上功能的组合可以帮助解决这个问题。在本文中，我们使用字典理解来执行值的赋值，使用 type 来测试类型。items()用于从字典中提取值，并对每个嵌套执行递归处理。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Reinitialize Value lists to K in Dictionary
# Using recursion + type() + dictionary comprehension + items() + loop

# helper function
def helper_fnc(ele, K):
    if type(ele) is list:
        return [helper_fnc(val, K) for val in ele]
    elif type(ele) is dict:
        return {key : helper_fnc(val, K) for key, val in ele.items()}
    return K

# initializing dictionary
test_dict = {'gfg' : [4, 6, 7], 'is' : 8, 'best' : [[4, 5], [8, 9, 20]]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K
K = 4

# Reinitialize Value lists to K in Dictionary
# Using recursion + type() + dictionary comprehension + items() + loop
res = helper_fnc(test_dict, K)

# printing result
print("The Reinitialized dictionary : " + str(dict(res)))
```

**Output : **

原始字典:{'best': [[4，5]，[8，9，20]]，' is': 8，' gfg': [4，6，7]}
重新初始化的字典:{'best': [[4，4]，[4，4，4]]，' is': 4，' gfg': [4，4，4]}