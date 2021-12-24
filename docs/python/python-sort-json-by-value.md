# Python |按值排序 JSON

> 原文:[https://www.geeksforgeeks.org/python-sort-json-by-value/](https://www.geeksforgeeks.org/python-sort-json-by-value/)

让我们看看使用 Python 对 JSON 数据进行排序的不同方法。

**什么是 JSON？**
JSON(JavaScript Object notification)是一种轻量级的、基于文本的、独立于语言的数据交换格式，易于人类和机器读写。JSON 可以表示两种结构化类型:对象和数组。对象是零个或多个名称/值对的无序集合。数组是由零个或多个值组成的有序序列。这些值可以是字符串、数字、布尔值、null 和这两种结构化类型。

任务是先按*编码*，再按*等级*，再按*招生 _ 号*对 JSON 进行排序。

**代码#1:** 按 Desc 顺序排序

```
# Python code to demonstrate sorting in JSON.
import json

data='''{  
   "Student":[  
      {  
         "enrollment_no":"9915103000",
         "name":"JIIT",
         "subject":[  
            {  
               "code":"DBMS",
               "grade":"C"
            }
         ]
      },
      {  
         "enrollment_no":"8815103057",
         "name":"JSS",
         "subject":[  
            {  
               "code":"COA",
               "grade":"A"
            },
            {  
               "code":"CN",
               "grade":"A+"
            }
         ]
      }
   ]
}'''

# Parsing Json object
json_parse = json.loads(data)

# iterating 
for it in json_parse['Student']:
    for y in it['subject']:
        print(y['code'],y['grade'],it['enrollment_no'],it['name'])
```

**输出:**

```
DBMS C 9915103000 JIIT
COA A 8815103057 JSS
CN A+ 8815103057 JSS
```

**代码#2 :** 使用熊猫等外部库(升序排序)。

```
from pandas.io.json import json_normalize

df = json_normalize(json_parse['Student'],
                               'subject', 
                    ['enrollment_no', 'name'])

df.sort_values(['code', 'grade', 'enrollment_no']).reset_index(drop=True)
```

**输出:**

```
  code grade  enrollment_no      name
0  CN     A+  8815103057         JSS
1  COA    A  8815103057         JSS
2  DBMS   C  9915103000        JIIT
```