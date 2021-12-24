# Python–矩阵中带 K 字符串的行

> 原文:[https://www . geesforgeks . org/python-row-with-k-string-in-matrix/](https://www.geeksforgeeks.org/python-rows-with-k-string-in-matrix/)

给定矩阵，提取出现特定字符串的行号。

> **输入**:test _ list =[[“GFG”、“最佳”、“极客”]、[“极客”、“摇滚”]、[“GFG”、“for”、“CS”]、[“Keep”、“learning”]、K =“GFG”
> **输出**:【0，2】
> **解释**:第 0 个索引和第 2 个索引中有“GFG”作为元素。
> 
> **输入**:test _ list =[[“GFG”、“最佳”、“极客”]、[“极客”、“摇滚”、“GFG”]、[“GFG”、“for”、“CS”]、[“Keep”、“learning”]、K =“GFG”
> **输出**:【0、1、2】
> **说明**:第 0 索引、第 1 索引、第 2 索引中有“GFG”作为元素。

**方法#1:使用循环**

在这种情况下，我们对矩阵中的每个元素进行迭代，得到与 K 字符串匹配的所有行的索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rows with K string in Matrix
# Using loop

# initializing list
test_list = [["GFG", "best", "geeks"], ["geeks", "rock"],
             ["GFG", "for", "CS"], ["Keep", "learning"]]

# printing original list
print("The original list is : ", test_list)

# initializing K
K = "GFG"

res = []

# enumerate() used for getting both index and ele
for idx, ele in enumerate(test_list):

    # checking for K String
    if K in ele:
        res.append(idx)

# printing result
print("Rows with K : " + str(res))
```

**输出:**

> 原列表为:[['GFG '，'最佳'，'极客']，['极客'，'摇滚']，['GFG '，' for '，' CS']，['Keep '，' learning ']
> 行带 K : [0，2]

**方法 2:使用列表理解**

这和上面的方法类似，不同的是它是解决问题的一种简写。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rows with K string in Matrix
# Using list comprehension

# initializing list
test_list = [["GFG", "best", "geeks"], ["geeks", "rock"],
             ["GFG", "for", "CS"], ["Keep", "learning"]]

# printing original list
print("The original list is : ", test_list)

# initializing K
K = "GFG"

# shorthand to get result
res = [idx for idx, ele in enumerate(test_list) if K in ele]

# printing result
print("Rows with K : " + str(res))
```

**输出:**

> 原列表为:[['GFG '，'最佳'，'极客']，['极客'，'摇滚']，['GFG '，' for '，' CS']，['Keep '，' learning ']
> 行带 K : [0，2]