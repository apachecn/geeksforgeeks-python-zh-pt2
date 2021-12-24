# Python 程序检查字符串列表中的所有元素是否都是数字

> 原文:[https://www . geesforgeks . org/python-program-to-check-字符串列表中的所有元素是否都是数字/](https://www.geeksforgeeks.org/python-program-to-check-whether-all-elements-in-a-string-list-are-numeric/)

给定一个只包含字符串元素的列表，这里的任务是编写一个 Python 程序来检查它们是否都是数字。如果都是数字，则返回真，否则返回假。

> **输入**:test _ list =[“434”、“823”、“98”、“74”]
> 
> **输出:**真
> 
> **说明:**所有字符串均为数字。
> 
> **输入:**test _ list =[“434”、“82e”、“98”、“74”]
> 
> **输出:**假
> 
> **说明:** e 不是数字，因此判定为假。

**方法 1 :** *使用*[*all()*](https://www.geeksforgeeks.org/any-all-in-python/)*[*is digit()*](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/)T14】和[T17】发电机表达式](https://www.geeksforgeeks.org/generator-expressions/)*

*在本例中，我们从 isdigit()中检查号码。all()用于检查所有要编号的字符串，每个字符串的迭代都是使用生成器表达式完成的。*

***示例:***

## *蟒蛇 3*

```
*# initializing list
test_list = ["434", "823", "98", "74"]

# printing original list
print("The original list is : " + str(test_list))

# checking all elements to be numeric using isdigit()
res = all(ele.isdigit() for ele in test_list)

# printing result
print("Are all strings digits ? : " + str(res))*
```

***输出:***

> *原列表为:['434 '，' 823 '，' 98 '，' 74']*
> 
> *所有字符串都是数字吗？:真*

***方法二:** *使用*[*all()*](https://www.geeksforgeeks.org/any-all-in-python/)*[*is digit()*](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/)*和* [*map()*](https://www.geeksforgeeks.org/python-map-function/)**

**在本文中，我们使用 map()而不是生成器表达式将测试逻辑扩展到每个字符串。其余所有功能的执行与上述方法相似。**

****示例:****

## **蟒蛇 3**

```
**# initializing list
test_list = ["434", "823", "98", "74"]

# printing original list
print("The original list is : " + str(test_list))

# checking all elements to be numeric using isdigit()
# map() to extend to each element
res = all(map(str.isdigit, test_list))

# printing result
print("Are all strings digits ? : " + str(res))**
```

****输出:****

> **原列表为:['434 '，' 823 '，' 98 '，' 74']**
> 
> **所有字符串都是数字吗？:真**