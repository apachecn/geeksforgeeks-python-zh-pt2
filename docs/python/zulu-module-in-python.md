# Python 中的祖鲁模块

> 原文:[https://www.geeksforgeeks.org/zulu-module-in-python/](https://www.geeksforgeeks.org/zulu-module-in-python/)

**祖鲁**是原生 DateTime 的嵌入式替代。在这种情况下，所有日期时间对象都转换为世界协调时，并存储为世界协调时。世界协调时和时区之间有一个轮廓。因此，时区表示仅适用于转换为原始日期时间。它支持使用 strptime strftime 指令和 Unicode 日期模式的多种字符串格式。

### 装置

要安装此模块，请在终端中键入以下命令。

```
pip install zulu
```

## 祖鲁模块的类别

*   **zulu.Zulu:** The Zulu class used to represent an immutable UTC DateTime object. Any timezone information which is given to it will be converted from timezone to UTC. If there is no timezone information is given, then it is assumed that the DateTime is a UTC value. All types of arithmetic are performed on the Fundamental UTC DateTime object. In this respect, Zulu has no concept of shifting the timezone. In spite of this, localization occurs only when a Zulu object is formatted as a string.

    ### 函数或类方法

    **1。now()** :-它以祖鲁语对象的形式返回当前 UTC 日期和时间。

    ```
    import zulu

    dt = zulu.now()
    print("Today date and time is:", dt)
    ```

    **输出:**

    > 今天日期时间为:2020-04-17t 16:10:15.708064+00:00

    **2。解析(obj，format=None，default_tz=None) :-** 默认情况下，它会查找 ISO8601 格式的字符串或 POSIX 时间戳。假设世界协调时时区，如果没有给出时区。它从 obj 返回祖鲁对象解析。

    ```
    import zulu

    print("Zulu object when timezone is passed:",
          zulu.parse('2020-04-17T16:10:15.708064+00:00'))

    print("Zulu object when only date is passed:", 
          zulu.parse('2020-04-17'))

    print("Zulu object when date and time is passed:",
          zulu.parse('2020-04-17 16:10'))

    print("Zulu object when ISO8601 is passed as formats:",
          zulu.parse('2020-04-17T16:10:15.708064+00:00',
                     zulu.ISO8601))

    print("Zulu object when Default timezone is used :", 
          zulu.parse('2020-04-17', 
                     default_tz ='US/Eastern'))
    ```

    **输出:**

    > 传递时区时的祖鲁对象:2020-04-17t 16:10:15.708064+00:00
    > 仅传递日期时的祖鲁对象:2020-04-17t 00:00+00:00
    > 传递日期和时间时的祖鲁对象:2020-04-17T16:10:00+00:00
    > 以格式传递 ISO8601 时的祖鲁对象:

    **3。格式(format=None，tz=None，locale='en_US_POSIX') :** 使用字符串格式的格式返回字符串日期时间。当转换到时区 tz 时，可以选择首先。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    print("The Datetime string without timezone is:", 
          dt.format('% m/% d/% y % H:% M:% S % z'))

    print("The Datetime string without timezone is:", 
          dt.format('MM / dd / YY HH:mm:ss Z'))

    print("The Datetime string when timezone is given  is:",
          dt.format('% Y-% m-% d % H:% M:% S % z', 
                    tz ='US/Eastern'))

    print("The Datetime string when timezone is given as local is:", 
          dt.format('%Y-%m-%d %H:%M:%S %z', 
                    tz ='local'))
    ```

    **输出:**

    > 不带时区的 Datetime 字符串为:04/17/20 16:10:15 +0000
    > 不带时区的 Datetime 字符串为:04/17/20 16:10:15 +0000
    > 给定时区时的 Datetime 字符串为:2020-04-17 12:10:15-0400
    > 给定时区时的 Datetime 字符串为:2020-04-17 21:40:15

    **4。范围(帧、开始、结束):**祖鲁实例的范围从开始到结束以给定时间范围的步长返回。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    range1 = list(zulu.range('hour', dt, 
                             dt.shift(hours = 4)))
    range2 = list(zulu.range('minute', dt, 
                             dt.shift(minutes = 4)))

    print("The range when time frame is in hour:", 
          range1)
    print("The range when time frame is in minute:",
          range2)
    ```

    **输出:**

    > 时间范围以小时为单位:【<zulu>、
    > 】T8】祖鲁【2020-04-17T17:10:15.708064+00:00】>、
    > T10】祖鲁【2020-04-17t 18:10:15.708064+00:00】>、
    > <祖鲁【2020-04-17t 17</zulu>

    **5。shift(other=None，years=0，months=0，weeks=0，days=0，hours=0，minutes=0，seconds=0，微秒=0) :** 它可以使用通过传递的参数创建的 timedelta 向前或向后移动日期时间，并返回一个新的 Zulu 实例。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')
    shifted1 = dt.shift(hours =-5, minutes = 10)

    print("The shifted time is:", shifted1)

    shifted2 = dt.shift(minutes = 55, seconds = 11,
                        microseconds = 10)
    print("The new shifted time is:", shifted2)
    ```

    **输出:**

    ```
    The shifted time is: 2020-04-17T11:20:15.708064+00:00
    The new shifted time is: 2020-04-17T17:05:26.708074+00:00

    ```

    **6。add(other=None，years=0，months=0，weeks=0，days=0，hours=0，minutes=0，seconds=0，微秒=0) :** 它使用从传递的参数创建的 timedelta 添加时间，并返回一个新的 Zulu 实例。第一个参数是“timedelta”或 dateutil.relativedelta 对象，在这种情况下，其他参数将被忽略，而在这个 datetime 对象中会添加其他参数。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    shifted = dt.add(minutes = 5)
    print("The new shifted time zone is :", shifted)
    ```

    **输出:**

    > 新转移的时区为:2020-04-17t 16:15:15.708064+00:00

    **7。减法(其他=无，年=0，月=0，周=0，天=0，小时=0，分钟=0，秒=0，微秒=0):** 它使用从传递的参数创建的时间增量减去时间，并返回一个新的祖鲁实例。祖鲁语、datetime、timedelta 或 dateutil.relativedelta 对象可以是第一个参数，在这种情况下，其他参数将被忽略，并且在这个 datetime 对象中将被减去。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')
    shifted1 = dt.subtract(hours = 5)
    shifted2 = dt.subtract(hours = 9).add(minutes = 56)

    print("The new shifted timezone is:", shifted1)
    print("The new shifted timezone using both add\
     and subtract is:", shifted2)
    ```

    **输出:**

    > 新移动的时区为:2020-04-17t 11:10:15.708064+00:00
    > 使用加减的新移动时区为:2020-04-17t 08:06:15.708064+00:00

    **8。替换(年=无，月=无，日=无，小时=无，分钟=无，秒=无，微秒=无，tzinfo =无，*折叠=无):**它替换日期时间属性，并返回一个新的祖鲁实例。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    replaced1 = dt.replace(day = 23, hour = 15)
    print("Replaced time is:", replaced1)

    replaced2 = dt.replace(minute = 10, second = 11,
                           microsecond = 18)
    print("The new replaced time is:", replaced2)
    ```

    **输出:**

    > 更换时间为:2020-04-23t 15:10:15.708064+00:00
    > 新更换时间为:2020-04-17t 16:10:11.000018+00:00

    **9。copy() :** 它返回一个新“祖鲁”实例，但具有相同的日期时间值。
    **返回**
    祖鲁

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')
    print("The copied datetime is:", dt.copy())
    ```

    **输出:**

    > 复制的日期时间为:2020-04-17t 16:10:15.708064+00:00

    既然祖鲁是不可改变的。因此，在更改原始实例的同时，移动、替换和复制返回新的祖鲁实例。

    **10。span(frame，count=1) :** 返回的两个新祖鲁对象与该对象和给定时间范围之间的时间跨度相关。默认情况下，正在跨越的帧数为 1。它返回一个元组(帧开始，帧结束)。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')

    print("The span of a century:", dt.span('century'))
    print("The span of a month:", dt.span('month'))
    print("The span of a day:", dt.span('day'))
    print("The span of a decade:", dt.span('decade'))
    print("The span of a century with given count is:",
           dt.span('century', count = 3))
    ```

    **输出:**

    > 一个世纪的跨度:(<zulu>、 <zulu>)
    > 一个月的跨度:(<祖鲁【2020-04-01t 00:00:00+00:00】>、<祖鲁【2020-04-30t 23:59:59.9999999+00:00】>)
    > 一天的跨度:(<祖鲁【2020-04-04】</zulu></zulu>

    **11 时。span_range(帧、开始、结束):**返回给定时间帧中从给定开始到结束的时间跨度范围。

    ```
    import zulu

    start = zulu.parse('2020-04-17T16:10:15.708064+00:00')
    end = zulu.parse('2020-04-17T22:10:15.708064+00:00')

    for span in zulu.span_range('hour', start, end):
        print(span)
    ```

    **输出:**

    > (<zulu>、 <zulu>)
    > ( <祖鲁【2020-04-17t 17:00:00+00:00】>、<祖鲁【2020-04-17t 17:59:59.9999999+00:00】>)
    > (<祖鲁【2020-04-17T18:00:00+00:00】</zulu></zulu>

    **12 时。开始时间(帧):**对于这个日期时间，它返回给定时间帧 f 的开始时间

    **13。start_of_day() :** 对于这个日期时间，它返回一个新的祖鲁对象/设置为一天的开始。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')
    print("The start of month is:", dt.start_of('month'))
    print("The start of day is:", dt.start_of_day())
    ```

    **输出:**

    ```
    The start of month is: 2020-04-01T00:00:00+00:00
    The start of day is: 2020-04-17T00:00:00+00:00

    ```

    **其他功能开始时间为:**

    | 函数名 | 描述 |
    | --- | --- |
    | 世纪之初() | 将此日期时间的新祖鲁语集返回到世纪初。 |
    | 十年初() | 将此日期时间的新祖鲁语集返回到十年的开始。 |
    | 起始时间() | 将此日期时间的新祖鲁语集返回到小时的开始。 |
    | 分钟开始时间() | 将此日期时间的新祖鲁语集返回到分钟的开头。 |
    | 月初() | 将此日期时间的新祖鲁语集返回到月初。 |
    | 秒的开始时间() | 将此日期时间的新祖鲁语集返回到第二个日期时间的开始。 |
    | 年初() | 将此日期时间的新祖鲁语集返回到年初。 |

    **14。end_of(frame，count=1) :** 对于此日期时间，它返回给定时间帧 f 的结束。默认情况下，正在跨越的帧数为 1。

    **15。end_of_day(count=1) :** 对于这个日期时间，它返回一个新的祖鲁对象/设置为一天的结束。
    默认情况下，正在跨越的帧数为 1。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    print("The end of month is:", dt.end_of('month', 1))
    print("The end of day is without count:", dt.end_of_day())
    print("The end of day is with the count of 2:", dt.end_of_day(2))
    ```

    **输出:**

    > 月末为:2020-04-30t 23:59:59.999999+00:00
    > 日终无计数:2020-04-17t 23:59:59.999999+00:00
    > 日终有计数:2:2020-04-18t 23:59:59.99999+00:00

    **功能的另一端是:**

    | 函数名 | 描述 |
    | --- | --- |
    | 世纪末(计数=1) | 将此日期时间的新祖鲁语集返回到本世纪末。 |
    | 十年末(计数=1) | 将此日期时间的新祖鲁语集返回到十年结束时。 |
    | 小时结束(计数=1) | 将此日期时间的新祖鲁语集返回到小时结束。 |
    | 分钟结束(计数=1) | 将此日期时间的新祖鲁语集返回到分钟的末尾。 |
    | 月末(计数=1) | 将此日期时间的新祖鲁语集返回到月底。 |
    | 秒结束(计数=1) | 将此日期时间的新祖鲁语集返回到第二个日期时间的末尾。 |
    | 年末(计数=1) | 将此日期时间的新祖鲁语集返回到年底。 |

    **16。time_from(dt，* *选项):**它返回这个日期时间和另一个给定日期时间之间的差值，单位为“以前的时间”。
    T3】参数

    *   dtime – A datetime object.

        **返回**T2 字符串

    **17。time _ from _ now(* *选项):**返回这个和现在在“以前的时间”中的差异。

    **18。time_to(dt，* *选项):**返回该日期时间和另一个日期时间在“time to”中的差值。

    **19。time _ to _ now(* *选项):**它以“time to”返回该日期时间和现在之间的差值。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064+00:00')

    print("The difference between this time and end of the day is:",
          dt.time_from(dt.end_of_day()))
    print("The difference between this time and end of the day is:",
          dt.time_to(dt.end_of_day()))
    print("The difference between this time and start of the day is:",
          dt.time_from(dt.start_of_day()))
    print("The difference between this time and start of the day is:",
          dt.time_to(dt.start_of_day()))

    print("The difference is", dt.time_from_now())
    print("The difference is", dt.time_to_now())
    ```

    **输出:**

    > 这个时间和一天结束的差是:8 小时前
    > 这个时间和一天结束的差是:8 小时内
    > 这个时间和一天开始的差是:16 小时内
    > 这个时间和一天开始的差是:16 小时前
    > 这个差是 2 天前
    > 这个差是 2 天

    **20。astimezone(tz='local') :** 它返回移动到给定时区的本机日期时间对象。默认情况下，时区是本地的。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')
    local = dt.astimezone()

    print("Local timezone is", local)

    pacific = dt.astimezone('US / Pacific')
    print("Pacific timezone is:", pacific)
    ```

    **输出:**

    > 当地时区为 2020-04-17 21:40:15.708064+05:30
    > 太平洋时区为:2020-04-17 09:10:15.708064-07:00

    **21。timetuple() :** 返回时间元组。

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')
    print("The timetuple is:", dt.timetuple())
    ```

    **输出**

    > 时间图为:time.struct_time(tm_year=2020，tm_mon=4，tm_mday=17，tm_hour=16，tm_min=10，tm_sec=15，tm_wday=4，tm_yday=108，tm_isdst=-1)

    **22。utcnow() :** 它返回当前的 UTC 日期和时间。

    **23。utcoffset() :** 它返回特定地点与相应世界时的小时、分钟和秒的差值。

    **24。utctimetuple() :** 它返回与 time.localtime()协调的 UTC 时间元组

    ```
    import zulu

    dt = zulu.parse('2020-04-17T16:10:15.708064 + 00:00')

    print("The current UTC datetime is:", dt.utcnow())
    print("The utcoffest is:", dt.utcoffset())
    print("The utctimetuple is:", dt.utctimetuple())
    ```

    **输出:**

    > 当前 UTC 日期时间为:2020-04-19t 07:17:30.162600+00:00
    > UTC off 为:0:00:00
    > UTC time couple 为:time.struct_time(tm_year=2020，tm_mon=4，tm_mday=17，tm_hour=16，tm_min=10，tm_sec=15，tm_wday=4，tm_yday

    **该类其他功能为:**

    | 函数名 | 描述 |
    | --- | --- |
    | ctime() | 返回 ctime()样式字符串。 |
    | 日期() | 返回一个日期对象，但是具有相同的年、月和日，并且顺序相同。 |
    | 日期时间 | 返回本机日期时间对象。 |
    | datetimetuple() | 返回包含年、月、日、小时、分钟、秒、微秒、tzoneinfo 日期时间元组。 |
    | datetuple() | 返回包含年、月、日的日期元组。 |
    | 月中天数() | 返回一个月的总天数 |
    | dst() | 返回夏令时 |
    | is_after(其他) | 返回该日期时间是否在其他日期时间之后 |
    | is_before(其他) | 返回该日期时间是否在其他日期时间之前 |
    | is _ 介于(开始、结束) | 返回该日期时间是否介于开始和结束之间 |
    | is_leap_year() | 返回该日期时间的年份是否为闰年。 |
    | is_on_or_after(其他) | 返回该日期时间是开启还是在其他日期时间之后 |
    | is_on_or_before(其他) | 返回该日期时间是在其他日期时间之前还是之前 |
    | isocialendar _) | 返回包含国际标准化组织年份、周数和工作日三元组 |
    | 异格式() | 返回一个 ISO 8601 格式的字符串，即..YYYY-MM-DDTHH:MM:SS[。mmmmmm][+HH:MM]。 |
    | 等星期日（） | 返回日期代表的星期几，例如星期一== 1，星期二== 2。。。星期日==7 |
    | 天真的 | 返回本机日期时间对象。 |
    | strftime（） | 返回格式–str time()样式字符串。 |
    | strptime（） | 返回字符串，格式–从字符串解析而来的新日期时间。 |
    | 时间() | 返回具有相同时间但时区信息=无的时间对象 |
    | 时间表() | 返回一个时间对象，但时间和时区信息相同。 |
    | 今日() | 返回当前日期或日期时间。 |
    | toordinal() | 返回罗马儒略历/公历序数。 |
    | tzname() | 返回与 datetime 对象关联的时区的名称。 |
    | utcfromtimestamp(时间戳) | 从 POSIX 时间戳返回祖鲁对象。 |
    | 工作日() | 返回日期代表的星期几。周一== 0，周二== 1。。。星期日==6 |
    | 弗洛姆日期时间 | 从本机日期时间对象返回祖鲁对象。 |
    | fromgmtime(结构) | 从一个元组中返回一个祖鲁语对象，该元组类似于 time.gmtime 返回的元组，表示一个 UTC 日期时间。 |
    | fromlocaltime(struct) | 从像 time.localtime 返回的元组中返回一个 Zulu 对象，该元组表示本地日期时间。 |
    | 从序数(序数) | 从罗马儒略历/公历序数返回祖鲁语对象。 |
    | fromtimestamp(时间戳，tz=tzutc()) | 从 POSIX 时间戳返回祖鲁对象。 |

*   **zulu.Delta :-**
    It is an extended version of datetime.timedelta that provides new functionality.

    ### 函数或类方法

    **1。parse_delta(obj) :** 它返回从给定 obj 解析的 delta 对象。

    ```
    import zulu

    delta1 = zulu.parse_delta('4h 45m')
    delta2 = zulu.parse_delta('-4h 45m')

    print("The delta is:", delta1)
    print("The delta is:", delta2)
    ```

    **输出:**

    ```
    The delta is: 4:45:00
    The delta is: -1 day, 19:15:00

    ```

    **2。格式(格式='long '，粒度='second '，阈值=0.85，add_direction=False，locale=None) :** 以格式化字符串形式返回 timedelta。

    ```
    import zulu

    delta = zulu.parse_delta('4h 45m')

    print("The timedelta with given granularity is:", 
          delta.format(granularity ='day'))

    print("The timedelta with given locale is:",
          delta.format(locale ='de'))

    print("The timedelta with given locale and add_direction is:",
          delta.format(locale ='fr', add_direction = True))

    print("The timedelta with given threshold is:", 
          delta.format(threshold = 5))

    print("The timedelta with given threshold and granularity is:", 
          delta.format(threshold = 155, granularity ='minute'))
    ```

    **输出:**

    > 给定粒度的时间增量为:1 天
    > 给定区域的时间增量为:5 秒
    > 给定区域和 add_direction 的时间增量为:5 秒
    > 给定阈值的时间增量为:285 分钟
    > 给定阈值和粒度的时间增量为:285 分钟

    **3。从时间增量(增量):**从本机时间增量对象返回增量对象。

    ```
    import zulu

    delta = zulu.parse_delta('4h 45m')
    delta1 = zulu.parse_delta('6h 42m 11s')

    print("The timedelta is:", delta.fromtimedelta(delta1))
    ```

    **输出:**

    ```
    The timedelta is: 6:42:11

    ```

*   **祖鲁。解析错误:-**
    当一个对象不能被解析为日期时间时，它引发异常。