# Python 程序查找最常见元素集

> 原文:[https://www . geesforgeks . org/python-程序-查找最常见元素-set/](https://www.geeksforgeeks.org/python-program-to-find-most-common-elements-set/)

给定一个集合列表，任务是编写一个 Python 程序来比较元素和参数集，并返回一个具有最大匹配元素的列表。

**示例:**

> **输入:** test_list = [{4，3，5，2}，{8，4，7，2}，{1，2，3，4}，{9，5，3，7}]，arg_set = {9，6，5，3}
> 
> **输出:** {9，3，5，7}
> 
> **说明:**结果集有最大匹配元素。
> 
> **输入:** test_list = [{4，3，5，2}，{8，4，7，2}，{1，2，3，4}，{9，5，3，7}]，arg_set = {4，6，5，3}
> 
> **输出:** {2，3，4，5}
> 
> **说明:**结果集有最大匹配元素。

**方法 1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**设置.交集()**](https://www.geeksforgeeks.org/intersection-function-python/)

在本例中，我们使用交集()获取所有带有参数集的公共元素，并使用 len()获取其长度，最大长度和集在迭代过程中进行比较和更新。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Most common elements set
# Using loop + intersection()

# initializing list
test_list = [{4, 3, 5, 2}, {8, 4, 7, 2},
             {1, 2, 3, 4}, {9, 5, 3, 7}]

# printing original list
print("The original list is : " + str(test_list))

# initializing arg_set
arg_set = {9, 6, 5, 3}

res = set()
max_len = 0

for sub in test_list:

    # updating max value on occurrence
    if len(sub.intersection(arg_set)) > max_len:
        max_len = len(sub.intersection(arg_set))
        res = sub

# printing result
print("Max Set intersection : " + str(res))
```

**输出:**

```
The original list is : [{2, 3, 4, 5}, {8, 2, 4, 7}, {1, 2, 3, 4}, {9, 3, 5, 7}]
Max Set intersection : {9, 3, 5, 7}
```

**方法二:使用**[**max()**](https://www.geeksforgeeks.org/max-min-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/) **+** [**交集()**](https://www.geeksforgeeks.org/intersection-function-python/)

在这种情况下，初始步骤是检查所有相交集合结果的长度，并使用 max()获得最大值。接下来，提取与所需长度匹配的集合的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Most common elements set
# Using loop + intersection()

# initializing list
test_list = [{4, 3, 5, 2}, {8, 4, 7, 2},
             {1, 2, 3, 4}, {9, 5, 3, 7}]

# printing original list
print("The original list is : " + str(test_list))

# initializing arg_set
arg_set = {9, 6, 5, 3}

# getting maximum length 
max_len = max(len(sub.intersection(arg_set)) for sub in test_list)

# getting element matching length
res = [sub for sub in test_list if len(sub.intersection(arg_set)) == max_len][0]

# printing result
print("Set intersection : " + str(res))
```

**输出:**

```
The original list is : [{2, 3, 4, 5}, {8, 2, 4, 7}, {1, 2, 3, 4}, {9, 3, 5, 7}]
Max Set intersection : {9, 3, 5, 7}
```