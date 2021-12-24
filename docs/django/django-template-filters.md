# 姜戈模板过滤器

> 原文:[https://www.geeksforgeeks.org/django-template-filters/](https://www.geeksforgeeks.org/django-template-filters/)

Django 模板引擎提供了用于转换变量值的过滤器；es 和标记参数。我们已经讨论了主要的[姜戈模板标签](https://geeksforgeeks.org/django-template-tags/)。标签不能修改变量值，而过滤器可以用来增加变量值或根据自己的需要修改它。

###### 句法

```py
{{ variable_name | filter_name }}
```

过滤器可以是“链式的”一个滤波器的输出应用于下一个滤波器。`{{ text|escape|linebreaks }}`是一个常见的习惯用法，用于转义文本内容，然后将换行符转换为< p >标签。

###### 例子

```py
{{ value | length }}
```

如果值为 **['a '，' b '，' c '，' d']** ，则输出为 **4** 。

## 姜戈的主要模板过滤器

本文围绕项目中可以使用的各种 Django 模板过滤器展开。过滤器转换变量值和标签参数。让我们检查一些主要的过滤器。

| [添加](#add) | [加力](#addslashes) | capfirst |
| [中心](#center) | [切](#cut) | [日期](#date) |
| [默认](#default) | 词典 | [可拆分](#divisibleby) |
| [逃生](#escape) | [排版化](#filesizeformat) | [第一](#first) |
| [加入](#join) | [最后](#last) | [长度](#length) |
| [行号](#linenumbers) | [降低](#lower) | [制作 _ 列表](#make_list) |
| [随机](#random) | [切片](#slice) | [斯鲁吉](#slugify) |
| [时间](#time) | [时间火花](#timesince) | [标题](#title) |
| [无序列表](#unordered_list) | [上部](#upper) | [wordcount](#wordcount) |

1.  #### 增加

    它用于向值添加参数。
    **例**

    ```py
    {{ value | add:"2" }}
    ```

    如果值为 4，则输出将为 6。该过滤器用于**增加 django 模板**中的一个变量。

2.  #### 添加睫毛

    它用于在引号前添加斜线。用于在 CSV 中转义字符串。
    **例**

    ```py
    {{ value | addslashes }}
    ```

    如果值是“我是杰”，输出将是“我是杰”。

3.  #### capfirst

    它用于将值的第一个字符大写。如果第一个字符不是字母，则此过滤器不起作用。
    **例**

    ```py
    {{ value | capfirst }}
    ```

    如果值为“jai”，输出将为“Jai”。

4.  #### 中心

    它用于将给定宽度的字段中的值居中。
    **例**

    ```py
    "{{ value | center:"15" }}"
    ```

    如果值为“Jai”，输出将为“Jai”。

5.  #### 切口

    它用于从给定字符串中移除所有 arg 值。

    **例**

    ```py
    {{ value | cut:" " }}
    ```

    如果值是“带空格的字符串”，输出将是“字符串空格”。

6.  #### 日期

    它用于根据给定的格式格式化日期。
    **例**

    ```py
    {{ value | date:"D d M Y" }}
    ```

    如果值是 datetime 对象(例如 datetime.datetime.now())的结果，则输出将是字符串“2020 年 2 月 6 日星期四”。更多信息和模式[请访问这里](https://docs.djangoproject.com/en/3.0/ref/templates/builtins/#date)。

7.  #### 系统默认值

    它用于给变量赋予默认值。如果变量的计算结果为假，它将使用给定变量值本身的默认参数。

    **例**

    ```py
    {{ value | default:"nothing" }}
    ```

    如果值为“”(空字符串)，则输出将为空。

8.  #### 字典排序

    它获取一个字典列表，并返回按参数中给定的关键字排序的列表。
    **例**

    ```py
    {{ value | dictsort:"name" }}
    ```

    如果值为:

    ```py
    [
        {'name': 'zed', 'age': 19},
        {'name': 'amy', 'age': 22},
        {'name': 'joe', 'age': 31},
    ]
    ```

    那么输出将是:

    ```py
    [
        {'name': 'amy', 'age': 22},
        {'name': 'joe', 'age': 31},
        {'name': 'zed', 'age': 19},
    ] 
    ```

9.  #### 可被...整除

    如果该值可被参数整除，则返回真。
    **例**

    ```py
    {{ value | divisibleby:"3" }}
    ```

    如果值为 21，则输出为真。

10.  #### 逃跑

    它用于转义字符串的 HTML。具体来说，它会进行以下替换:

    ```py
    < is converted to <
    > is converted to >
    ' (single quote) is converted to '
    " (double quote) is converted to "
    & is converted to &
    ```

    **例**

    ```py
    {{ title | escape }}
    ```

11.  #### 文件大小格式

    它用于格式化该值，如“人类可读”文件大小(即“13 KB”、“4.1 MB”、“102 字节”等)。).
    **例**

    ```py
    {{ value | filesizeformat }}
    ```

    如果值为 123456789，输出将为 117.7 MB。

12.  #### 第一

    它用于返回列表中的第一项。
    **例**

    ```py
    {{ value | first }}
    ```

    如果值是列表['a '，' b '，' c']，输出将是' a '。

13.  #### 加入

    它用于用字符串连接列表，就像 Python 的 str.join(list)
    **示例**

    ```py
    {{ value | join:" // " }}
    ```

    如果值是列表['a '，' b '，' c']，输出将是字符串" a//b///c "。

14.  #### 最后的

    它用于返回列表中的最后一项。
    **例**

    ```py
    {{ value | last }}
    ```

    如果值是列表['a '，' b '，' c '，' d']，输出将是字符串" d "。

15.  #### 长度

    它用于返回值的长度。这适用于字符串和列表。
    **例**

    ```py
    {{ value | length }}
    ```

    如果值是['a '，' b '，' c '，' d '或" abcd "，输出将是 4。

16.  #### 行号

    它用于显示带有行号的文本。
    **例**

    ```py
    {{ value | linenumbers }}
    ```

    如果值为:

    ```py
    one
    two
    three
    ```

    输出将是:

    ```py
    1\. one
    2\. two
    3\. three
    ```

17.  #### 降低

    它用于将字符串转换为全部小写。
    **例**

    ```py
    {{ value | lower }}}
    ```

    如果值为**我的名字是 Jai** ，输出将是**我的名字是 jai** 。

18.  #### 制作列表

    它用于返回变成列表的值。对于字符串，它是一个字符列表。对于整数，在创建列表之前，参数被转换为字符串。
    **例**

    ```py
    {{ value | make_list }}
    ```

    如果值是字符串“Naveen”，输出将是列表['N '，' a '，' v '，' e '，' e '，' n']。如果值为 123，输出将是列表['1 '，' 2 '，' 3']。

19.  #### 随意

    它用于从给定列表中返回随机项目。
    **例**

    ```py
    {{ value | random }}
    ```

    如果值是列表['a '，' b '，' c '，' d']，则输出可能是" b "。

20.  #### 薄片

    它用于返回列表的一部分。
    **例**

    ```py
    {{ some_list | slice:":2" }}
    ```

    如果 some_list 为['a '，' b '，' c']，则输出将为['a '，' b']。

21.  #### 斯鲁吉

    它用于转换为 ASCII。它将空格转换为连字符，并删除不是字母数字、下划线或连字符的字符。转换为小写。也去除前导和尾随空白。
    **例**

    ```py
    {{ value | slugify }}
    ```

    如果值为“耆是蛞蝓”，输出将为“耆是蛞蝓”。

22.  #### 时间

    它用于根据给定的格式格式化时间。
    **例**

    ```py
    {{ value | time:"H:i" }}
    ```

    如果值等于 **datetime.datetime.now()** ，输出将是字符串**“01:23”**。

23.  #### 时间自

    它用于将日期格式化为自该日期起的时间(例如，“4 天 6 小时”)。

    **例**

    ```py
    {{ blog_date | timesince:comment_date }}
    ```

    如果 blog_date 是表示 2006 年 6 月 1 日午夜的日期实例，而 comment_date 是表示 2006 年 6 月 1 日 08:00 的日期实例，则下面的内容将返回“8 小时”

24.  #### 标题

    它用于通过使单词以大写字符开头，其余字符为小写字符，将字符串转换为标题大小写。该过滤器不努力将“琐碎的单词”保持为小写。

    **例**

    ```py
    {{ value | title }}
    ```

    如果值是“我的第一篇文章”，输出将是“我的第一篇文章”。

25.  #### 无序列表

    它用于递归地获取一个自嵌套列表，并返回一个 HTML 无序列表–无需打开和关闭

    **例**

    ```py
    {{ var | unordered_list }}
    ```

    如果 var 包含`['States', ['Kansas', ['Lawrence', 'Topeka'], 'Illinois']],`，那么`{{ var|unordered_list }}`将返回:

    ```py
    <li>States
    <ul>
            <li>Kansas
            <ul>
                    <li>Lawrence</li>
                    <li>Topeka</li>
            </ul>
            </li>
            <li>Illinois</li>
    </ul>
    </li>
             </li>
    ```

26.  #### 上面的

    它用于将字符串转换为全大写。
    **例**

    ```py
    {{ value | upper }}
    ```

    如果值为“JAI 是蛞蝓”，输出将为“Jai 是蛞蝓”。

27.  #### word count(word count)

    它用于返回字数。
    **例**

    ```py
    {{ value | wordcount }}
    ```

    如果值为“jai 是蛞蝓”，输出将为 4。