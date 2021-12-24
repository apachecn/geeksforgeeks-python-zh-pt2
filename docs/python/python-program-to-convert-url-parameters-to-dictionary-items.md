# Python 程序将 URL 参数转换为字典项

> 原文:[https://www . geesforgeks . org/python-程序-转换-URL-参数-字典-项目/](https://www.geeksforgeeks.org/python-program-to-convert-url-parameters-to-dictionary-items/)

给定网址参数字符串，转换为字典项目。

> **输入**:test _ str = ' gfg = 4&is = 5 '
> **输出** : {'gfg': ['4']，' is': ['5']}
> **解释** : gfg 的值为 4。
> 
> **输入** : test_str = 'gfg=4'
> **输出** : {'gfg': ['4']}
> **说明** : gfg 的值为 4 为参数。

**方法#1:使用 urllib.parse.parse_qs()**

这是执行此任务的默认内置函数，它解析并从“=”的 LHS 形成键，并返回参数的 RHS 值中的值列表。因此，导入外部 urllib.parse()，以使其能够工作。

## 蟒蛇 3

```py
# import module
import urllib.parse

# initializing string
test_str = 'gfg=4&is=5&best=yes'

# printing original string
print("The original string is : " + str(test_str))

# parse_qs gets the Dictionary and value list
res = urllib.parse.parse_qs(test_str)

# printing result
print("The parsed URL Params : " + str(res))
```

**Output**

> 原始字符串为:gfg=4&is=5&best=yes
> 解析后的 URL 参数:{'gfg': ['4']，' is': ['5']，' best': ['yes']}

**方法 2:使用 findall() + setdefault()**

在这里，我们使用 [findall()](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/#:~:text=findall()%20%3A%20Return%20all%20non,(Source%20%3A%20Python%20Docs).) 获取所有参数，然后使用 [setdefault()](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/#:~:text=Dictionary%20in%20Python%20is%20an,the%20key%20is%20in%20dictionary).) 和 loop 分配键和值。

## 蟒蛇 3

```py
import re

# initializing string
test_str = 'gfg=4&is=5&best=yes'

# printing original string
print("The original string is : " + str(test_str))

# getting all params
params = re.findall(r'([^=&]+)=([^=&]+)', test_str)

# assigning keys with values
res = dict()
for key, val in params:

    res.setdefault(key, []).append(val)

# printing result
print("The parsed URL Params : " + str(res))
```

**Output**

> 原始字符串为:gfg=4&is=5&best=yes
> 解析后的 URL 参数:{'gfg': ['4']，' is': ['5']，' best': ['yes']}