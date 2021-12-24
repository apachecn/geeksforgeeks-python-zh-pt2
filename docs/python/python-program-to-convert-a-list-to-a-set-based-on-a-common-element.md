# Python 程序将列表转换为基于公共元素的集合

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-list-a-set-based-on-a-common-element/](https://www.geeksforgeeks.org/python-program-to-convert-a-list-to-a-set-based-on-a-common-element/)

给定一个列表列表，任务是编写一个 python 程序，该程序可以将每个子列表转换成一个集合，如果子列表有一个公共元素，就可以将它们组合成一个集合。打印的输出将是一个集合列表。

> **输入:** test_list = [[15，14，12，18]，[9，5，2，1]，[4，3，2，1]，[19，11，13，12]]
> 
> **输出:** [{11，12，13，14，15，18，19}，{1，2，3，4，5，9}]
> 
> **说明:**列表 1 和列表 4 共有 12 个，因此全部合并为一个。
> 
> **输入** : test_list = [[15，14，12，18]，[9，5，2，1]，[4，3，2，1]，[19，11，13，22]]
> 
> **输出:** [{18，12，14，15}，{1，2，3，4，5，9}，{11，19，13，22}]
> 
> **说明:**列表 2 和列表 3 共有 1、2 个，因此全部合并为一个。

**方法:** *利用* [*递归*](https://www.geeksforgeeks.org/recursion-in-python/) *和* [*联合()*](https://www.geeksforgeeks.org/union-function-python/)

在本例中，我们使用 union()，根据条件执行获取具有相似元素的所有容器的任务。递归用于执行与大多数所需列表相似的任务。

**示例:**

## 蟒蛇 3

```py
# utility function
def common_set(test_set):
    for idx, val in enumerate(test_set):
        for j, k in enumerate(test_set[idx + 1:], idx + 1):

            # getting union by conditions
            if val & k:
                test_set[idx] = val.union(test_set.pop(j))
                return common_set(test_set)
    return test_set

# utility function

# initializing lists
test_list = [[15, 14, 12, 18], [9, 5, 2, 1], [4, 3, 2, 1], [19, 11, 13, 12]]

# printing original list
print("The original list  is : " + str(test_list))

test_set = list(map(set, test_list))

# calling recursive function
res = common_set(test_set)

# printing result
print("Common element groups : " + str(res))
```

**输出:**

> 原来的名单是:[[15，14，12，18]，[9，5，2，1]，[4，3，2，1]，[19，11，13，12]]
> 
> 公共元素组:[{11，12，13，14，15，18，19}，{1，2，3，4，5，9}]