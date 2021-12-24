# Python–解包字符串中的值

> 原文:[https://www . geesforgeks . org/python-解包-字符串中的值/](https://www.geeksforgeeks.org/python-unpacking-values-in-strings/)

给定一个字典，将其值解包成一个字符串。

> **输入** : test_str =“第一个值是{}第二个是{}”，test _ dict = { 3:“Gfg”，9:“Best”}
> **输出**:第一个值是 Gfg 第二个是 Best
> **解释**:换人后，我们得到 Gfg 和 Best 作为值。
> 
> **输入** : test_str = "First 值为{} Second 为{} "，test_dict = {3 : "G "，9 : "f"}
> **输出** : First 值为 G Second 为 f.
> **解释**:代入后，我们得到 G 和 f 作为值。

**方法:使用格式()+ *运算符+值()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用格式来映射字符串中带大括号的所需值。*运算符用于解包和分配。这些值是使用值()提取的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Unpacking Integer Keys in Strings
# Using format() + * operator + values()

# initializing string
test_str = "First value is {} Second is {} Third {}"

# printing original string
print("The original string is : " + str(test_str))

# initializing dictionary 
test_dict = {3 : "Gfg", 4 : "is", 9 : "Best"}

# using format() for mapping required values 
res = test_str.format(*test_dict.values())

# printing result 
print("String after unpacking dictionary : " + str(res)) 
```

**Output**

```py
The original string is : First value is {} Second is {} Third {}
String after unpacking dictionary : First value is Gfg Second is is Third Best

```