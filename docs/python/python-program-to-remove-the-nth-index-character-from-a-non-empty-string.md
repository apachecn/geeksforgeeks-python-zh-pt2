# Python 程序从非空字符串中删除第 n 个索引字符

> 原文:[https://www . geeksforgeeks . org/python-从非空字符串中删除第 n 个索引字符的程序/](https://www.geeksforgeeks.org/python-program-to-remove-the-nth-index-character-from-a-non-empty-string/)

给定一个字符串，任务是编写一个 Python 程序，从非空字符串中删除第 n 个索引字符

**示例:**

```py
Input: str = "Stable"
Output: Modified string after removing  4 th character 
Stabe.

Input: str = "Arrow"
Output: Modified string after removing  4 th character 
Arro
```

第一种方法**使用一个新的字符串变量来存储修改后的字符串。我们跟踪字符串的字符，一旦在第 n 个索引处遇到字符，我们就不会将其复制到修改后的字符串变量中。否则，我们将其复制到一个新变量中。**

## **蟒蛇 3**

```py
# declaring a string variable
str = "Geeksforgeeks is fun."

# index to remove character at
n = 4

# declaring an empty string variable for storing modified string
modified_str = ''

# iterating over the string
for char in range(0, len(str)):

    # checking if the char index is equivalent to n
    if(char != n):
        # append original string character
        modified_str += str[char]

print("Modified string after removing ", n, "th character ")
print(modified_str)
```

****输出:****

```py
Modified string after removing  4 th character  
Geekforgeeks is fun.
```

****时间复杂度=** O(n)，其中 n 为字符串的长度。**

****空间复杂度=** O(n)**

**第二种方法**使用在一个索引值范围内提取字符序列的思想。Python 中使用的语法如下:****

> ******string _ name【start _ index:end_index】**
> –提取从 start_index
> 开始且小于 end _ index 的字符，即直到 end_index-1。
> 如果我们不指定 end_index，它会一直计算到字符串的长度。****

****因此，我们将字符串的所有字符分为两部分提取，第一部分直到第 n 个索引，另一部分从第 n+1 个索引开始。然后我们将这两部分附加在一起。****

## ****蟒蛇 3****

```py
**# declaring a string variable
str = "Geeksforgeeks is fun."

# index to remove character at
n = 8

# extracts 0 to n-1th index
first_part = str[0:n]

# extracts characters from n+1th index until the end
second_part = str[n+1:]
print("Modified string after removing ", n, "th character ")

# combining both the parts together
print(first_part+second_part)**
```

******输出:******

```py
**Modified string after removing  8 th character  
Geeksforeeks is fun.**
```

******时间复杂度=** O(n)，其中 n 为字符串的长度。****

******空间复杂度=** O(n)****