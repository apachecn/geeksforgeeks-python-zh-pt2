# Python 程序查找你出生当天的生日

> 原文:[https://www . geesforgeks . org/python-program-to-find-出生当天的生日/](https://www.geeksforgeeks.org/python-program-to-find-birthdate-on-the-same-day-you-were-born/)

写一个程序，找出你出生当天的出生日期。让输入的格式为:YYYY-MM-DD

**示例:**

> **输入:**1996-11-12
> T3】输出: ['1996-11-12 '，' 2002-11-12 '，' 2013-11-12 '，' 2019-11-12 '，' 2024-11-12 '，' 2030-11-12 '，' 2041-11-12 '，' 2047-11-12']
> 
> **输入:**1992-11-2
> T3】输出: ['1992-11-2 '，' 1998-11-2 '，' 2009-11-2 '，' 2015-11-2 '，' 2020-11-2 '，' 2026-11-2 '，' 2037-11-2 '，' 2043-11-2 '，' 2048-11-2']

## [推荐:请先在 ***<u>{IDE}</u>*** 上尝试您的方法，然后再进入解决方案。](https://ide.geeksforgeeks.org/)

**创建的功能:**

*   **split_date(生日):**该功能将用户给出的日期拆分为年、月、日。
*   **get _ 生日(生日):**此功能用于返回用户出生的星期几。
*   **true _ 生日(生日):**该函数用于返回用户出生当天的日期列表。

要找到与用户出生日期相同的出生日期，以上三种方法将有助于我们。首先，用户输入日期，`split_date()`功能将日期拆分为年、月、日。然后功能`get_birthday()`将用于查找该特定日期的工作日。最后，`true_birthdays()`功能将用于查找所有具有相同工作日的日期列表。在这个函数中，一个 for 循环将从出生年份迭代到特定年份，并将检查任何特定年份的出生日期是否具有相同的工作日。如果工作日相同，则该日期将被添加到日期列表中。

下面是实现。

```
import datetime
import calendar

weekdays = ["Monday", "Tuesday", "Wednesday", 
           "Thursday", "Friday", "Saturday", "Sunday"]

# get_birth day
def split_date(birthday):

    # Split it to year, month and day
    year, month, day = birthday.split('-')    
    return year, month, day

def get_birthday(birthday):

    year, month, day = split_date(birthday)

    # Get a date object for the day of birth
    bdate = datetime.datetime(int(year), int(month), int(day))

    # Get the integer weekday for the day of birth
    weekday = bdate.weekday()

    # Tell the user
    day = weekdays[weekday]

    return day   

def listToString(x):

    # initialize an empty string 
    String = " " 

    # return string   
    return (String.join(x))

def true_birthdays(birthdate):
    year, month, day = split_date(birthdate)

    # get the year from birthday
    year = birthdate[:4].split('-')

    # convert list to string   
    year = listToString(year)

    # get the weekday you are born
    d_day = get_birthday(birthdate) 

    # list of true birthdate[birthday that have same 
    # weekday as the day you were born]    
    true_BD = [] 

    j = 0

    for i in range(int(year), 2050):

        # add + j to birth year 
        new_year = int(year)+j 

        # construct new birthday
        new_birthday = str(str(new_year)+"-"+month+"-"+day) 

        # get weekday of the new birthday
        new_d_day = get_birthday(new_birthday)

        # if birthday that have same weekday 
        # as the day you were born
        if d_day == new_d_day: 

        # add to the list of true birthdate
            true_BD.append(new_birthday)
        else:
            pass
        j += 1

    return true_BD

def main():

    # Get the birth date
    birthdate = "1996-11-12"

    # year_limit = input("search limit from your birthday- ")
    dates = true_birthdays(birthdate)  

    print(dates)

# Driver's code
main()
```

**输出:**

> [‘1996-11-12’, ‘2002-11-12’, ‘2013-11-12’, ‘2019-11-12’, ‘2024-11-12’, ‘2030-11-12’, ‘2041-11-12’, ‘2047-11-12’]