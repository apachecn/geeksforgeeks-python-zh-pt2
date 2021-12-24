# Python 程序查找列表中给定条件的所有组合

> 原文:[https://www . geesforgeks . org/python-program-to-find-all-in-list-the-combinations-in-the-给定条件/](https://www.geeksforgeeks.org/python-program-to-find-all-the-combinations-in-the-list-with-the-given-condition/)

给定一个列表，其中一些元素是可选元素的列表。任务是从所有选项中找到所有可能的组合。

**示例:**

> **输入**:test _ list =[“geekforgeks”、[5，4，3]、“is”、[“best”、“good”、“better”]、K = 3
> **输出**:[‘geekforgeks’，5，‘is’，‘best’]、[‘geekforgeks’，4，‘is’，‘good’]、[‘geekforgekeks’，3，‘is’，‘better’]
> **解释**:内部元素拾取并与相似索引配对。5 - >“最佳”。
> 
> **输入**:test _ list =[“geek forgek”、[5，4]、“is”、[“best”、“good”]]、K = 2
> **输出**:【【‘geek forgek’、5、‘is’、‘best’】、【‘geek forgek’、4、‘is’、‘good’】】
> **解释**:内部元素拾取并与相似索引配对。5 - >“最好”。

**方法:使用循环**

在这种情况下，我们使用嵌套循环从每个嵌套选项列表中获取按索引排列的组合，然后使用外部循环获取所有组合中的默认值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Optional Elements Combinations
# Using loop

# initializing list
test_list = ["geekforgeeks", [5, 4, 3, 4], "is", 
             ["best", "good", "better", "average"]]

# printing original list
print("The original list is : " + str(test_list))

# initializing size of inner Optional list 
K = 4

res = []
cnt = 0
while cnt <= K - 1:
    temp = []

    # inner elements selections
    for idx in test_list:

        # checks for type of Elements
        if not isinstance(idx, list):
            temp.append(idx)
        else:
            temp.append(idx[cnt])
    cnt += 1
    res.append(temp)

# printing result 
print("All index Combinations : " + str(res))
```

**输出:**

> 原始列表为:['geekforgeeks '，[5，4，3，4]，' is '，['best '，' good '，' better '，' average']]
> 
> 所有索引组合:[[' geek forgeks '，5，' is '，' best']，[' geek forgeks '，4，' is '，' good']，[' geek forgeks '，3，' is '，' better']，[' geek forgeks '，4，' is '，' average']]