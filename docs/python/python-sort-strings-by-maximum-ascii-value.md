# Python–按最大 ASCII 值排序字符串

> 原文:[https://www . geesforgeks . org/python-sort-strings-by-maximum-ascii-value/](https://www.geeksforgeeks.org/python-sort-strings-by-maximum-ascii-value/)

给定字符串列表，按字符串中的最大字符进行排序。

> **输入**:test _ list =[“geeksforgeeks”、“is”、“best”、“cs”]
> **输出**:[“geeksforgeeks”、“is”、“cs”、“best”]
> **解释** : s = s = s < t，按最大字符排序。
> 
> **输入** : test_list =【“苹果”、“是”、“果”】
> **输出**:【“苹果”、“是”、“果”】
> **解释** : p < s < t，遂按 max 排序后保留顺序。性格。

**方法#1:使用 sort() + max()**

在这种情况下，使用 *sort()* 执行排序，使用 *max()* 从字符串中获取最大字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Strings by Maximum Character
# Using sort() + max()

# get maximum character fnc.
def get_max(sub):

    # returns maximum character
    return ord(max(sub))

# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "cs"]

# printing original lists
print("The original list is : " + str(test_list))

# performing sorting
test_list.sort(key=get_max)

# printing result
print("Sorted List : " + str(test_list))
```

**输出:**

> 原列表为:['geeksforgeeks '，' is '，' best '，' for '，' cs']
> 排序列表:['for '，' geeksforgeeks '，' is '，' cs '，' best']

**方法 2:使用排序的()+λ+max()**

在本例中，我们使用 *sorted()* 、 *lambda* 和 *max()* 来执行排序任务，用于输入获取最大字符的逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Strings by Maximum Character
# Using sorted() + lambda + max()

# initializing list
test_list = ["geeksforgeeks", "is", "best", "for", "cs"]

# printing original lists
print("The original list is : " + str(test_list))

# performing sorting using sorted()
# lambda function provides logic
res = sorted(test_list, key=lambda sub: ord(max(sub)))

# printing result
print("Sorted List : " + str(res))
```

**输出:**

> 原列表为:['geeksforgeeks '，' is '，' best '，' for '，' cs']
> 排序列表:['for '，' geeksforgeeks '，' is '，' cs '，' best']