# Python 程序检查字符串中的特定字符

> 原文:[https://www . geesforgeks . org/python-程序检查特定字符的字符串/](https://www.geeksforgeeks.org/python-program-to-check-a-string-for-specific-characters/)

给定一个字符串和字符数组，任务是编写一个 python 程序来检查字符数组中的字符。

**示例:**

```
Input: s = @geeksforgeeks%
       arr[] = {'o','e','%'}
Output: [true,true,true]

Input: s = $geek
       arr[] = {'@','e','a','{content}apos;} 
Output: [false,true,false,true]
```

**方法#1:** 在关键字 +循环中使用

遍历字符数组，对于 arr 中的每个字符，使用返回布尔值(真或假)的 in 运算符检查该字符是否出现在字符串 s 中。

## 蟒蛇 3

```
# Python implementation to check string
# for specific characters

# function to check string
def check(s, arr):
    result = []
    for i in arr:

        # for every character in char array
        # if it is present in string return true else false
        if i in s:
            result.append("True")
        else:
            result.append("False")
    return result

# Driver Code
s = "@geeksforgeeks123"
arr = ['e', 'r', '1', '7']
print(check(s, arr))
```

**Output**

```
['True', 'True', 'True', 'False']
```

**方法#2:** 替代方法

## 蟒蛇 3

```
# Python implementation to check string for
# specific characters

# function to check string
def check(s, arr):

    # returns a list of booleans
    result = [characters in s for characters in arr]
    return result

# Driver Code
s = "@geeksforgeeks123"
arr = ['e', 'r', '1', '@', '0']
print(check(s, arr))
```

**Output**

```
[True, True, True, True, False]
```