# 用字符串中的$替换所有出现的‘a’的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-replace-all-occurs-with-in-string/](https://www.geeksforgeeks.org/python-program-to-replace-all-occurrences-of-a-with-in-a-string/)

给定一个字符串，任务是编写一个 Python 程序，用$替换所有出现的“a”。

**示例:**

```
Input: Ali has all aces
Output: $li h$s $ll $ces

Input: All Exams are over
Output: $ll Ex$ms $re Over
```

**第一种方法**使用给定的指定字符串拆分成一组字符。空字符串变量用于存储修改后的字符串。我们循环遍历字符数组，检查该索引处的字符是否等同于“a”，然后追加“{content}”签名，以防条件满足。否则，原始字符将被复制到新字符串中。

## 蟒蛇 3

```
# declaring a string variable
str = "Amdani athani kharcha rupaiya."

# declaring an empty string variable for storing modified string
modified_str = ''

# iterating over the string
for char in range(0, len(str)):
    # checking if the character at char index is equivalent to 'a'
    if(str[char] == 'a'):
        # append $ to modified string
        modified_str += '{content}apos;
    else:
        # append original string character
        modified_str += str[char]

print("Modified string : ")
print(modified_str)
```

**输出:**

```
Modified string :
$md$ni $th$ni kh$rch$ rup$iy$.
```

第二种方法**使用内置方法 replace()用新的指定字符替换字符串中特定字符的所有出现。该方法具有以下语法:**

```
replace( oldchar , newchar)
```

**该方法不改变原始字符串，结果必须显式存储在字符串变量中。**

## **蟒蛇 3**

```
# declaring a string variable
str = "An apple A day keeps doctor Away."

# replacing character a with $ sign
str = str.replace('a', '{content}apos;)
print("Modified string : ")
print(str)
```

****输出:****

```
Modified string :
$n $pple $ d$y keeps doctor $w$y.
```