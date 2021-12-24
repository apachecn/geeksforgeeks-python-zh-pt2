# 提取网格匹配字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-提取-网格-匹配-字符串/](https://www.geeksforgeeks.org/python-program-to-extract-mesh-matching-strings/)

给定一个包含缺失字符的字符网格，匹配匹配该网格的字符串。

**示例:**

> **输入** : test_list = [“极客”、“最佳”、“偷看”]，mesh =“_ ee _ s”
> **输出** : [“极客”、“偷看”]
> **解释**:根据 mesh 的元素是极客和偷看。
> 
> **输入** : test_list = [“极客”、“最佳”、“测试”]，mesh =“_ e _ t”
> **输出**:[‘最佳’、‘测试’]
> **解释**:元素根据网格是最佳和测试。

**方法#1:使用 loop + all() + len() + zip()**

以上的结合可以用来解决这个问题。在本例中，我们执行匹配网格的任务，每个字符串使用 zip()和 all()来检查所有字符串，len()用于测试匹配网格的正确字符串长度。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Mesh matching Strings
# Using len() + loop + zip() + all()

# initializing list
test_list = ["geeks", "best", "peeks", "for", "seeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing mesh 
mesh = "_ee_s"

res = []
for sub in test_list:

    # testing for matching mesh, checking each character and length
    if (len(sub) == len(mesh)) and all((ele1 == "_") or (ele1 == ele2)
       for ele1, ele2 in zip(mesh, sub)):
        res.append(sub)

# printing result 
print("The extracted strings : " + str(res))
```

**Output**

```
The original list : ['geeks', 'best', 'peeks', 'for', 'seeks']
The extracted strings : ['geeks', 'peeks', 'seeks']

```

**方法 2:使用列表理解**

这以与上述方法类似的方式解决了问题，这里唯一的区别是提供了 1 个线性解决方案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Mesh matching Strings
# Using list comprehension

# initializing list
test_list = ["geeks", "best", "peeks", "for", "seeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing mesh 
mesh = "_ee_s"

# one liner to solve this problem
res = [sub for sub in test_list if (len(sub) == len(mesh)) and all((ele1 == "_") or (ele1 == ele2)
      for ele1, ele2 in zip(mesh, sub))]

# printing result 
print("The extracted strings : " + str(res))
```

**Output**

```
The original list : ['geeks', 'best', 'peeks', 'for', 'seeks']
The extracted strings : ['geeks', 'peeks', 'seeks']

```