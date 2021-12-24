# Python–按总字符排序矩阵

> 原文:[https://www . geeksforgeeks . org/python-按总字符排序-矩阵/](https://www.geeksforgeeks.org/python-sort-matrix-by-total-characters/)

给定字符串矩阵，按总数据排序，即每行总字符数。

> **输入**:test _ list =[[“Gfg”、“is”、“Best”]、[“Geeksforgeeks”、“Best”]、[“ILvGFG”]]
> **输出**:[“‘ILvGFG’]、[‘Gfg’、‘is’、‘Best’]、[‘Geeksforgeeks’、‘Best’]
> **解释** : 6 < 11 <排序后共分别 17 个字符。
> 
> **输入**:test _ list =[[“Geeksforgeeks”，“Best”]，[“ILvGFG”]
> **输出**:[[‘ILvGFG’]，[‘Geeksforgeeks’，‘Best’]
> **解释** : 6 <排序后分别合计 17 个字符。

**方法#1:使用 sort()+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)

在本文中，我们使用 sort()执行排序任务，使用 len()和 sum()完成获取总字符数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Matrix by total characters
# Using sort() + len() + sum()

def total_chars(row):

    # getting total characters
    return sum([len(sub) for sub in row])

# initializing list
test_list = [["Gfg", "is", "Best"], ["Geeksforgeeks", "Best"],
             ["GFg", "4", "good"], ["ILvGFG"]]

# printing original list
print("The original list is : " + str(test_list))

# calling utility fnc
test_list.sort(key=total_chars)

# printing result
print("Sorted results : " + str(test_list))
```

**输出:**

> 原列表为:[['Gfg '，' is '，' Best']，['Geeksforgeeks '，' Best']，['Gfg '，' 4 '，' good']，['ILvGFG']]
> 排序结果:[['ILvGFG '，' 4 '，' good']，['GFg '，' is '，' Best']，['Geeksforgeeks '，' Best']

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

其中，sorted()用于获取排序结果，lambda 函数代替外部函数获取字符串排序逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Matrix by total characters 
# Using sorted() + lambda

# initializing list
test_list = [["Gfg", "is", "Best"], ["Geeksforgeeks", "Best"],
             ["GFg", "4", "good"], ["ILvGFG"]]

# printing original list
print("The original list is : " + str(test_list))

# sorted() gives sorted result 
# lambda function providing logic
res = sorted(test_list, key = lambda row : sum([len(sub) for sub in row]))

# printing result 
print("Sorted results : " + str(res))
```

**输出:**

> 原列表为:[['Gfg '，' is '，' Best']，['Geeksforgeeks '，' Best']，['Gfg '，' 4 '，' good']，['ILvGFG']]
> 
> 排序结果:[['ILvGFG']，['GFg '，' 4 '，' good']，['Gfg '，' is '，' Best']，['Geeksforgeeks '，' Best']]