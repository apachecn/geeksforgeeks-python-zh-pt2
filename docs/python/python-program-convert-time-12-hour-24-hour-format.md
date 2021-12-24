# Python 程序将时间从 12 小时转换为 24 小时格式

> 原文:[https://www . geesforgeks . org/python-program-convert-time-12 小时-24 小时-format/](https://www.geeksforgeeks.org/python-program-convert-time-12-hour-24-hour-format/)

给定 12 小时上午/下午格式的时间，将其转换为军用(24 小时)时间。

**注:**12 小时制的午夜为上午 12:00:00，24 小时制的午夜为 00:00:00。中午是 12 小时制的中午 12:00:00，24 小时制的中午 12:00:00。

示例:

```py
Input : 11:21:30 PM
Output : 23:21:30

Input : 12:12:20 AM
Output : 00:12:20

```

**进场:**时间格式是否为 12 小时，可以用列表切片的方式查出来。检查最后两个元素是否是 PM，然后简单地添加 12。如果是 AM，那就不要加了。从更新时间中删除上午/下午。

下面是实现:

```py
# Python program to convert time
# from 12 hour to 24 hour format

# Function to convert the date format
def convert24(str1):

    # Checking if last two elements of time
    # is AM and first two elements are 12
    if str1[-2:] == "AM" and str1[:2] == "12":
        return "00" + str1[2:-2]

    # remove the AM    
    elif str1[-2:] == "AM":
        return str1[:-2]

    # Checking if last two elements of time
    # is PM and first two elements are 12   
    elif str1[-2:] == "PM" and str1[:2] == "12":
        return str1[:-2]

    else:

        # add 12 to hours and remove PM
        return str(int(str1[:2]) + 12) + str1[2:8]

# Driver Code        
print(convert24("08:05:45 PM"))
```

**输出:**

```py
20:05:45
```