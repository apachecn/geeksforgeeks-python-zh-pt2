# 使用 Python 中的 JSON 数据

> 原文:[https://www . geesforgeks . org/work-with-JSON-data-in-python/](https://www.geeksforgeeks.org/working-with-json-data-in-python/)

**Python 中 JSON 的介绍:**

JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 JSON 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的值。它类似于 Python 中的字典。JSON 显示了一个类似于标准库封送和 pickle 模块用户的应用编程接口，Python 本身支持 JSON 特性。例如

## 蟒 3

T5

```py
# Python program showing
# use of json package

import json

# {key:value mapping}
a ={"name":"John",
   "age":31,
    "Salary":25000}

# conversion to JSON done by dumps() function
 b = json.dumps(a)

# printing the output
print(b)
```