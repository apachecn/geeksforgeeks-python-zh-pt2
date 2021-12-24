# Python–类似于 K 的其他索引元素

> 原文:[https://www . geesforgeks . org/python-similar-other-index-element-of-k/](https://www.geeksforgeeks.org/python-similar-other-index-element-of-k/)

给定元素列表、其他列表和 K，如果元素在列表中是 K，提取所有相似的其他列表索引元素。

> 输入:test_list = [6，4，6，3，6]，arg_list = [7，5，4，6，3]，K = 6
> 
> 输出:[7，4，3]
> 
> 说明:7、4 和 3 对应于第一个列表中出现的 6。
> 
> 输入:test_list = [2，3]，arg_list = [4，6]，K = 3
> 
> 输出:[6]
> 
> 说明:6 只对应于 3 的出现。

**方法一:使用 enumerate() +列表理解**

上述方法的结合提供了一种解决该任务的方法。在本文中，我们使用 enumerate()从其他列表中检查相似索引，并使用列表理解创建新列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Similar other index element if K
# Using list comprehension + enumerate()

# initializing list
test_list = [5, 7, 3, 2, 3, 8, 6]

# printing original list
print("The original list : " + str(test_list))

# initializing arg. list
arg_list = [4, 5, 8, 3, 7, 9, 3]

# initializing K
K = 3

# Using enumerate() to locate similar index in other list and extract element
res = [ele for idx, ele in enumerate(arg_list) if test_list[idx] == K]

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```
The original list : [5, 7, 3, 2, 3, 8, 6]
Extracted elements : [8, 7]

```

**方法 2:使用列表理解+ zip()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 zip()在两个列表中执行每个元素与其他元素的组合。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Similar other index element if K
# Using list comprehension + zip()

# initializing list
test_list = [5, 7, 3, 2, 3, 8, 6]

# printing original list
print("The original list : " + str(test_list))

# initializing arg. list
arg_list = [4, 5, 8, 3, 7, 9, 3]

# initializing K
K = 3

# Using zip() to lock both the lists, with similar indices mapping
res = [ele for ele, ele1 in zip(arg_list, test_list) if ele1 == K]

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```
The original list : [5, 7, 3, 2, 3, 8, 6]
Extracted elements : [8, 7]

```