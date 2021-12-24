# Python 程序获取给定键的最大值索引给定的字典的值

> 原文:[https://www . geesforgeks . org/python-program-to-get-value-of-a-dictionary-by-index-of-value-of-given-key/](https://www.geeksforgeeks.org/python-program-to-get-value-of-a-dictionary-given-by-index-of-maximum-value-of-given-key/)

给定一个以值为列表的字典，任务是编写一个 Python 程序，该程序可以找到任何一个键的最大值，并输出其他键的值的类似索引列。

**进场:**

*   获取给定密钥的最大值。
*   获取找到的最大元素的索引。
*   检查搜索关键字中是否存在最大索引，如果不存在，则返回结果不可能。
*   获取搜索关键字(opt_key)上的元素，它位于步骤 2 中找到的索引处。

> **输入:** test_dict = {"gfg" : [4，1，6]，" is" : [1，4，8]，" best" : [9，10，1]}，max_search = "best "，opt_key = "gfg "
> 
> **输出:** 1
> 
> **说明:** 10 是最佳键中的最大元素，对应第 1 个索引。在 gfg 中，第一个索引是 1，因此是 1。
> 
> **输入:** test_dict = {"gfg" : [4，10，6]，" is" : [1，4，8]，" best" : [9，10，1]}，max_search = "best "，opt_key = "gfg "
> 
> **输出:** 10
> 
> **说明:** 10 是最佳键中的最大元素，对应第 1 个索引。在 gfg 中，第一个指数是 10，因此是 10。

**方法 1 :** *使用* [*指数()*](https://www.geeksforgeeks.org/python-list-index/#:~:text=index()%20is%20an%20inbuilt,index%20where%20the%20element%20appears.&text=Parameters%20%3A,from%20where%20the%20search%20begins.)*[*max(*](https://www.geeksforgeeks.org/max-min-python/)*)和*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*

*在本文中，我们使用 max()找到 max 搜索关键字的最大值，并使用 index()获取其索引，然后获取输出关键字中的 index 值。*

***示例:***

## *蟒蛇 3*

```py
*# initializing dictionary
test_dict = {"gfg": [4], "is": [1, 4, 8], "best": [9, 10]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing max_search key
max_search = "best"

# initializing output key
opt_key = "gfg"

# handling case in which maximum index is not 
# present in output key
if len(test_dict[opt_key]) <= test_dict[max_search].index(
  max(test_dict[max_search])):
    res = "Result not possible"

# using max() to get of search key
else:
    res = max(test_dict[opt_key], key=lambda sub: test_dict[max_search]
              [test_dict[opt_key].index(sub)])

# printing result
print("The required output : " + str(res))*
```

***输出:***

> *原始字典为:{'gfg': [4]，' is': [1，4，8]，' best': [9，10]}*
> 
> *要求的输出:结果不可能*

***方法二:** *使用* [*zip()*](https://www.geeksforgeeks.org/zip-in-python/) *和* [*max()*](https://www.geeksforgeeks.org/max-min-python/)*

*在这种情况下，搜索关键字和输出关键字的列表使用 zip()组合在一起，这样最多可以找到一个列表，并返回相应的输出关键字索引。*

***示例:***

## *蟒蛇 3*

```py
*# initializing dictionary
test_dict = {"gfg": [4, 1, 6], "is": [1, 4, 8], "best": [9, 10, 1]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing max_search key
max_search = "best"

# initializing output key
opt_key = "gfg"

# handling case in which maximum index is not present 
# in output key
if len(test_dict[opt_key]) <= test_dict[max_search].index(
  max(test_dict[max_search])):
    res = "Result not possible"

# using max() to get of search key
# zip() used for combining lists
else:
    res = max(zip(test_dict[opt_key], test_dict[max_search]),
              key=lambda sub: sub[1])[0]

# printing result
print("The required output : " + str(res))*
```

***输出:***

> *原始字典为:{'gfg': [4，1，6]，' is': [1，4，8]，' best': [9，10，1]}*
> 
> *所需的输出:1*