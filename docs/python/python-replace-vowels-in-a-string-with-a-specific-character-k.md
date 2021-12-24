# Python–用特定字符 K 替换字符串中的元音

> 原文:[https://www . geesforgeks . org/python-用特定字符替换字符串中的元音-k/](https://www.geeksforgeeks.org/python-replace-vowels-in-a-string-with-a-specific-character-k/)

给定一个字符串，用字符 k 替换所有元音。

> ***输入** : test_str =“极客为极客”；K='#'*
> ***输出**:*G # # ks f # r G # # ks*"*
> ***解释**:test _ str 中的所有元音都被一个给定的特定字符替换。*
> 
> ***输入**:test _ list =“GFG”；k =“{ content }”# x201；*
> ***输出** : GFG*
> ***解释**:由于 test_str 不包含元音，所以返回相同的字符串。*

**方法#1:使用循环+替换()**

首先创建一串元音，然后通过给定的 *test_str* 、在 *test_str* 中检测到一个元音，使用 *replace()* 方法将该元音替换为 *K* 。

## 蟒蛇 3

```
# Function to Replace each vowel in
# the string with a specified character
def replaceVowelsWithK(test_str, K):

    # string of vowels
    vowels = 'AEIOUaeiou'

    # iterating to check vowels in string
    for ele in vowels:

        # replacing vowel with the specified character
        test_str = test_str.replace(ele, K)

    return test_str

# Driver Code
# input string
input_str = "Geeks for Geeks"

# specified character
K = "#"

# printing input
print("Given Sting:", input_str)
print("Given Specified Character:", K)

# printing output
print("After replacing vowels with the specified character:",
      replaceVowelsWithK(input_str, K))
```

**Output**

```
Given Sting: Geeks for Geeks
Given Specified Character: #
After replacing vowels with the specified character: G##ks f#r G##ks
```

**输出:**

> 给定 Sting:极客的极客
> 给定指定字符:#
> 用指定字符替换元音后:G##ks f#r G##ks

**方法 2:使用嵌套循环**

在这里，我们首先将给定的字符串转换成一个列表，然后创建一个元音列表和一个空列表，即 *new_string* 。然后比较*字符串列表和元音列表*的元素，如果元素是元音，那么 *K* 被附加到*新字符串*上，否则给定字符串的元素被附加。

## 蟒蛇 3

```
# Function to Replace each vowel
# in the string with a specified character
def replaceVowelsWithK(test_str, K):

    # creating list of vowels
    vowels_list = ['A', 'E', 'I', 'O', 'U', 'a', 'e', 'i', 'o', 'u']

    # creating empty list
    new_string = []

    # converting the given string to list
    string_list = list(test_str)

    # running 1st iteration for
    # comparing all the
    # characters of string with
    # the vowel characters
    for char in string_list:

        # running 2nd iteration for
        # comparing all the characters
        # of vowels with the string character
        for char2 in vowels_list:

            # comparing string character
            # and vowel character
            if char == char2:

                # if condition is true then adding
                # the specific character entered
                # by the user in the new list
                new_string.append(K)
                break

        # else adding the character
        else:
            new_string.append(char)

    # return the converted list into string
    return(''.join(new_string))

# Driver Code
# input string
input_str = "Geeks for Geeks"

# specified character
K = "#"

# printing input
print("Given Sting:", input_str)
print("Given Specified Character:", K)

# printing output
print("After replacing vowels with the specified character:",
      replaceVowelsWithK(input_str, K))
```

**Output**

```
Given Sting: Geeks for Geeks
Given Specified Character: #
After replacing vowels with the specified character: G##ks f#r G##ks
```