# 在 Python 中序列化和反序列化复杂的 JSON

> 原文:[https://www . geesforgeks . org/serialize-and-serialize-complex-JSON-in-python/](https://www.geeksforgeeks.org/serialize-and-deserialize-complex-json-in-python/)

JSON 代表 JS 对象简谱。它是一种以字符串格式编码数据的格式。JSON 是独立于语言的，因此，它用于存储或传输文件中的数据。从 JSON 对象字符串转换数据被称为序列化，而其相反的字符串 JSON 对象被称为反序列化。JSON 对象是使用花括号{}定义的，由键值对组成。需要注意的是，JSON 对象键是一个字符串，它的值可以是任何原语(例如 int、string、null)或复杂的数据类型(例如 array)。

**JSON 对象示例:**

```
{
 "id":101,
 "company" : "GeeksForGeeks"
}

```

复杂的 JSON 对象是那些包含嵌套对象的对象。复杂 JSON 对象的示例。

```
{
 "id":101,
 "company" : "GeeksForGeeks",
 "Topics" : { "Data Structure",
              "Algorithm",
              "Gate Topics" }
}

```

**序列化&反序列化**

Python 和 JSON 模块与字典配合得非常好。对于 JSON 对象的序列化和反序列化，可以使用 Python“_ _ dict _ _”。任何 Python 对象上都有 __dict__ 属性，这是一个用于存储对象(可写)属性的字典。我们可以用它来和 JSON 一起工作，而且效果很好。
**代号:**

## 蟒蛇 3

```
import json

class GFG_User(object):
    def __init__(self, first_name: str, last_name: str):
        self.first_name = first_name
        self.last_name = last_name

user = GFG_User(first_name="Jake", last_name="Doyle")
json_data = json.dumps(user.__dict__)
print(json_data)
print(GFG_User(**json.loads(json_data)))
```

**输出:**

```
{"first_name": "Jake", "last_name": "Doyle"} 
__main__.GFG_User object at 0x105ca7278

```

**注意:**GFG _ User(** JSON . load(JSON _ data)行中的双星号* *可能看起来很混乱。但它所做的只是扩充字典。

## **复杂物体**

现在，在处理复杂的 JSON 对象时，事情变得棘手了，因为我们的技巧“_dict__”已经不起作用了。
**代号:**

## 蟒蛇 3

```
from typing import List
import json

class Student(object):
    def __init__(self, first_name: str, last_name: str):
        self.first_name = first_name
        self.last_name = last_name

class Team(object):
    def __init__(self, students: List[Student]):
        self.students = students

student1 = Student(first_name="Geeky", last_name="Guy")
student2 = Student(first_name="GFG", last_name="Rocks")
team = Team(students=[student1, student2])
json_data = json.dumps(team.__dict__, indent=4)
print(json_data)
```

**输出:**

```
TypeError: Object of type Student is not JSON serializable

```

但是如果你看一下 dump 函数的文档，你会发现有一个我们可以使用的默认设置。只需替换这一行:

```
json_data = json.dumps(team.__dict__, indent=4)

```

通过这一行:

```
json_data = json.dumps(team.__dict__, lambda o: o.__dict__, indent=4)

```

现在一切都和以前一样。现在，让我们看看反序列化:
**代码:**

## 蟒蛇 3

```
from typing import List
import json

class Student(object):
    def __init__(self, first_name: str, last_name: str):
        self.first_name = first_name
        self.last_name = last_name

class Team(object):
    def __init__(self, students: List[Student]):
        self.students = students

student1 = Student(first_name="Geeky", last_name="Guy")
student2 = Student(first_name="GFG", last_name="Rocks")
team = Team(students=[student1, student2])

# Serialization
json_data = json.dumps(team, default=lambda o: o.__dict__, indent=4)
print(json_data)

# Deserialization
decoded_team = Team(**json.loads(json_data))
print(decoded_team)
```

**输出:**

```
{
    "students": [
        {
            "first_name": "Geeky",
            "last_name": "Guy"
        },
        {
            "first_name": "GFG",
            "last_name": "Rocks"
        }
    ]
}
__main__.Team object at 0x105cd41d0

```