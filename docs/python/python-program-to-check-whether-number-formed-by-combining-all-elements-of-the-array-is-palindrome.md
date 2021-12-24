# Python 程序检查数组所有元素组合形成的数字是否为回文

> 原文:[https://www . geesforgeks . org/python-program-to-check-number-formed-通过组合数组的所有元素来检查数组是否是回文/](https://www.geeksforgeeks.org/python-program-to-check-whether-number-formed-by-combining-all-elements-of-the-array-is-palindrome/)

给定一个数组 arr[]，任务是按顺序组合数组中的所有元素，并检查它是否是回文。

**示例**:

> **输入:** arr[] ={1，69，54，45，96，1}
> 
> **输出:**回文
> 
> **说明:**所有元素组合而成的数为**“1695445961”**，为回文
> 
> **输入** : arr[] ={2，73，95，59，96，2}
> 
> **输出:**不是回文
> 
> **说明**:所有元素组合而成的数字是**“2739559962”**，不是回文

**方法 1:** 使用 map()和 join()

*   使用[**贴图()**](https://www.geeksforgeeks.org/python-map-function/) 功能将列表中的每个元素转换为字符串。
*   加入列表使用[**加入()**](https://www.geeksforgeeks.org/join-function-python/) 功能。
*   检查它是否是回文。
*   如果是，那么打印回文。
*   如果没有打印，不是回文。

**以下是上述方法的实现:**

## 蟒蛇 3

```
# function to check palindrome
def checkPalindrome(string):

    # reverse the string
    rev = string[::-1]

    # checking if string is equal to reverse
    if(string == rev):
        return True
    else:
        return False

# function to convert list to single number string
def joinArray(lis):

    # convert the elements of list to string
    lis = list(map(str, lis))

    # converting list to string
    number = ''.join(lis)

    # checking if it is palindrome
    if(checkPalindrome(number)):
        return True
    else:
        return False

# Driver code
lis = [1, 76, 39, 93, 67, 1]
if(joinArray(lis)):
    print("Palindrome")
else:
    print("not Palindrome")
```

**输出:**

```
Palindrome
```

**时间复杂度:** O(n)

**方法 2:** 使用类型转换和字符串连接

*   取一根空弦，说**弦。**
*   遍历列表，并使用类型转换将每个元素转换为字符串
*   使用字符串连接将其添加到**字符串**中
*   检查**字符串**是否是回文

**以下是上述方法的实现:**

## 蟒蛇 3

```
# function to check palindrome
def checkPalindrome(string):

    # reverse the string
    rev = string[::-1]

    # checking if string is equal to reverse
    if(string == rev):
        return True
    else:
        return False

# function to convert list to single number string
def joinArray(lis):

    # defining empty string as number
    number = ""

    # convert the elements of list to string using type conversion
    for i in lis:

        # converting to string
        i = str(i)

        # concat this to string
        number = number + i

    # checking if it is palindrome
    if(checkPalindrome(number)):
        return True
    else:
        return False

# Driver code
lis = [1, 76, 39, 93, 67, 1]

if(joinArray(lis)):
    print("Palindrome")
else:
    print("not Palindrome")
```

**输出:**

```
Palindrome
```