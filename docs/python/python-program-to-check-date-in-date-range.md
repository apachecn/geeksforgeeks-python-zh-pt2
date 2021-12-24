# Python 程序检查日期范围内的日期

> 原文:[https://www . geesforgeks . org/python-程序检查日期范围/](https://www.geeksforgeeks.org/python-program-to-check-date-in-date-range/)

给定日期列表和日期范围，任务是编写一个 Python 程序来检查在给定范围内列表中是否存在任何日期。

**示例:**

> **输入 ：** test_list = [datetime（2019， 12， 30）， datetime（2018， 4， 4）， datetime（2016， 12， 21）， datetime（2021， 2， 2）， datetime（2020， 2， 3）， datetime（2017， 1， 1）]， date_strt， date_end = datetime（2019， 3， 14）， datetime（2020， 1， 4）
> 
> **输出:**真
> 
> **说明:**2019 年 12 月 30 日在 2019 年 3 月 14 日至 2020 年 1 月 4 日之间，因此为真。
> 
> **输入 ：** test_list = [datetime（2018， 4， 4）， datetime（2016， 12， 21）， datetime（2021， 2， 2）， datetime（2020， 2， 3）， datetime（2017， 1， 1）]， date_strt， date_end = datetime（2019， 3， 14）， datetime（2020， 1， 4）
> 
> **输出:**假
> 
> **说明:**没有日期在范围内。

**方法一:使用** [**循环**](https://www.geeksforgeeks.org/understanding-for-loop-in-python/)

在这种情况下，对于每个元素，我们使用条件检查是否有任何日期落在该范围内，如果找到，则返回 true。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test for date in date range
# Using loop
from datetime import datetime

# initializing list
test_list = [datetime(2019, 12, 30), datetime(2018, 4, 4), 
             datetime(2016, 12, 21), datetime(2021, 2, 2), 
             datetime(2020, 2, 3), datetime(2017, 1, 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing date ranges
date_strt, date_end = datetime(2019, 3, 14), datetime(2020, 1, 4)

res = False
for ele in test_list:

    # checking for date in range
    if ele >= date_strt and ele <= date_end:
        res = True

# printing result
print("Does list contain any date in range : " + str(res))
```