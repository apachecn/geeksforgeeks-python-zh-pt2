# Python |从字符串列表中删除冗余子字符串

> 原文:[https://www . geesforgeks . org/python-remove-reduntant-substrings-from-strings-list/](https://www.geeksforgeeks.org/python-remove-reduntant-substrings-from-strings-list/)

给定字符串列表，任务是移除所有字符串，这些字符串是其他字符串的子字符串。

> **输入**:test _ list =[“Gfg”、“Gfg 最好”、“极客”、“for”、“Gfg 是极客”]
> **输出**:[‘Gfg 最好’、‘Gfg 是极客’]
> **解释**:“Gfg”、“for”和“极客”在其他字符串中作为子字符串出现。
> **输入**:test _ list =【“Gfg”、“Geeks”、“for”、“Gfg 是 Geeks”】
> **输出**:【‘Gfg 是 Geeks’】
> **解释**:“Gfg”、“for”和“Geeks”在其他字符串中作为子字符串出现。

**方法#1:使用 enumerate() + join() + sort()**

上述功能的组合可以用来解决这个问题。在这种情况下，首先对长度参数进行排序，用其他词检查当前词，如果它作为子串出现，如果是，则从过滤结果中排除。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Reduntant Substrings from Strings List
# Using enumerate() + join() + sort()

# initializing list
test_list = ["Gfg", "Gfg is best", "Geeks", "Gfg is for Geeks"]

# printing original list
print("The original list : " + str(test_list))

# using loop to iterate for each string
test_list.sort(key = len)
res = []
for idx, val in enumerate(test_list):

    # concatenating all next values and checking for existence
    if val not in ', '.join(test_list[idx + 1:]):
        res.append(val)

# printing result
print("The filtered list : " + str(res))
```

**Output**

```
The original list : ['Gfg', 'Gfg is best', 'Geeks', 'Gfg is for Geeks']
The filtered list : ['Gfg is best', 'Gfg is for Geeks']
```

**方法 2:使用列表理解+联接()+枚举()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们以与上面类似的方式执行任务，只是在列表理解方面有更紧密的区别。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Reduntant Substrings from Strings List
# Using list comprehension + join() + enumerate()

# initializing list
test_list = ["Gfg", "Gfg is best", "Geeks", "Gfg is for Geeks"]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension to iterate for each string
# and perform join in one liner
test_list.sort(key = len)
res = [val for idx, val in enumerate(test_list) if val not in ', '.join(test_list[idx + 1:])]

# printing result
print("The filtered list : " + str(res))
```

**Output**

```
The original list : ['Gfg', 'Gfg is best', 'Geeks', 'Gfg is for Geeks']
The filtered list : ['Gfg is best', 'Gfg is for Geeks']
```