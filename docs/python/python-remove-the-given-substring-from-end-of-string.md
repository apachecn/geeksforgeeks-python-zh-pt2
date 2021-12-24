# Python |从字符串末尾删除给定的子字符串

> 原文:[https://www . geesforgeks . org/python-从字符串末尾移除给定的子字符串/](https://www.geeksforgeeks.org/python-remove-the-given-substring-from-end-of-string/)

有时，我们需要操纵字符串，从字符串中移除额外的信息，以便更好地理解和更快地处理。给定一个任务，其中需要从字符串的末尾移除子字符串。下面给出了一些解决给定任务的方法。

**方法#1:使用朴素方法**

```
# Python3 code to demonstrate
# to remove a substring from end of the string

# Initialising string
ini_string = 'xbzefdgstb'

# initializing string
sstring = 'stb'

# printing initial string and substring
print ("initial_strings : ", ini_string, "\nsubstring : ", sstring)

# removing substring from end
# of string using Naive Method
if ini_string.endswith(sstring):
    res = ini_string[:-(len(sstring))]

# printing result
print ("resultant string", res)
```

**Output:**

```
initial_strings :  xbzefdgstb 
substring :  stb
resultant string xbzefdg

```