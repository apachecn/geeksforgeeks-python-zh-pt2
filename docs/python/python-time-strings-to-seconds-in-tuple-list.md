# Python–元组列表中的时间字符串到秒

> 原文:[https://www . geesforgeks . org/python-时间字符串到秒元组列表/](https://www.geeksforgeeks.org/python-time-strings-to-seconds-in-tuple-list/)

给定分钟字符串，转换为元组列表中的总秒数。

> **输入**:test _ list =[(“5:12”，“9:45”)，(“12:34”，)，(“10:40”，)]
> **输出** : [(312，585)，(754)，(640)，]
> **解释** : 5 * 60 + 12 = 312 为 5:12。
> 
> **输入**:test _ list =[(“5:12”、“9:45”)]
> **输出** : [(312，585)]
> **解释** : 5 * 60 + 12 = 312 为 5:12。

**方法:使用循环+拆分()**

在本文中，我们使用 split()分离分钟和秒钟分量，并执行数学计算以将值转换为所需的秒，使用 int()将字符串转换为整数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Time Strings to Seconds in Tuple List
# Using loop + split()

# initializing list
test_list = [("5:12", "9:45"), ("12:34", "4:50"), ("10:40", )]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:
    tup = tuple()

    # iterating each tuple
    for ele in sub:

        # perform conversion
        min, sec = ele.split(":")
        secs = 60 * int(min) + int(sec)
        tup += (secs, )
    res.append(tup)

# printing result 
print("The corresponding seconds : " + str(res))
```

**Output**

```py
The original list is : [('5:12', '9:45'), ('12:34', '4:50'), ('10:40', )]
The corresponding seconds : [(312, 585), (754, 290), (640, )]

```