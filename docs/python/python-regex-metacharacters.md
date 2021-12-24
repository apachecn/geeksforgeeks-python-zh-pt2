# Python 正则表达式元字符

> 原文:[https://www.geeksforgeeks.org/python-regex-metacharacters/](https://www.geeksforgeeks.org/python-regex-metacharacters/)

**元字符**被认为是正则表达式的构建块。正则表达式是用于匹配字符串中字符组合的模式。元字符在寻找模式中有特殊的意义，主要用于定义搜索标准和任何文本操作。

一些最常用的元字符及其用法如下:

<figure class="table">

| **元字符** | **描述** | **例** |
| --- | --- | --- |
| \d | 整数(0-9)(一位数) | \d = 7，\d\d=77 |
| \w | 文字数字式字符 | \w\w\w\w =极客

\w\w\w =！极客 |
| * | 0 个或更多字符 | s。 |
| + | 1 个或更多字符 | s+ = s，ss，sss，sss….. |
| ？ | 0 或 1 个字符 | s？= _ 或 s |
| {m} | 出现“m”次 | sd { 3 } = sddd |
| {m，n} | 最小“m”和最大“n”次 | sd{2，3}=sdd 或 sddd |
| \W | 标志 | \W = % |
| [a-z]或[0-9] | 字符集 | 极客[sy] = 极客奇克[sy]！= geeki |

</figure>

正则表达式可以由元字符构建，模式可以使用 Python 中的库进行处理**正则表达式**被称为**“re”。**

```py
import re  # used to import regular expressions
```

内置库可用于**编译模式、查找模式**、**T3 等。**

**示例:**在下面的代码中，我们将基于给定的正则表达式生成所有模式

## 蟒蛇 3

```py
import re

'''
Meta characters - 
* - 0 or more
+ - 1 or more
? - 0 or 1
{m} - m times
{m,n} - min m and max n
'''

test_phrase = 'sddsd..sssddd...sdddsddd...dsds...dsssss...sdddd'
test_patterns = [r'sd*',        # s followed by zero or more d's
                 r'sd+',          # s followed by one or more d's
                 r'sd?',          # s followed by zero or one d's
                 r'sd{3}',        # s followed by three d's
                 r'sd{2,3}',      # s followed by two to three d's
                 ]

def multi_re_find(test_patterns, test_phrase):
    for pattern in test_patterns:
        compiledPattern = re.compile(pattern)
        print('finding {} in test_phrase'.format(pattern))
        print(re.findall(compiledPattern, test_phrase))

multi_re_find(test_patterns, test_phrase)
```

**输出:**

> 在 test _ 短语
> 中找到 sd *[' SDD '，' SD '，' s '，' s '，' sddd '，' sddd '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' s '，' sdddd']
> 在 test _ 短语
> 中找到 SD+[在测试短语
> ['sd '，' sd '，' s '，' sd '，' sd '，' sd '，' s '，' s '，' s '，' s '，' sd']
> 在测试短语
> 中找到 SD { 3 }[' sddd '，' sddd '，' sddd '，' sddd '，' sddd']
> 在测试短语
> ['sdd '，' sddd '，' sddd '，' sddd']