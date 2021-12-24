# Python 程序删除列表中小于 K 差的元素

> 原文:[https://www . geesforgeks . org/python-程序移除列表中小于 k 的元素差异/](https://www.geeksforgeeks.org/python-program-to-remove-elements-that-are-less-than-k-difference-away-in-a-list/)

给定一个列表，执行那些与其前一个元素的差小于 K 的元素的移除。

> **输入**:test _ list =【3，19，5，8，10，13】，K = 4
> **输出**:【3，8，13，19】
> **解释**:5–3 = 2，2 < 4，因此 5 被移除，同样，10–8 是 2，小于 K
> 
> **输入**:test _ list =【15，7，20】，K = 4
> **输出**:【7，15，20】
> **解释**:无需删除。

**进场:** 使用[循环](https://www.geeksforgeeks.org/loops-in-python/)和[排序()](https://www.geeksforgeeks.org/sorted-function-python/)

在这种情况下，首先，必须对列表进行排序，然后删除其前后元素之间没有适当距离的元素。

## 蟒蛇 3

```py
# initializing list
test_list = [3, 19, 4, 8, 10, 13]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# sorting list 
test_list = sorted(test_list)

idx = 0
while idx < len(test_list) - 1:

    # checking for difference
    if test_list[idx] + K > test_list[idx + 1]:

        # deleting if K closer
        del test_list[idx + 1]
    else:
        idx += 1

# printing result 
print("Required List : " + str(test_list))
```

**输出:**

> 原来的名单是:[3，19，4，8，10，13]
> 
> 必需列表:[3，8，13，19]