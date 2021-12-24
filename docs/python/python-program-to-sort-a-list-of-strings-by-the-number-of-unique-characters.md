# Python 程序根据唯一字符数对字符串列表进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按唯一字符数对字符串列表进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-strings-by-the-number-of-unique-characters/)

给定一个字符串列表。任务是根据唯一字符的数量对字符串列表进行排序。

**示例:**

> **输入** : test_list = ['gfg '，' best '，' for '，' geek ']，
> **输出** : ['gfg '，' for '，' best '，' geek ']
> **解释** : 2、3、4、4 是列表中唯一的元素。
> 
> **输入** : test_list = ['gfg '，' for '，'极客']，
> **输出** : ['gfg '，' for '，'极客']
> **解释** : 2、3、4 是列表中唯一的元素。

**方法#1:使用 sort()+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**set()**](https://www.geeksforgeeks.org/python-set-method/)

在本文中，我们使用 sort()执行排序任务，并使用 len 和 sort 函数获取字符串中唯一字符的长度。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings by Unique characters
# Using sort() + len() + set()

# helper function
def hlper_fnc(ele):

    # getting Unique elements count 
    return len(list(set(ele)))

# initializing list
test_list = ['gfg', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# perform sort
test_list.sort(key = hlper_fnc)

# printing result 
print("Sorted List : " + str(test_list))
```

**Output**

```
The original list is : ['gfg', 'best', 'for', 'geeks']
Sorted List : ['gfg', 'for', 'best', 'geeks']

```

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**set()**](https://www.geeksforgeeks.org/python-set-method/)**+**[T21】lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

与上述方法类似，区别不在于位置排序，也使用 lambda 函数执行任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Strings by Unique characters
# Using sorted() + len() + set() + lambda

# initializing list
test_list = ['gfg', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# perform sort
res = sorted(test_list, key = lambda sub : len(list(set(sub))))

# printing result 
print("Sorted List : " + str(res))
```

**Output**

```
The original list is : ['gfg', 'best', 'for', 'geeks']
Sorted List : ['gfg', 'for', 'best', 'geeks']

```