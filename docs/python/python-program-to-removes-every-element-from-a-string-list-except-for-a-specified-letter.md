# Python 程序从字符串列表中移除除指定字母以外的所有元素

> 原文:[https://www . geesforgeks . org/python-program-to-remove-从字符串列表中删除除指定字母之外的每个元素/](https://www.geeksforgeeks.org/python-program-to-removes-every-element-from-a-string-list-except-for-a-specified-letter/)

给定一个只包含字符串元素的列表，下面的程序展示了如何从元素中移除除特定元素之外的所有其他字母，然后返回输出。

> **输入**:test _ list =[“Google”，“is”，“good”，“goggled”，“god”]，K = 'g'
> **输出** : ['gg '，“，' g '，' ggg '，' g']
> **解释**:除了“g”以外的所有字符都被删除。
> **输入**:test _ list =[“Google”，“is”，“good”，“goggled”，“god”]，K = 'o'
> **输出** : ['oo '，“，' oo '，' o '，' o']
> **解释**:除了“o”以外的所有字符都被删除。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们通过仅追加 K 来重新构建字符串，并从结果中避免所有其他字符串。

## 蟒蛇 3

```
# initializing list
test_list = ["google", "is", "good", "goggled", "god"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'g'

res = []
for sub in test_list:

    # joining only K characters
    res.append(''.join([ele for ele in sub if ele == K]))

# printing result
print("Modified List : " + str(res))
```

**输出:**

> 最初的名单是:['谷歌'，'是'，'好'，' goggled '，'上帝'
> 
> 修改列表:['gg '，"，' g '，' ggg '，' g']

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*加入()*](https://www.geeksforgeeks.org/join-function-python/#:~:text=The%20join()%20method%20is,of%20iterable%20will%20be%20stored.)

在本文中，我们使用列表理解来执行重新创建列表的任务，然后 join()可以连接 k 的所有出现。

## 蟒蛇 3

```
# initializing list
test_list = ["google", "is", "good", "goggled", "god"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 'g'

# appending and joining using list comprehension and join()
res = [''.join([ele for ele in sub if ele == K]) for sub in test_list]

# printing result
print("Modified List : " + str(res))
```

**输出:**

> 最初的名单是:['谷歌'，'是'，'好'，' goggled '，'上帝'
> 
> 修改列表:['gg '，"，' g '，' ggg '，' g']