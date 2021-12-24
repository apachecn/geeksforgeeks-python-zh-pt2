# Python 程序从字典中删除第 n 个元素

> 原文:[https://www . geesforgeks . org/python-program-to-remove-n-element-from-kth-key-value-from-dictionary/](https://www.geeksforgeeks.org/python-program-to-remove-nth-element-from-kth-keys-value-from-the-dictionary/)

给定一个带有值列表的字典，我们的任务是编写一个 Python 程序，从 Kth 键的值中移除 N 元素。

**示例:**

> **输入:** test_dict = {"gfg" : [9，4，5，2，3，2]，" is" : [1，2，3，4，3，2]，" best" : [2，2，2，3，4]}，K，N = "gfg "，2
> 
> **输出:** {'gfg': [9，4，5，3]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}
> 
> **说明:** 2 从“gfg”键的值列表中删除。
> 
> **输入:** test_dict = {"gfg" : [9，4，5，2，3，2]，" is" : [1，2，3，4，3，2]，" best" : [2，2，2，3，4]}，K，N = "gfg "，4
> 
> **输出:** {'gfg': [9，5，2，3，2]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}
> 
> **说明:** 4 从“gfg”键的值列表中删除。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+条件语句**

在这种情况下，重新分配所有键及其值，当 K 键出现时，从其值列表中省略 N 的出现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove N from K key's value in dictionary values list
# Using loop + conditional statements

# initializing dictionary
test_dict = {"gfg" : [9, 4, 5, 2, 3, 2],
             "is" : [1, 2, 3, 4, 3, 2],
             "best" : [2, 2, 2, 3, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K, N 
K, N = "gfg", 2

res = dict()
for key, val in test_dict.items():

    # reassigning omitting desired number
    res[key] = (val if key != K else [idx for idx in val if idx != N])

# printing result
print("The altered dictionary : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': [9，4，5，2，3，2]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}
> 
> 修改后的字典:{'gfg': [9，4，5，3]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}

**方法二:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

在这种情况下，我们执行与上述方法类似的任务，不同之处在于使用字典理解，而不是使用传统的循环来循环键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove N from K key's value in dictionary values list
# Using dictionary comprehension

# initializing dictionary
test_dict = {"gfg" : [9, 4, 5, 2, 3, 2],
             "is" : [1, 2, 3, 4, 3, 2], 
             "best" : [2, 2, 2, 3, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K, N 
K, N = "gfg", 2

# dictionary comprehension used for shorthand
res = {key : (val if key != K else [idx for idx in val if idx != N]) for key, val in test_dict.items()}

# printing result
print("The altered dictionary : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': [9，4，5，2，3，2]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}
> 
> 修改后的字典:{'gfg': [9，4，5，3]，' is': [1，2，3，4，3，2]，' best': [2，2，2，3，4]}