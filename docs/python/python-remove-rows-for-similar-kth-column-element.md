# Python–删除类似第 Kth 列元素的行

> 原文:[https://www . geesforgeks . org/python-remove-rows-for-simple-kth-column-element/](https://www.geeksforgeeks.org/python-remove-rows-for-similar-kth-column-element/)

给定一个矩阵，如果类似的元素出现在第 k 列的上一行，则删除该行。

> **输入** : test_list = [[3，4，5]，[2，3，5]，[10，4，3]，[7，8，9]，[9，3，6]]，K = 2
> **输出** : [[3，4，5]，[10，4，3]，[7，8，9]，[9，3，6]]
> **解释**:在【2，3，5】中，我们已经有了 list [3，4]
> **输入** : test_list = [[3，4，5]，[2，3，3]，[10，4，3]，[7，8，9]，[9，3，6]]，K = 2
> **输出**:In【10，4】

**方法:使用循环**

在这种情况下，我们维护一个 memoization 容器，该容器跟踪第 Kt 列中的元素，如果行的第 Kt 列元素已经存在，则从结果中省略该行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Rows for similar Kth column element
# Using loop

# initializing list
test_list = [[3, 4, 5], [2, 3, 5], [10, 4, 3], [7, 8, 9], [9, 3, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

res = []
memo = []
for sub in test_list:

    # in operator used to check if present or not
    if not sub[K] in memo:
        res.append(sub)
        memo.append(sub[K])

# printing result
print("The filtered Matrix : " + str(res))
```

**Output**

```py
The original list is : [[3, 4, 5], [2, 3, 5], [10, 4, 3], [7, 8, 9], [9, 3, 6]]
The filtered Matrix : [[3, 4, 5], [2, 3, 5], [7, 8, 9]]
```