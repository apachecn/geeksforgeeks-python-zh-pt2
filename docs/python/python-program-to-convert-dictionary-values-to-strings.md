# Python 程序将字典值转换为字符串

> 原文:[https://www . geesforgeks . org/python-程序-转换-字典-值-字符串/](https://www.geeksforgeeks.org/python-program-to-convert-dictionary-values-to-strings/)

给定以混合数据类型作为值的字典，任务是编写一个 Python 程序，通过不同的 delims 转换为解析的字符串。

**示例:**

> **输入:** test_dict = {'Gfg' : 4，' is ':' 1 '，' best' : [8，10]，' geek' : (10，11，2)}，list_delim，tuple_delim = '-'，'^'
> 
> **输出:** {'Gfg': '4 '，' is': '1 '，' best': '8-10 '，' geek ':'10^11^2′}
> 
> **解释:**列表元素通过-连接，元组通过^符号连接。
> 
> **输入:** test_dict = {'Gfg' : 4，' is ':' 1 '，' best' : [8，10]，' geek' : (10，11，2)}，list_delim，tuple_delim = '* '，'
> 
> **输出:** {'Gfg': '4 '，' is': '1 '，' best': '8*10 '，' geek': '10，11，2'}
> 
> **说明:**列表元素通过*连接，元组通过，符号连接。

**示例:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)**+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)

在本例中，我们使用 isinstance()检查所有值数据类型，并使用 join()连接差异传递，转换为解析的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert dictionary values to Strings
# Using loop + isinstance()

# initializing dictionary
test_dict = {'Gfg' : 4,
             'is' : "1",
             'best' : [8, 10],
             'geek' : (10, 11, 2)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing delims
list_delim, tuple_delim = '-', '^'

res = dict()
for sub in test_dict:

    # checking data types
    if isinstance(test_dict[sub], list):
        res[sub] = list_delim.join([str(ele) for ele in test_dict[sub]])
    elif isinstance(test_dict[sub], tuple):
        res[sub] = tuple_delim.join(list([str(ele) for ele in test_dict[sub]]))
    else:
      res[sub] = str(test_dict[sub])

# printing result
print("The converted dictionary : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 4，' is': '1 '，' best': [8，10]，' geek': (10，11，2)}
> 
> 转换后的字典:{'Gfg': '4 '，' is': '1 '，' best': '8-10 '，' geek ':'10^11^2′}