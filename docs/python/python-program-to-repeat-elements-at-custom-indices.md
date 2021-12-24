# Python 程序在自定义索引处重复元素

> 原文:[https://www . geesforgeks . org/python-程序到重复元素-at-custom-indexs/](https://www.geeksforgeeks.org/python-program-to-repeat-elements-at-custom-indices/)

给定一个列表，下面的程序重复那些在自定义索引中的元素，这些自定义索引作为一个单独的列表提供给它。

> **输入** : test_list = [4，6，7，3，1，9，2，19]，idx_list = [3，1，6]
> **输出** : [4，6，6，7，3，3，1，9，2，2，19]
> **解释**:所有需要的索引元素重复，例如 6 和索引 1 一样重复。
> **输入** : test_list = [4，6，7，3，1，9，2，19]，idx_list = [1，6]
> **输出** : [4，6，6，7，3，1，9，2，2，19]
> **说明:**所有需要的索引元素重复，6 个按索引 1 重复。

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*延伸()*](https://www.geeksforgeeks.org/append-extend-python/#:~:text=If%20you%20append%20another%20list,the%20end%20of%20the%20list.&text=extend()%3A%20Iterates%20over%20its,of%20elements%20in%20it's%20argument.)

在这种情况下，我们执行重复每个元素的任务，以防它是需要使用 extend()重复的索引，并且循环用于迭代每个索引。[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)用于获取所有索引和元素。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [4, 6, 7, 3, 1, 9, 2, 19]

# printing original list
print("The original list is : " + str(test_list))

# initializing index list 
idx_list = [3, 1, 4, 6]

res = []
for idx, ele in enumerate(test_list):
    if idx in idx_list:

        # incase of repetition
        res.extend([ele, ele])
    else :
        res.append(ele)

# printing result 
print("The Custom elements repetition : " + str(res))
```

**输出:**

> 原来的名单是:[4，6，7，3，1，9，2，19]
> 
> 自定义元素重复:[4，6，6，7，3，3，1，1，9，2，2，19]