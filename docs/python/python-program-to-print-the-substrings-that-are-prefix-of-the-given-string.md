# Python 程序打印给定字符串的前缀子字符串

> 原文:[https://www . geesforgeks . org/python-program-to-print-the-substrings-即给定字符串的前缀/](https://www.geeksforgeeks.org/python-program-to-print-the-substrings-that-are-prefix-of-the-given-string/)

给定一个字符串，打印所有可能的子字符串，这些子字符串也是给定字符串的前缀。

**示例:**

```
Input : ababc         
Output : a, ab, aba, abab, ababc, a, ab

Input : abdabc          
Output : a, ab, abd, abda, abdab, abdabc, a, ab          

```

**方法:**
我们使用两个变量:**开始**和**结束**来跟踪当前子串，并遵循以下条件直到`start < len(string)`:

*   如果当前子字符串也是给定字符串的前缀，则打印并递增*结束*。如果`end == len(string)`，增加*启动*和`end = start`
*   否则增加*启动*和`end = start`

检查当前子字符串是否是给定字符串前缀的逻辑:

```
string[end] == string[end-start]
```

这利用了这样的事实:如果长度为 *L* 的子串是给定字符串的前缀，那么如果字符串中位于 *(L+1)* 索引处的字符等于 *ch* ，则在包括序列中的下一个字符 *ch* 之后获得的长度为 *L+1* 的子串也是给定字符串的前缀。

下面是上述方法的实现:

```

# Python3 code to find all possible substrings that 
# are also the prefix of the given string

# Function to print all the special substrings
def func(string):

    # Used to store the starting and
    # ending index of the substrings
    start, end = 0, 0

    while start < len(string):

        # If substring is also the prefix
        if string[end] == string[end-start]:

            # Print the substring
            print(string[start:end + 1], end= " ")
            end += 1

            if end == len(string):
                start += 1
                end = start

        # Increment the starting 
        # index of the substring        
        else:
            start += 1
            end = start

if __name__ == "__main__":

    string = "ababc"
    func(string)
```

**Output:**

```
a ab aba abab ababc a ab

```

**时间复杂度:** ![O(n^2)](img/598be626cedc018633480e0f69670fd8.png "Rendered by QuickLaTeX.com")