# 基于前缀列表打印字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-打印-基于字符串的前缀列表/](https://www.geeksforgeeks.org/python-program-to-print-strings-based-on-the-list-of-prefix/)

给定一个字符串列表，这里的任务是编写一个 python 程序，它可以提取前缀与另一个列表中给定的任何一个自定义前缀匹配的所有字符串。

> **输入**:test _ list =[“geeks”“peeks”“meeks”“韭菜”“mean”]，pref _ list =[“ge”“ne”“me”“re”]
> **输出**:[“geeks”“Meeks”“mean”]
> **解释** : geeks、Meeks、mean 分别有前缀，ge、me、me 分别出现在前缀列表中。
> 
> **输入**:test _ list =[“geeks”“peeks”“meeks”“韭菜”“mean”]，pref _ list =[“ge”“le”“me”“re”]
> **输出**:[“geeks”“Meeks”“mean”，韭菜]
> **解释** : geeks、Meeks、韭菜、mean 分别有前缀，ge、me、me、le 分别出现在前缀列表中。

**方法 1 :** 使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)、[任意()](https://www.geeksforgeeks.org/python-any-function/)和[从()](https://www.geeksforgeeks.org/python-startswith-endswidth-function/)开始

在本例中，我们使用 any()和 startswith()执行检查所有元素是否匹配的任务，并提取所有前缀。列表理解用于遍历列表中的所有字符串。

## 蟒蛇 3

```
# initializing List
test_list = ["geeks", "peeks", "meeks", "leeks", "mean"]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix list
pref_list = ["ge", "ne", "me", "re"]

# checking for all possible allowed prefixes using any()
res = [ele for ele in test_list if any(ele.startswith(el) for el in pref_list)]

# printing result
print("The extracted prefix strings list : " + str(res))
```

**输出:**

> 最初的名单是:['极客'，'窥视'，'米克斯'，'韭菜'，'卑鄙']
> 
> 提取的前缀字符串列表:['极客'，'米克斯'，'平均']

**方法 2 :** 使用[过滤器()](https://www.geeksforgeeks.org/filter-in-python/)、[λ](https://www.geeksforgeeks.org/python-lambda/)、[任意()](https://www.geeksforgeeks.org/python-any-function/)和[启动开关()](https://www.geeksforgeeks.org/python-startswith-endswidth-function/)

这类似于上述方法，不同之处在于使用 filter()和 lambda 执行过滤。

## 蟒蛇 3

```
# initializing List
test_list = ["geeks", "peeks", "meeks", "leeks", "mean"]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix list
pref_list = ["ge", "ne", "me", "re"]

# checking for all possible allowed prefixes using any()
# filtering using filter() and lambda
res = list(filter(lambda ele: any(ele.startswith(el)
                                  for el in pref_list), test_list))

# printing result
print("The extracted prefix strings list : " + str(res))
```

**输出:**

> 最初的名单是:['极客'，'窥视'，'米克斯'，'韭菜'，'卑鄙']
> 
> 提取的前缀字符串列表:['极客'，'米克斯'，'平均']