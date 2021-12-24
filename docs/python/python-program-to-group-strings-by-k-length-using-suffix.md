# Python 程序使用后缀

按 K 长度分组字符串

> 原文:[https://www . geesforgeks . org/python-程序到组-字符串-按 k-长度-使用-后缀/](https://www.geeksforgeeks.org/python-program-to-group-strings-by-k-length-using-suffix/)

给定字符串列表，任务是编写一个 Python 程序，将它们分组为 K 长度后缀。

> **输入**:test _ list =[“food”、“peak”、“geek”、“good”、“weak”、“sneek”]，K = 3
> **输出**:{“ood”:[“food”、“good”]、“eak”:[“peak”、“weak”]、“eek”:[“geek”、“sneek”]}
> **解释**:以 ood 结尾的词为 food 和 good，遂分组。
> 
> **输入** : test_list = [“峰”、“极客”、“好”、“弱”]，K = 3
> **输出**:{“ood”:[“好”]、“eak”:[“峰”、“弱”]、“eek”:[“极客”]}
> **解释**:以 ood 结尾的词为好，遂分组。

**方法 1 :** 使用[尝试/除](https://www.geeksforgeeks.org/python-try-except/) +循环

在这种情况下，我们提取最后的 K 个字符并形成一个字符串，并追加到与其对应的现有键的列表中，如果没有找到，它将通过 catch 流并创建一个新的键，其列表中的第一个单词已初始化。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group Strings by K length Suffix
# Using try/except + loop

# initializing list
test_list = ["food", "peak", "geek",
             "good", "weak", "sneek"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

res = {}
for ele in test_list:

    # extracting suffix
    suff = ele[-K : ]

    # appending if key found, else creating new one
    try: 
        res[suff].append(ele)
    except:
        res[suff] = [ele]

# printing result 
print("The grouped suffix Strings : " + str(res))
```

**输出:**

> 原列表为:['food '，' peak '，' geek '，' good '，' weak '，' sneek']
> 分组后缀字符串:{'ood': ['food '，' good']，' eak': ['peak '，' weak']，' eek': ['geek '，' sneek']}

**方法二:**使用 [defaultdict()](https://www.geeksforgeeks.org/defaultdict-in-python/) +循环。

此方法避免了使用 try/except 块的需要，因为默认列表初始化是由 defaultdict()处理的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group Strings by K length Suffix
# Using defaultdict() + loop
from collections import defaultdict

# initializing list
test_list = ["food", "peak", "geek",
             "good", "weak", "sneek"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

res = defaultdict(list)
for ele in test_list:

    # extracting suffix
    suff = ele[-K : ]

    # appending into matched suffix key
    res[suff].append(ele)

# printing result 
print("The grouped suffix Strings : " + str(dict(res)))
```

**输出:**

> 原列表为:['food '，' peak '，' geek '，' good '，' weak '，' sneek']
> 分组后缀字符串:{'ood': ['food '，' good']，' eak': ['peak '，' weak']，' eek': ['geek '，' sneek']}