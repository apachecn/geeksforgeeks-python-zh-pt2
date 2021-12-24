# Python |时区转换

> 原文:[https://www.geeksforgeeks.org/python-timezone-conversion/](https://www.geeksforgeeks.org/python-timezone-conversion/)

大多数从`dateutil parser`返回的日期时间项目都是幼稚的，这意味着它们没有明确的 **tzinfo** 。tzinfo 确定时区和世界协调时时差。它是世界协调时日期时间字符串的标准国际标准化组织格式。世界协调时是**协调世界时**，基本上等同于格林尼治时间。ISO 是**国际标准组织**，除了其他的东西，它还决定了标准的日期时间设计。

Python 日期时间项目可能是幼稚的，也可能是谨慎的。如果日期时间项有 tzinfo，那么它知道。另外，日期时间很幼稚。要使天真的 datetime 对象了解时区，请定义 tzinfo 抽象基类。无论如何，Python datetime 库只是表征了 tzinfo 的一个概念基类，并将其留给其他人来真正实现 tzinfo 的创建。这就是 dateutil 的 tz 模块的用武之地——它给出了从操作系统时区信息向上转换时区所需的所有信息。

**安装:**

> 使用 pip 或 easy_install dateutil 进行安装。确保操作系统有时区数据。
> 
> 在 Linux 上，这通常可以在 `/usr/share/zoneinfo`中找到，Ubuntu 包叫做 tzdata。如果 `/usr/share/zoneinfo`中的文件和目录数量，如美洲/和欧洲/，那么就可以继续了。

**获取世界协调时 tzinfo 对象–通过调用`tz.tzutc()`**

```
from dateutil import tz
tz.tzutc()
```

```
tzutc()
```

**通过用世界协调时日期时间对象调用`utcoffset()`方法，偏移量为 0。**

```
import datetime
tz.tzutc().utcoffset(datetime.datetime.utcnow())
```

```
datetime.timedelta(0)
```

将时区文件路径传递给`gettz()`函数，以获取其他时区的 tzinfo 对象。

```
tz.gettz('US/Pacific')
```

```
tzfile('/usr/share/zoneinfo/US/Pacific')
```

```
tz.gettz('Europe / Paris')
```

```
tzfile('/usr/share/zoneinfo/Europe/Paris')
```

```
tz.gettz('US / Pacific').utcoffset(datetime.datetime.utcnow())
```

```
datetime.timedelta(-1, 61200)
```

要将非世界协调时日期时间项目更改为世界协调时，必须注意时区。如果您试图将轻信的日期时间转换为世界协调时，您将获得值错误豁免。为了让天真的日期时间时区记住，你基本上用正确的 tzinfo 调用`replace()`策略。一旦日期时间项有了时间信息，就可以通过使用`tz.tzutc()`调用`astimezone()`技术来执行世界协调时的更改。

```
abc = tz.gettz('US/Pacific')
dat = datetime.datetime(2010, 9, 25, 10, 36)
dat.tzinfo
dat.astimezone(tz.tzutc())
```

```
Traceback (most recent call last):
 File "/usr/lib/python2.6/doctest.py", line 1228, in __run
 compileflags, 1) in test.globs
 File "", line 1, in 
 dat.astimezone(tz.tzutc())
ValueError: astimezone() cannot be applied to a naive datetime
```

```
dat.replace(tzinfo = abc)
```

```
datetime.datetime(2010, 9, 25, 10, 36, tzinfo=tzfile(
'/usr/share/zoneinfo/US/Pacific'))
```

**所有人都在工作–**

*   tzutc 和 tzfile 项是 tzinfo 的两个子类。
*   综合考虑，他们知道时区变化的正确 UTC 偏移量(对于 tzutc 为 0)。
*   tzfile 项实现了如何仔细阅读工作框架的 zoneinfo 文档以获得基本的平衡信息。
*   日期时间项的 replace()策略顾名思义，就是替换质量。
*   一旦日期时间有了 tzinfo，astimezone()策略很可能会利用 UTC 平衡来相信时间，然后用新的 tzinfo 取代当前的 tzinfo

**代码:**将 tzinfos 关键字参数传递到 dateutil 解析器中，以检测无法识别的时区

```
parser.parse('Wednesday, Aug 4, 2010 at 6:30 p.m. (CDT)',
             fuzzy = True)
```

```
datetime.datetime(2010, 8, 4, 18, 30)
```

```
tzinfos = {'CDT': tz.gettz('US/Central')}
parser.parse('Wednesday, Aug 4, 2010 at 6:30 p.m. (CDT)',
fuzzy = True, tzinfos = tzinfos)
```

```
datetime.datetime(2010, 8, 4, 18, 30, tzinfo=tzfile('
/usr/share/zoneinfo/US/Central'))
```