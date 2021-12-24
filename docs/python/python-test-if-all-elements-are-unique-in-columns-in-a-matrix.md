# Python–测试矩阵中各列的所有元素是否都是唯一的

> 原文:[https://www . geesforgeks . org/python-test-如果所有元素在矩阵中的列中是唯一的/](https://www.geeksforgeeks.org/python-test-if-all-elements-are-unique-in-columns-in-a-matrix/)

给定一个矩阵，测试是否所有列都包含唯一的元素。

> **输入** : test_list = [[3，4，5]，[1，2，4]，[4，1，10]]
> **输出** : True
> **解释** : 3，1，4；4, 2, 1;5, 4, 10;所有元素在列中都是唯一的。
> 
> **输入** : test_list = [[3，4，5]，[3，2，4]，[4，1，10]]
> **输出** : False
> **解释** : 3，3，4；3 重复两次。

**方法#1:使用 loop + set() + len()**

在这种情况下，我们对每一列进行迭代，并使用 set size 使用 len()测试唯一元素，如果发现任何列的大小不等于实际列表的大小，则结果被标记为关闭。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if all elements Unique in Matrix Columns
# Using loop + set() + len()

# initializing list
test_list = [[3, 4, 5], [1, 2, 4], [4, 1, 10]]

# printing original lists
print("The original list is : " + str(test_list))

res = True 
for idx in range(len(test_list[0])):

    # getting column 
    col = [ele[idx] for ele in test_list]

    # checking for all Unique elements
    if len(list(set(col))) != len(col):
        res = False 
        break

# printing result 
print("Are all columns Unique : " + str(res))
```

**输出:**

```
The original list is : [[3, 4, 5], [1, 2, 4], [4, 1, 10]]
Are all columns Unique : True

```

**方法 2:使用 all() +列表理解**

这可以通过使用 all()在一行中解决，该函数使用列表理解检查所有列，如果所有列都返回 true，则 all()返回 True。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if all elements Unique in Matrix Columns
# Using loop + set() + len()

# initializing list
test_list = [[3, 4, 5], [1, 2, 4], [4, 1, 10]]

# printing original lists
print("The original list is : " + str(test_list))

res = True 
for idx in range(len(test_list[0])):

    # getting column 
    col = [ele[idx] for ele in test_list]

    # checking for all Unique elements
    if len(list(set(col))) != len(col):
        res = False 
        break

# printing result 
print("Are all columns Unique : " + str(res))
```

**输出:**

```
The original list is : [[3, 4, 5], [1, 2, 4], [4, 1, 10]]
Are all columns Unique : True

```