# Python 程序根据给定的百分比拆分每个单词

> 原文:[https://www . geesforgeks . org/python-程序-按给定百分比拆分每个单词/](https://www.geeksforgeeks.org/python-program-to-split-each-word-according-to-given-percent/)

给定带有单词的字符串，任务是编写一个 Python 程序，根据给定的值，根据分配的百分比将每个单词分成两半。

**示例:**

> **输入:** test_str = 'geeksforgeeks 最适合所有极客和 cs 学生'，per_splt = 50
> 
> **输出:**极客可能会被拒绝或被拒绝学习
> 
> **说明:**每个字拆分 50%后，输出结果。
> 
> **输入:** test_str = 'geeksforgeeks 最适合所有极客和 cs 学生'，per_splt = 70
> 
> **输出:**极客组织是所有学生的首选
> 
> **说明:**每个字拆分 70%后，输出结果。

**方法 1:使用** [**分割()**](https://www.geeksforgeeks.org/python-string-split/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[切片](https://www.geeksforgeeks.org/python-slice-function/)T18】+[T21【join()](https://www.geeksforgeeks.org/join-function-python/)

在本例中，我们使用 len()和 slicing 拆分每个单词并执行每个单词的百分比拆分。使用循环以中间方式连接结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split each word into percent segment in list
# Using split() + len() + slice + loop

# initializing string
test_str = 'geeksforgeeks is best for all geeks and cs students'

# printing original string
print("The original string is : " + str(test_str))

# initializing percent split 
per_splt = 50

test_str = test_str.split()
res = ''
for ele in test_str:
    prop = int((per_splt/100) * len(ele))
    new_str1 = ele[:prop]
    new_str2 = ele[prop:]
    res += new_str1 + " " + new_str2 + " "

# printing result
print("Segmented words : " + str(res))
```