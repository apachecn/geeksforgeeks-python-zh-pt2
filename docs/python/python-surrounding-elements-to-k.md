# Python–围绕元素到 K

> 原文:[https://www . geesforgeks . org/python-环绕元素-to-k/](https://www.geeksforgeeks.org/python-surrounding-elements-to-k/)

给定矩阵，从每一行，得到 K 的周围元素，如果存在的话。

> **输入** : test_list = [[7，6，3，2]，[5，6]，[2，1]，[6，1，2]]，K = 6
> **输出** : [[7，3]，[5]，[]，[1]]
> 解释:所有被 6 包围的元素都被提取出来。
> 
> **输入** : test_list = [[7，6，3，2]，[5，6]，[2，1]，[6，1，2]]，K = 1
> **输出** : [[]，[]，[2]，[6，2]]
> **解释**:1 包围的元素全部移除。

**方法#1:使用** [**指标()**](https://www.geeksforgeeks.org/python-list-index/) **+循环+** [**尝试/除外**](https://www.geeksforgeeks.org/python-try-except/)

在这种情况下，我们使用 index()检查元素的索引，然后通过访问下一个和上一个元素来获取所需的周围元素。如果元素不存在，将返回一个空列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Surrounding elements to K
# Using index() + loop + try/except

# initializing list
test_list = [[7, 6, 3, 2], [5, 6], [2, 1], [6, 1, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 6

res = []
for sub in test_list:

    # getting index 
    try :
        idx = sub.index(K)
    except Exception as e :
        res.append([])
        continue

    # appending Surrounding elements
    if idx != 0 and idx != len(sub) - 1:
        res.append([sub[idx - 1], sub[idx + 1]])
    elif idx == 0:
        res.append([sub[idx + 1]])
    else : res.append([sub[idx - 1]])

# printing result 
print("The Surrounding elements : " + str(res))
```

**输出:**

> 原始列表为:[[7，6，3，2]，[5，6]，[2，1]，[6，1，2]]
> 周围元素:[[7，3]，[5]，[]，[1]]

**方法 2:在运算符+循环中使用 index()+**

在本例中，我们在应用 index()之前检查元素是否存在于行中，以避免使用 try/except 块。其余所有功能与上述方法相同。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Surrounding elements to K
# Using index() + in operator + loop

# initializing list
test_list = [[7, 6, 3, 2], [5, 6], [2, 1], [6, 1, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

res = []
for sub in test_list:

    # getting index
    # checking for element presence in row
    if K in sub:
        idx = sub.index(K)
    else:
        res.append([])
        continue

    # appending Surrounding elements
    if idx != 0 and idx != len(sub) - 1:
        res.append([sub[idx - 1], sub[idx + 1]])
    elif idx == 0:
        res.append([sub[idx + 1]])
    else:
        res.append([sub[idx - 1]])

# printing result
print("The Surrounding elements : " + str(res))
```

**输出:**

> 原始列表为:[[7，6，3，2]，[5，6]，[2，1]，[6，1，2]]
> 周围元素:[[7，3]，[5]，[]，[1]]