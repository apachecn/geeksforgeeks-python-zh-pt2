# Python 程序将第一个“K”元素替换为“N”

> 原文:[https://www . geesforgeks . org/python-program-to-replace-first-k-elements-by-n/](https://www.geeksforgeeks.org/python-program-to-replace-first-k-elements-by-n/)

给定一个列表，用 n 替换前 K 个元素

> **输入** : test_list = [3，4，6，8，4，2，6，9]，K = 4，N = 3
> **输出** : [3，3，3，3，4，2，6，9]
> **:前 4 个元素替换为 3。**
> 
> ****输入** : test_list = [3，4，6，8，4，2，6，9]，K = 2，N = 10
> **输出** : [10，10，6，8，4，2，6，9]
> **解释**:前 2 个元素替换为 10。**

****方法 1:使用**T2 循环**

**这个简单的方法遍历列表“ **k** 次，并为遇到的每个元素分配“ **N** ，直到循环结束。**

## **蟒蛇 3**

```
# initializing list
test_list = [3, 4, 6, 8, 4, 2, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# initializing N
N = 6

# assigning value 'N' till K elements
for idx in range(K):

    test_list[idx] = N

# printing result
print("Elements after replacement : " + str(test_list))
```

****Output**

```
The original list is : [3, 4, 6, 8, 4, 2, 6, 9]
Elements after replacement : [6, 6, 6, 6, 6, 2, 6, 9]

```** 

 ****方法二:使用列表切片****

**在这种情况下，我们从列表中切下几个元素，并将“ **N** ”分配给切片列表。**

## **蟒蛇 3**

```
# initializing list
test_list = [3, 4, 6, 8, 4, 2, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# initializing N
N = 6

# assigning the N value till K elements
test_list[: K] = [N] * K

# printing result
print("Elements after replacement : " + str(test_list))
```

****Output**

```
The original list is : [3, 4, 6, 8, 4, 2, 6, 9]
Elements after replacement : [6, 6, 6, 6, 6, 2, 6, 9]

```**