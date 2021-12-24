# Python–根据大小写差异对字符串进行排序

> 原文:[https://www . geeksforgeeks . org/python-按大小写对字符串进行排序-差异/](https://www.geeksforgeeks.org/python-sort-strings-by-case-difference/)

给定字符串列表，任务是编写一个 Python 程序来执行基于大小写差异的排序，即小写和大写的计数。

**示例:**

> **输入**:test _ list =[“GFG”、“极客”、“最佳”、“FOr”、“alL”、“极客”]
> **输出** : [“极客”、“FOr”、“alL”、“GFG”、“最佳”、“极客”]
> **解释**:ees(3)–GK(2)= 1，因此在第 1 个索引处，其他相应排序。
> 
> **输入**:test _ list =[“GFG”、“极客”、“最佳”]
> **输出** : [“极客”、“GFG”、“最佳”]
> **解释**:ees(3)–GK(2)= 1，因此在第 1 个索引处，其他的被相应地排序。

**方法#1:使用 sort()+**[**is lower()**](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)**+**[**is upper()**](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)**+**[**ABS()**](https://www.geeksforgeeks.org/abs-in-python/)

在这种情况下，就地排序使用 sort()执行，islower()和 isupper()用于检查案例和计数。然后 abs()用于获取绝对差值，以提供参数来执行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Strings by Case difference
# Using sort() + islower() + isupper() + abs()

def get_case_diff(string):

    # getting case count and difference
    lower_cnt = len([ele for ele in string if ele.islower()])
    upper_cnt = len([ele for ele in string if ele.isupper()])
    return abs(lower_cnt - upper_cnt)

# initializing Matrix
test_list = ["GFG", "GeeKs", "best", "FOr", "alL", "GEEKS"]

# printing original list
print("The original list is : " + str(test_list))

# inplace sort using sort()
test_list.sort(key=get_case_diff)

# printing result
print("Sorted Strings by case difference : " + str(test_list))
```

**输出:**

> 原列表为:['GFG '，'极客'，'最佳'，' FOr '，' alL '，'极客']
> 按大小写差异排序的字符串:['极客'，' FOr '，' alL '，' GFG '，'最佳'，'极客']

**方法 2:使用排序的()+lambda+islower()+len()+is upper()+ABS()**

与上述方法类似，不同之处在于使用了排序方式，sorted()和 lambda 用作注入功能的方式。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Python3 code to demonstrate working of
# Sort Strings by Case difference
# Using sorted() + lambda + islower() + len() + isupper() + abs()

# initializing Matrix
test_list = ["GFG", "GeeKs", "best", "FOr", "alL", "GEEKS"]

# printing original list
print("The original list is : " + str(test_list))

# sorting using sorted()
# lambda function to inject functionality
res = sorted(test_list, key = lambda string : \
        abs(len([ele for ele in string if ele.islower()]) - \
        len([ele for ele in string if ele.isupper()])))

# printing result
print("Sorted Strings by case difference : " + str(res))
```

**输出:**

> 原列表为:['GFG '，'极客'，'最佳'，' FOr '，' alL '，'极客']
> 按大小写差异排序的字符串:['极客'，' FOr '，' alL '，' GFG '，'最佳'，'极客']