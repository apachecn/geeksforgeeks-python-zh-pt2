# 使用 Python 读取、写入和解析 JSON】

> 原文:[https://www . geesforgeks . org/read-write-parse-JSON-using-python/](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)

[JSON](https://www.geeksforgeeks.org/javascript-json/) 是一种轻量级的数据交换数据格式，人类可以轻松读写，机器可以轻松解析生成。这是一种完全独立于语言的文本格式。为了处理 json 数据，Python 有一个名为 JSON 的内置包。

```
Example:
s = '{"id":01, "name": "Emily", "language": ["C++", "Python"]}'
```

JSON 的语法被认为是 JavaScript 语法的子集，包括以下内容:

*   **名称/值对:**代表数据，名称后面跟“:”(冒号)和名称/值对之间用(逗号)分隔。
*   **花括号:**保存对象。
*   **方括号:**保存值由(逗号)分隔的数组。

键/名称必须是带双引号的字符串，值必须是以下数据类型之一:

*   线
*   数字
*   对象(JSON 对象)
*   排列
*   布尔代数学体系的
*   空

```
Example:
 {
   "employee": [

      {
         "id": "01",
         "name": "Amit",
         "department": "Sales"
      },

      {
         "id": "04",
         "name": "sunil",
         "department": "HR"
      }
   ]
}
```

#### 解析 JSON(从 JSON 转换为 Python)

json.loads()方法可以解析一个 json 字符串，结果将是一个 Python 字典。
**语法:**

```
json.loads(json_string)
```

**示例:**

## 蟒蛇 3

```
# Python program to convert JSON to Python

import json

# JSON string
employee ='{"id":"09", "name": "Nitin", "department":"Finance"}'

# Convert string to Python dict
employee_dict = json.loads(employee)
print(employee_dict)

print(employee_dict['name'])
```

**输出:**

```
{'id': '09', 'department': 'Finance', 'name': 'Nitin'}
Nitin
```

#### Python 读取 JSON 文件

方法可以读取包含 json 对象的文件。考虑一个名为 employee.json 的文件，其中包含一个 json 对象。
**语法:**

```
json.load(file_object)
```

**示例:**假设 JSON 是这样的。

![pyhton-append-json1](img/c1f7ebbcf82ae42f4b6124add68e99f2.png)

我们想阅读这个文件的内容。下面是实现。

## 蟒蛇 3

```
# Python program to read
# json file

import json

# Opening JSON file
f = open('data.json',)

# returns JSON object as 
# a dictionary
data = json.load(f)

# Iterating through the json
# list
for i in data['emp_details']:
    print(i)

# Closing file
f.close()
```