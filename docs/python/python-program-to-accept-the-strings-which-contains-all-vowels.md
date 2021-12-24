# Python |接受包含所有元音的字符串的程序

> 原文:[https://www . geesforgeks . org/python-program-to-accept-the-strings-其中包含所有元音/](https://www.geeksforgeeks.org/python-program-to-accept-the-strings-which-contains-all-vowels/)

给定一个字符串，任务是检查每个元音是否存在。如果元音以大写或小写出现，我们认为它是存在的。即‘a’、‘e’、‘I’。' O '，' U '或' A '，' E '，' I '，' O '，' U '。
**例:**

```
Input : geeksforgeeks
Output : Not Accepted
All vowels except 'o' are not present

Input : ABeeIghiObhkUul
Output : Accepted
All vowels are present
```

**方法:**首先，使用 set()函数创建一组元音。检查字符串的每个字符是否是元音，如果是元音，则添加到集合 s 中。从循环中出来后，检查集合 s 的长度，如果集合 s 的长度等于元音集合的长度，则字符串被接受，否则不被接受。
以下是执行情况:

## 蟒蛇 3

```
# Python program to accept the strings
# which contains all the vowels

# Function for check if string
# is accepted or not
def check(string) :

    string = string.lower()

    # set() function convert "aeiou"
    # string into set of characters
    # i.e.vowels = {'a', 'e', 'i', 'o', 'u'}
    vowels = set("aeiou")

    # set() function convert empty
    # dictionary into empty set
    s = set({})

    # looping through each
    # character of the string
    for char in string :

        # Check for the character is present inside
        # the vowels set or not. If present, then
        # add into the set s by using add method
        if char in vowels :
            s.add(char)
        else:
            pass

    # check the length of set s equal to length
    # of vowels set or not. If equal, string is 
    # accepted otherwise not
    if len(s) == len(vowels) :
        print("Accepted")
    else :
        print("Not Accepted")

# Driver code
if __name__ == "__main__" :

    string = "SEEquoiaL"

    # calling function
    check(string)
```

**Output**

```
Accepted

```