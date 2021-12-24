# Python–按大小排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-size/](https://www.geeksforgeeks.org/python-sort-dictionaries-by-size/)

给定字典列表，按字典大小进行排序。

> **输入** : test_list = [{4:6，9:1，10: 2，2:8}，{4:3，9:1}，{3:9}，{1:2，9: 3，7:4}]
> **输出** : [{3: 9}，{4: 3，9: 1}，{1: 2，9:3，7:4}，{4:6，9:1，10:2，2: 8}]
> 【T6
> 
> **输入** : test_list = [{4:3，9:1}，{3:9}，{1:2，9: 3，7:4}]
> **输出** : [{3: 9}，{4:3，9: 1}，{1: 2，9:3，7: 4}]
> **解释** : 1 < 2 < 3，按字典键数排序。

**方法#1:使用 len() + sort()**

在这种情况下，使用 *sort()* 执行排序，并且使用 *len()* 获得字典的大小。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Dictionaries by Size
# Using len() + sort()

# function to get length
def get_len(sub):

    # return length
    return len(sub)

# initializing list
test_list = [{4: 6, 9: 1, 10: 2, 2: 8}, {
    4: 3, 9: 1}, {3: 9}, {1: 2, 9: 3, 7: 4}]

# printing original lists
print("The original list is : " + str(test_list))

# performing inplace sort of list
test_list.sort(key=get_len)

# printing result
print("Sorted List : " + str(test_list))
```

**输出:**

> 原始列表为:[{4: 6，9: 1，10: 2，2: 8}、{4: 3，9: 1}、{3: 9}、{1: 2，9: 3，7: 4}]
> 排序列表:[{3: 9}、{4: 3，9: 1}、{1: 2，9: 3，7: 4}、{4: 6，9: 1，10: 2，2: 8}]

**方法 2:使用排序的()+ len() + lambda**

这里，我们使用 *sorted()* 执行排序任务， *lambda* 函数代替外部函数解决长度获取问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Dictionaries by Size
# Using sorted() + len() + lambda

# initializing list
test_list = [{4: 6, 9: 1, 10: 2, 2: 8}, {
    4: 3, 9: 1}, {3: 9}, {1: 2, 9: 3, 7: 4}]

# printing original lists
print("The original list is : " + str(test_list))

# performing sort using sorted(), lambda for filtering
res = sorted(test_list, key=lambda sub: len(sub))

# printing result
print("Sorted List : " + str(res))
```

**输出:**

> 原始列表为:[{4: 6，9: 1，10: 2，2: 8}、{4: 3，9: 1}、{3: 9}、{1: 2，9: 3，7: 4}]
> 排序列表:[{3: 9}、{4: 3，9: 1}、{1: 2，9: 3，7: 4}、{4: 6，9: 1，10: 2，2: 8}]