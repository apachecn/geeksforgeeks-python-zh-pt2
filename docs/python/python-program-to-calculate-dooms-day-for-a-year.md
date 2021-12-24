# 计算一年末日的程序

> 原文:[https://www . geesforgeks . org/python-计算程序-一年一天的末日/](https://www.geeksforgeeks.org/python-program-to-calculate-dooms-day-for-a-year/)

世界末日可能指的是一个假设的事件，根据这个事件，人类生命的终结是最有可能的。有许多算法被编写来计算一年中一周的哪一天世界末日降临的可能性最高。
所有的说法都是关于公历的。由于公历每 400 年重复一次，所以一套规则只适用于第一个 400 年。算法是由约翰·康威、刘易斯·卡罗尔和历史上许多致力于计算末日的数学家的计算得出的。
**使用以下算法计算特定年份的末日:-**

*   提取年份的最后两位数字。(假设这是 y)
*   除以 12 取值的下限。
*   然后将 y 除以 12 的余数相加。
*   计算 y 除以 12 的余数除以 4 的结果。
*   取上述值的楼层，然后相加。
*   用 7 除后取余数(mod 7)。
*   添加从周日开始的一周中的锚点日的值(将周日视为 0)

**公式变为–**

![([y/12]+ y mod 12 + [y mod 12/4]) mod 7 + anchor      ](img/d70a3cf1313067a7c55b41976b3ab5fa.png "Rendered by QuickLaTeX.com")

这里[ ]是最大整数函数。
锚日在 100 年后发生变化，每 400 年后以下列方式重复–

```
0-99 yrs --> Tuesday
100-199 yrs --> Sunday
200-299 yrs --> Friday
300-399 yr --> Wednesday
```

在此之后，上面的锚日重复文章开头提到的内容。
**例:**

```
Input :  2005
Output : Doomsday in the year 2005 = Monday

Input : 1800
Output : Doomsday in the year 1800 = Friday
```

下面是实现。

## C++14

```
#include<bits/stdc++.h>
using namespace std;

string dooms_day(int year)
{

    // map to store days value of
    // anchor day can be known
    map<int, string> dict_day;
    dict_day[0] = "Sunday";
    dict_day[1] = "Monday";
    dict_day[2] = "Tuesday";
    dict_day[3] = "Wednesday";
    dict_day[4] = "Thursday";
    dict_day[5] = "Friday";
    dict_day[6] = "Saturday";

    // Gregorian calendar repeats
    // every 400 years
    int k = year % 400;

    int anchor;

    // Decide the anchor day
    if(k >= 0 && k < 100)
        anchor = 2;

    else if(k >= 100 && k < 200)
        anchor = 0;

    else if(k >= 200 && k < 300)
        anchor = 5;

    else
        anchor = 3;

    int y = year % 100;

    // Dooms day formula by Conway
    int doomsday = ((y / 12 + y % 12 +
                    (y % 12) / 4) % 7 + anchor) % 7;

    return dict_day[doomsday];
}

// Driver code
int main()
{
    int year = 1966;

    cout << "Doomsday in the year "
         << year << " = " << dooms_day(year);

    return 0;
}

// This code is contributed by yatinagg
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

class GFG{

public static String dooms_day(int year)
{

    // map to store days value of 
    // anchor day can be known 
    HashMap<Integer, String> dict_day = new HashMap<>();
    dict_day.put(0, "Sunday");
    dict_day.put(1, "Monday");
    dict_day.put(2, "Tuesday");
    dict_day.put(3, "Wednesday");
    dict_day.put(4, "Thursday");
    dict_day.put(5, "Friday");
    dict_day.put(6, "Saturday");

    // Gregorian calendar repeats 
    // every 400 years 
    int k = year % 400;

    int anchor;

    // Decide the anchor day 
    if (k >= 0 && k < 100)
        anchor = 2;

    else if (k >= 100 && k < 200)
        anchor = 0;

    else if (k >= 200 && k < 300)
        anchor = 5;

    else
        anchor = 3;

    int y = year % 100;

    // Dooms day formula by Conway 
    int doomsday = ((y / 12 + y % 12 + 
                   (y % 12) / 4) % 7 +
                    anchor) % 7;

    return dict_day.get(doomsday);
}

// Driver code
public static void main(String[] args)
{
    int year = 1966;

    System.out.println("Doomsday in the year " +
                        year + " = " +
                        dooms_day(year));
}
}

// This code is contributed divyeshrabadiya07
```

## 蟒蛇 3

```
def dooms_day(year):

    # dictionary to store days
    # value of anchor day can be known
    dict_day ={ 0 : "Sunday",
               1 : "Monday",
               2 : "Tuesday",
               3 : "Wednesday",
               4 : "Thursday",
               5 : "Friday",
               6 : "Saturday" }

    # gregorian calendar repeats
    # every 400 years
    k = year % 400

    # decide the anchor day
    if(k >= 0 and k < 100):
        anchor = 2

    elif(k >= 100 and k < 200):
        anchor = 0

    elif(k >= 200 and k < 300):
        anchor = 5

    else:
        anchor = 3

    y = year % 100

    # dooms day formula by Conway
    doomsday = ((y//12 + y % 12 + (y % 12)//4)% 7 + anchor) % 7

    return dict_day[doomsday]

# Driver code
year = 1966
print("Doomsday in the year % s = % s"%(year,
                                        dooms_day(year)))
```

## C#

```
using System;
using System.Collections.Generic;  
class GFG
{  
    static String dooms_day(int year)
    {

        // map to store days value of 
        // anchor day can be known 
        Dictionary<int, string> dict_day =  
                       new Dictionary<int, string>(); 
        dict_day.Add(0, "Sunday");
        dict_day.Add(1, "Monday");
        dict_day.Add(2, "Tuesday");
        dict_day.Add(3, "Wednesday");
        dict_day.Add(4, "Thursday");
        dict_day.Add(5, "Friday");
        dict_day.Add(6, "Saturday");

        // Gregorian calendar repeats 
        // every 400 years 
        int k = year % 400;

        int anchor;

        // Decide the anchor day 
        if (k >= 0 && k < 100)
            anchor = 2;

        else if (k >= 100 && k < 200)
            anchor = 0;

        else if (k >= 200 && k < 300)
            anchor = 5;

        else
            anchor = 3;

        int y = year % 100;

        // Dooms day formula by Conway 
        int doomsday = ((y / 12 + y % 12 + 
                       (y % 12) / 4) % 7 +
                        anchor) % 7;

        return dict_day[doomsday];
    }

  // Driver code
  static void Main()
  {
        int year = 1966;

        Console.WriteLine("Doomsday in the year " +
                            year + " = " +
                            dooms_day(year));
  }
}

// This code is contributed by divyesh072019
```

## java 描述语言

```
<script>
      function dooms_day(year) {

        // map to store days value of
        // anchor day can be known
        var dict_day = new Map();
        dict_day.set(0, "Sunday");
        dict_day.set(1, "Monday");
        dict_day.set(2, "Tuesday");
        dict_day.set(3, "Wednesday");
        dict_day.set(4, "Thursday");
        dict_day.set(5, "Friday");
        dict_day.set(6, "Saturday");

        // Gregorian calendar repeats
        // every 400 years
        var k = year % 400;

        var anchor;

        // Decide the anchor day
        if (k >= 0 && k < 100)
            anchor = 2;

        else if (k >= 100 && k < 200)
            anchor = 0;

        else if (k >= 200 && k < 300)
            anchor = 5;

        else
            anchor = 3;

        var y = parseInt(year % 100);

        // Dooms day formula by Conway
        var doomsday = parseInt(parseInt(parseInt(y / 12) + y % 12 + parseInt((y % 12) / 4)) % 7 + anchor) % 7;

        return dict_day.get(doomsday);
    }

    // Driver code
        var year = 1966;
        document.write("Doomsday in the year " + year + " = " + dooms_day(year));

// This code is contributed by gauravrajput1
</script>
```

**Output:** 

```
Doomsday in the year 1966 = Monday
```