# Python–具有负值的时间增量对象

> 原文:[https://www . geesforgeks . org/python-time delta-带负值的对象/](https://www.geeksforgeeks.org/python-timedelta-object-with-negative-values/)

在 Python 中，有一个 Datetime 库，它是内置的库，在这个库下存在 **timedelta()** 函数。使用这个函数，我们可以找出未来的日期和时间或者过去的日期和时间。在 timedelta()中，对象 delta 表示两个日期或时间之间的差异。

**语法:**

> datetime.timedelta(天数=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)

所有参数都是可选的，默认情况下为 0。我们可以在参数中传递正值和负值。

让我们看一些例子来更好地理解这个话题。

**示例 1:使用具有负值的时间增量对象查找估计日期。**

## 蟒蛇 3

```py
# importing datetime and timedelta from
# datetime module
from datetime import datetime, timedelta

# function to return date
def get_date(current_date):

    # creating timedelta object with negative
    # values
    date_obj = timedelta(days=-534)

    # getting required date
    req_date = current_date + date_obj

    # splitting date from resultant datetime
    date = req_date.date()

    # returning date
    return date

# main function
if __name__ == '__main__':

    # getting current date and time
    current_datetime = datetime.now()

    # calling function to get the date
    resulted_date = get_date(current_datetime)

    # printing current date
    print('Current date is:', current_datetime.date())

    # printing resultant date after using timedelta
    print('Resultant time after using timedelta object is:',
          resulted_date)
```

**输出:**

```py
Current date is: 2021-03-24
Resultant time after using timedelta object is: 2019-10-07
```

上面的例子显示了当前日期和使用 timedelta 对象后的日期，在上面的例子中，我们在 timedelta 对象中传递了 days=-534 作为参数。负值代表过去，正值代表未来，在上面的代码中，我们已经过去了 534 天，这意味着我们得到的日期是从今天算起的 534 天。

**示例 2:使用具有负值的时间增量对象查找估计时间。**

## 蟒蛇 3

```py
# importing datetime and timedelta from
# datetime module
from datetime import datetime, timedelta

# function to return time
def get_time(current_time):

    # creating timedelta object with negative
    # values
    time_obj = timedelta(hours=-12, minutes=-15)

    # getting required time
    req_time = current_time + time_obj

    # splitting time from resultant datetime
    time = req_time.time()

    # returning time
    return time

# main function
if __name__ == '__main__':

    # getting current date and time
    current_datetime = datetime.now()

    # calling function to get the time
    resulted_time = get_time(current_datetime)

    # printing current time
    print('Current time is:', current_datetime.time())

    # printing resultant time after using timedelta
    print('Resultant time after using timedelta object is:',
          resulted_time)
```

**输出:**

```py
Current time is: 15:53:37.019928
Resultant time after using timedelta object is: 03:38:37.019928
```

上面的例子显示了当前时间和使用 timedelta 对象后的时间，在上面的代码中，我们已经传递了小时=-12 和分钟=-15，这意味着我们得到了结果时间，即从现在开始的 12 小时 15 分钟之前。

**示例 3:使用具有负值的 timedelta 对象查找估计时间的另一种方法。**

## 蟒蛇 3

```py
# importing datetime and timedelta from
# datetime module
from datetime import datetime, timedelta

# function to return time
def get_time(current_time):

    # creating timedelta object with negative
    # values
    time_obj = timedelta(hours=15, minutes=25)

    # getting required time
    req_time = current_time - time_obj

    # splitting time from resultant datetime
    time = req_time.time()

    # returning time
    return time

# main function
if __name__ == '__main__':

    # getting current date and time
    current_datetime = datetime.now()

    # calling function to get the time
    resulted_time = get_time(current_datetime)

    # printing current time
    print(f'Current time is: {current_datetime.time()}')

    # printing resultant time after using timedelta
    print(f'Resultant time after using timedelta object is: {resulted_time}')
```

**输出:**

```py
Current time is: 15:52:59.538796
Resultant time after using timedelta object is: 00:27:59.538796
```

在上面的例子中，我们在 timedelta 对象中传递了正值，但是它们的行为类似于负值，因为在上面的代码中找到第 9 行的 required_time 时，我们在 timedelta 对象中使用了负号，因此传递正值的参数值会自动变为负值，并且我们会得到结果时间，即从现在开始的 15 小时 25 分钟之前。

**例 4:使用带负值的 timedelta 对象查找估计日期和时间。**

## 蟒蛇 3

```py
# importing datetime and timedelta from datetime module
from datetime import datetime,timedelta

# function to return time
def get_datetime(current_datetime):

    # creating timedelta object with negative values
    time_obj = timedelta(weeks=-1, days=-4,
                         hours=-15, minutes=-25,
                         seconds=-54)

    # getting required time and time
    req_time = current_datetime + time_obj

    # returning date and time
    return req_time

# main function
if __name__ == '__main__':

    # getting current date and time
    current_datetime = datetime.now()

    # calling function to get the date and time
    resulted_time = get_datetime(current_datetime)

    # printing current date and time
    print(f'Current time is: {current_datetime}')

    # printing resultant date and time after using timedelta
    print(f'Resultant time after using timedelta object is: {resulted_time}')
```

**输出:**

```py
Current time is: 2021-03-24 15:51:33.024268
Resultant time after using timedelta object is: 2021-03-13 00:25:39.024268
```

上面的例子显示了当前的日期和时间以及使用 timedelta 对象后的结果日期和时间，在上面的代码中我们传递了 weeks=-1 days=-4，hours=-15，minutes=-25，seconds=-54 在 timedelta 对象中意味着我们在使用 timedelta 对象后得到的估计日期和时间是 1 周 4 天 15 小时 25 分 54 秒。