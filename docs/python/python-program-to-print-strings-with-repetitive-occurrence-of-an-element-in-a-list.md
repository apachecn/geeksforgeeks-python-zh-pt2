# Python 程序打印列表中某个元素重复出现的字符串

> 原文:[https://www . geesforgeks . org/python-program-to-print-strings-重复出现列表中的元素/](https://www.geeksforgeeks.org/python-program-to-print-strings-with-repetitive-occurrence-of-an-element-in-a-list/)

给定一个字符串列表，编写一个 Python 程序，提取列表元素中特定值(这里用 K 描述)出现多次的所有字符串。

**示例:**

> **输入**:test _ list =[“geeksforgeeks”“best”“for”“geeks”]，K = 'e'
> **输出**:[‘geeks forgeeks’，‘geeks’]
> **解释** : geeks 和 geeks forgeeks 分别有 2 个和 4 个 K 的出现。
> 
> 。
> **输入** : test_list = [“极客 forgeeks”、“best”、“for”、“极客”]，K = 'k'
> **输出** : ['极客 forgeeks']
> **解释**:极客 forgeeks 有 2 次出现 K

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*计数()*](https://www.geeksforgeeks.org/python-list-function-count/#:~:text=count()%20is%20an%20inbuilt,given%20object%20occurs%20in%20list.&text=Parameters%20%3A,count%20is%20to%20be%20returned.)

在这种情况下，我们使用 count 检查每个字符串中 K 的所有出现，并检查任何字符串是否有超过 1 个出现的 K，如果找到，提取该字符串。

## 蟒蛇 3

```py
# initializing Matrix
test_list = ["geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'e'

res = []
for ele in test_list:

    # checking for count greater than 1 (repetitive)
    if ele.count(K) > 1:
        res.append(ele)

# printing result
print("Repeated K strings : " + str(res))
```

**输出:**

> 最初的名单是:[‘极客’，‘最佳’，‘适合’，‘极客’
> 
> 重复的 K 字符串:['极客 forgeeks '，'极客'

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*计数()*](https://www.geeksforgeeks.org/python-list-function-count/#:~:text=count()%20is%20an%20inbuilt,given%20object%20occurs%20in%20list.&text=Parameters%20%3A,count%20is%20to%20be%20returned.)

这是这个任务的简答题，类似于上面的方法，只是迭代使用是使用列表理解来完成的。

## 蟒蛇 3

```py
# initializing Matrix
test_list = ["geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'e'

# checking for count greater than 1 (repetitive)
# one-liner using list comprehension
res = [ele for ele in test_list if ele.count(K) > 1]

# printing result
print("Repeated K strings : " + str(res))
```

**输出:**

> 最初的名单是:[‘极客’，‘最佳’，‘适合’，‘极客’
> 
> 重复的 K 字符串:['极客 forgeeks '，'极客'