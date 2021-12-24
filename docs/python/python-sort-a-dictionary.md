# Python |分类词典

> 原文:[https://www.geeksforgeeks.org/python-sort-a-dictionary/](https://www.geeksforgeeks.org/python-sort-a-dictionary/)

Python，给定一个字典，对键或值执行排序。[适用 Python >=3.6v ]。

> **输入**:test _ dict = {“Gfg”:5、“is”:7、“Best”:2 }
> **输出**:{“Best”:2、“Gfg”:5、“is”:7 }、{“is”:7、“Gfg”:5、“Best”:2 }
> **解释**:按键排序，升序和逆序。
> 
> **输入**:test _ dict = {“Best”:2、“for”:9、“极客”:8}
> **输出**:{“Best”:2、“Gfg”:5、“for”:9 }、{“for”:9、“极客”:8、“Best”:2 }
> **解释**:按值排序，升序和逆序。

**情况 1:按键排序**

这个任务是使用 sorted()执行的，在这个任务中，我们使用 items()提取的字典项的第一个索引来提取关键字，并将其作为自定义 lambda 函数传入 key 中以获得关键字排序。添加“反向=真”以执行反向排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort a Dictionary
# Sort by Keys

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 7, "Best" : 2, "for" : 9, "geeks" : 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using items() to get all items 
# lambda function is passed in key to perform sort by key 
res = {key: val for key, val in sorted(test_dict.items(), key = lambda ele: ele[0])}

# printing result 
print("Result dictionary sorted by keys : " + str(res)) 

# using items() to get all items 
# lambda function is passed in key to perform sort by key 
# adding "reversed = True" for reversed order
res = {key: val for key, val in sorted(test_dict.items(), key = lambda ele: ele[0], reverse = True)}

# printing result 
print("Result dictionary sorted by keys ( in reversed order ) : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 7, 'Best': 2, 'for': 9, 'geeks': 8}
Result dictionary sorted by keys : {'Best': 2, 'Gfg': 5, 'for': 9, 'geeks': 8, 'is': 7}
Result dictionary sorted by keys ( in reversed order ) : {'is': 7, 'geeks': 8, 'for': 9, 'Gfg': 5, 'Best': 2}

```

**情况 2:按值排序**

这个任务可以用与上面类似的方式执行，唯一的区别是提取值，items()的第二个元素作为比较器传递。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort a Dictionary
# Sort by Values 

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 7, "Best" : 2, "for" : 9, "geeks" : 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using items() to get all items 
# lambda function is passed in key to perform sort by key 
# passing 2nd element of items()
res = {key: val for key, val in sorted(test_dict.items(), key = lambda ele: ele[1])}

# printing result 
print("Result dictionary sorted by values : " + str(res)) 

# using items() to get all items 
# lambda function is passed in key to perform sort by key 
# passing 2nd element of items()
# adding "reversed = True" for reversed order
res = {key: val for key, val in sorted(test_dict.items(), key = lambda ele: ele[1], reverse = True)}

# printing result 
print("Result dictionary sorted by values ( in reversed order ) : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 7, 'Best': 2, 'for': 9, 'geeks': 8}
Result dictionary sorted by values : {'Best': 2, 'Gfg': 5, 'is': 7, 'geeks': 8, 'for': 9}
Result dictionary sorted by values ( in reversed order ) : {'for': 9, 'geeks': 8, 'is': 7, 'Gfg': 5, 'Best': 2}

```