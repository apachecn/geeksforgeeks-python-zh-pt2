# Python 程序按标点计数对字符串进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按标点符号对字符串进行排序-计数/](https://www.geeksforgeeks.org/python-program-to-sort-strings-by-punctuation-count/)

给定字符串列表，按标点符号排序计数。

> **输入**:test _ list =[“gfg@%^”、“是”、“最好！”】
> 输出 : ['是'，'最好！'，'gfg@%^'】
> **解释** : 0 < 1 < 3，按标点计数排序。
> 
> **输入**:test _ list =[“gfg@%^”，“最好！”】
> 输出:【‘最好！’，'gfg@%^'】
> **解释** : 1 < 3，按标点计数排序。

**方法#1:使用** [**字符串.标点符号**](https://www.geeksforgeeks.org/string-punctuation-in-python/) **+** [**排序()**](https://www.geeksforgeeks.org/sort-in-python/)

在这种情况下，排序使用 sort()完成，标点符号从字符串库中的标点符号池中提取。执行就地排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Strings by Punctuation count
# Using string.punctuation + sort()
from string import punctuation

def get_pnc_count(string):

    # getting punctuation count
    return len([ele for ele in string if ele in punctuation])

# initializing list
test_list = ["gfg@%^", "is", "Best!", "fo@#r", "@#$ge24eks!"]

# printing original list
print("The original list is : " + str(test_list))

# performing inplace sort
test_list.sort(key = get_pnc_count)

# printing result
print("Sorted Strings list : " + str(test_list))
```

**输出:**

> 最初的名单是:['gfg@%^'，‘是’、‘最好！’、' fo@#r '、' @#$ge24eks！']
> 排序字符串列表:['是'，'最佳！'，' fo@#r '，'gfg@%^'，' @#$ge24eks！'】

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+标点+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在这种情况下，我们使用 sorted()使用 lambda 执行排序，以避免外部函数执行过滤使用标点符号提取的标点符号的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Strings by Punctuation count
# Using sorted() + punctuation + lambda
from string import punctuation

# initializing list
test_list = ["gfg@%^", "is", "Best!", "fo@#r", "@#$ge24eks!"]

# printing original list
print("The original list is : " + str(test_list))

# performing sort using sorted() with lambda
# function for filtering
res = sorted(test_list, key=lambda string: len(
    [ele for ele in string if ele in punctuation]))

# printing result
print("Sorted Strings list : " + str(res))
```

**输出:**

> 最初的名单是:['gfg@%^'，‘是’、‘最好！’、' fo@#r '、' @#$ge24eks！']
> 排序字符串列表:['是'，'最佳！'，' fo@#r '，'gfg@%^'，' @#$ge24eks！'】