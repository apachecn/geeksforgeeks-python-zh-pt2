# Python–删除与 K 键匹配值的字典

> 原文:[https://www . geesforgeks . org/python-remove-dictionary-with-matching-values-with-k-key/](https://www.geeksforgeeks.org/python-remove-dictionaries-with-matching-values-with-k-key/)

给定两个字典列表，从其他字典列表中移除所有具有相似 K 键值的字典。

> **输入** : test_list = [{'Gfg' : 3、【is】:3、【最佳】:9}、
> {'Gfg' : 8、【is】:4、【最佳】:2}、
> {'Gfg' : 9、【is】:2、【最佳】:4}、
> {'Gfg' : 8、【is】:10、【最佳】:3}、
> {'Gfg' : 7、【is】:1、【最佳】:7}]、check_list = [{'Gfg' : 8、【最佳】:1}、{“” best': 9}、{'Gfg': 9、' is': 10、' best': 3}]
> **说明**:所有“Gfg”值为 8 或 7 的字典都被删除。
> 
> **输入** : test_list = [{'Gfg' : 3，" is" : 3，" best" : 9}，
> {'Gfg' : 8，" is" : 4，" best" : 2}]，check_list = [{'Gfg' : 8，" Best" : 1}，{"Best" : 2，" Gfg" : 7}]，K = "Gfg"
> **输出** : [{'Gfg': 3，' is': 3，' best': 9}]
> **解释**:所有字典用

**方法:使用列表理解+词典理解**

在这种情况下，我们使用字典理解来执行获取一组元素的任务，然后使用列表理解通过测试 K 键的值在所构建的值集中的缺失来构建新的列表。

整个任务分两步进行，

*   使用 *set()* 从 *K* 键对应的 *check_list* 中提取所有唯一值。
*   检查测试列表中每个字典的键 *K* 的值，如果它存在于第一步创建的集合中，则该字典在结果中被省略，否则字典作为结果被添加。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Dictionaries with Matching Values with K Key
# Using dictionary comprehension + list comprehension

# initializing list
test_list = [{'Gfg': 3, "is": 3, "best": 9},
             {'Gfg': 8, "is": 4, "best": 2},
             {'Gfg': 1, "is": 2, "best": 4},
             {'Gfg': 9, "is": 10, "best": 3},
             {'Gfg': 7, "is": 1, "best": 7}]

# printing original list
print("The original list is : " + str(test_list))

# initializing check dictionary list
check_list = [{'Gfg': 8, "Best": 1}, {"Best": 2, "Gfg": 7}]

# initializing Key
K = "Gfg"

# getting set of values
temp = {sub[K] for sub in check_list}

# checking for value occurrence in test dictionary using in
# filtering only with no matching values
res = [sub for sub in test_list if sub[K] not in temp]

# printing result
print("Dictionary list after removal : " + str(res))
```

**输出:**

> 原始列表为:[{'Gfg': 3，' is': 3，' best': 9}，{'Gfg': 8，' is': 4，' best': 2}，{ ' Gfg ':2，' best': 4}，{'Gfg': 9，' is': 10，' best': 3}，{'Gfg': 7，' is': 1，' best': 7}]
> 删除后的字典列表:[{'Gfg': 3，' is': 3，' best ' }，{'Gfg': 1，' is': 2，' best': 4