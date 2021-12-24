# Python |将字符串转换为 json 对象的方法

> 原文:[https://www . geesforgeks . org/python-将字符串转换为 json-object 的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-string-to-json-object/)

在许多 web API 中，数据通常以一串字典(JSON 对象)的形式发送和获取，以使用这些数据来提取有意义的信息，我们需要将这些数据转换为字典形式，并用于进一步的操作。

让我们看看将字符串转换为 json 的一些方法。

**方法#1:** 使用`json.loads`将对象指定为字符串对象

```py
# Python code to demonstrate
# converting string to json 
# using json.loads
import json

# inititialising json object
ini_string = {'nikhil': 1, 'akash' : 5, 
              'manjeet' : 10, 'akshat' : 15}

# printing initial json
ini_string = json.dumps(ini_string)
print ("initial 1st dictionary", ini_string)
print ("type of ini_object", type(ini_string))

# converting string to json
final_dictionary = json.loads(ini_string)

# printing final result
print ("final dictionary", str(final_dictionary))
print ("type of final_dictionary", type(final_dictionary))
```

**输出:**

```py
initial 1st dictionary {'manjeet': 10, 'nikhil': 1, 'akshat': 15, 'akash': 5}
type of ini_object <type 'str'>
final dictionary {'nikhil': 1, 'manjeet': 10, 'akshat': 15, 'akash': 5}
type of final_dictionary <type 'dict'>

```

**方法 2:** 使用`eval()`将对象串到字典对象

```py
# Python code to demonstrate
# converting string to json 
# using eval

# inititialising json object string
ini_string = """{'nikhil': 1, 'akash' : 5,
            'manjeet' : 10, 'akshat' : 15}"""

# printing initial json
print ("initial 1st dictionary", ini_string)
print ("type of ini_object", type(ini_string))

# converting string to json
final_dictionary = eval(ini_string)

# printing final result
print ("final dictionary", str(final_dictionary))
print ("type of final_dictionary", type(final_dictionary))
```

**输出:**

```py
initial 1st dictionary {'nikhil': 1, 'akash' : 5, 'manjeet' : 10, 'akshat' : 15}
type of ini_object <class 'str'>
final dictionary {'nikhil': 1, 'manjeet': 10, 'akash': 5, 'akshat': 15}
type of final_dictionary <class 'dict'>

```