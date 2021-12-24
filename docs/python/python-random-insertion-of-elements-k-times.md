# Python–元素随机插入 K 次

> 原文:[https://www . geesforgeks . org/python-元素随机插入-k-times/](https://www.geeksforgeeks.org/python-random-insertion-of-elements-k-times/)

给定 2 个列表，在随机位置插入从列表 2 到列表 1 的随机元素 K 次。

> **输入** : test_list = [5，7，4，2，8，1]，add _ List =[“Gfg”、“Best”、“CS”]，K = 2
> **输出** : [5，7，4，2，8，1，‘Best’，‘Gfg’]
> **解释**:列表 2 中的随机元素被添加 2 次。
> 
> **输入** : test_list = [5，7，4，2，8，1]，add _ List =[“Gfg”、“Best”、“CS”]，K = 1
> **输出** : [5，7，4，2，8，1，‘Gfg’]
> **解释**:列表 2 中的随机元素被添加 1 次。

**方法:使用 randint() +列表切片+循环+ choice()**

在这种情况下，choice()用于从列表 2 中获取要插入到列表 1 中的随机元素，randint()用于获取需要插入的索引。然后使用列表切片按照更新的顺序重新制作列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Random insertion of elements K times
# Using randint() + list slicing + loop + choice()
import random

# initializing list
test_list = [5, 7, 4, 2, 8, 1]

# printing original list
print("The original list : " + str(test_list))

# initializing add list 
add_list = ["Gfg", "Best", "CS"]

# initializing K 
K = 3

for idx in range(K):

    # choosing index to enter element
    index = random.randint(0, len(test_list))

    # reforming list and getting random element to add
    test_list = test_list[:index] + [random.choice(add_list)] + test_list[index:]

# printing result 
print("The created List : " + str(test_list))
```

**Output**

```py
The original list : [5, 7, 4, 2, 8, 1]
The created List : [5, 7, 4, 2, 'Best', 8, 1, 'Best', 'Gfg']

```