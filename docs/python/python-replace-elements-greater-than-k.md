# Python–替换大于 K 的元素

> 原文:[https://www . geesforgeks . org/python-replace-elements-大于-k/](https://www.geeksforgeeks.org/python-replace-elements-greater-than-k/)

给定元素列表，用给定的替换字符替换所有大于 K 的元素。

> **输入** : test_list = [3，4，7，5，6，7]，K = 5，repl_chr = None
> **输出** : [3，4，None，5，None，None]
> **解释**:字符替换为 None，大于 5。
> 
> **输入**:test _ list =【3，4，7，5，6，7】，K = 4，repl_chr = None
> **输出**:【3，4，None，None，None】
> **解释**:字符替换为 None，大于 4。

**方法#1:使用循环**

在这种情况下，我们检查大于 K 的元素，如果找到，它们被替换字符替换，否则旧值被保留。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace Elements greater than K
# Using loop

# initializing list
test_list = [3, 4, 7, 5, 6, 7, 3, 4, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# initializing repl_chr 
repl_chr = "NA"

res = []
for ele in test_list:

    # replace if greater than K
    if ele > K :
        res.append(repl_chr)
    else :
        res.append(ele)

# printing result 
print("The replaced list : " + str(res))
```

**Output**

```py
The original list is : [3, 4, 7, 5, 6, 7, 3, 4, 6, 9]
The replaced list : [3, 4, 'NA', 5, 'NA', 'NA', 3, 4, 'NA', 'NA']

```

**方法 2:使用列表理解**

这是解决这个问题的一个好办法。类似于上面的方法，只使用一个衬垫。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace Elements greater than K
# Using list comprehension

# initializing list
test_list = [3, 4, 7, 5, 6, 7, 3, 4, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# initializing repl_chr 
repl_chr = "NA"

# one liner to solve problem
res = [repl_chr if ele > K else ele for ele in test_list]

# printing result 
print("The replaced list : " + str(res))
```

**Output**

```py
The original list is : [3, 4, 7, 5, 6, 7, 3, 4, 6, 9]
The replaced list : [3, 4, 'NA', 5, 'NA', 'NA', 3, 4, 'NA', 'NA']

```