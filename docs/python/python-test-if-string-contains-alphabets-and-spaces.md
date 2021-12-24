# Python |测试字符串是否包含字母和空格

> 原文:[https://www . geesforgeks . org/python-test-if-string-contains-alphabets-and-spaces/](https://www.geeksforgeeks.org/python-test-if-string-contains-alphabets-and-spaces/)

有时，当测试字符串作为只包含字母的一部分的可信度时，必须明确提到空格的例外，这就成了一个问题。这可能发生在处理数据的域中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 all()+isspace()+isalpha()**
这是可以执行此任务的方式之一。在这种情况下，我们比较所有元素的字符串，只有字母或空格。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if String contains Alphabets and Spaces
# Using isspace() + isalpha() + all()
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + test_str)

# Test if String contains Alphabets and Spaces
# Using isspace() + isalpha() + all()
res = test_str != '' and all(chr.isalpha() or chr.isspace() for chr in test_str)

# printing result 
print("Does String contain only space and alphabets : " + str(res))
```

**Output : **

```py
The original string is : geeksforgeeks is best for geeks
Does String contain only space and alphabets : True
```

**方法#1:使用正则表达式**
这个问题也可以通过使用正则表达式在字符串中只包含空格和字母来解决。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if String contains Alphabets and Spaces
# Using regex
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + test_str)

# Test if String contains Alphabets and Spaces
# Using regex
res = bool(re.match('[a-zA-Z\s]+{content}apos;, test_str))

# printing result 
print("Does String contain only space and alphabets : " + str(res))
```

**Output : **

```py
The original string is : geeksforgeeks is best for geeks
Does String contain only space and alphabets : True
```