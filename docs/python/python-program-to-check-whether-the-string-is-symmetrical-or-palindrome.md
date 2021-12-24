# Python 程序检查字符串是对称还是回文

> 原文:[https://www . geesforgeks . org/python-program-to-check-string-是对称还是回文/](https://www.geeksforgeeks.org/python-program-to-check-whether-the-string-is-symmetrical-or-palindrome/)

给定一个字符串。任务是检查字符串是否对称，是否回文。如果字符串的两半相同，则称字符串是对称的；如果字符串的一半与另一半相反，或者向前或向后读取时字符串看起来相同，则称字符串是回文字符串。

**示例:**

```
Input: khokho
Output: 
The entered string is symmetrical
The entered string is not palindrome

Input:amaama
Output:
The entered string is symmetrical
The entered string is palindrome
```

**进场 1:** 进场很幼稚。在回文的情况下，循环运行到字符串的中间，第一个和最后一个字符匹配。如果字符不相似，则循环中断，字符串不是回文，否则字符串是回文。在对称的情况下，如果字符串长度是偶数，那么字符串被分成两半，循环运行，检查这两半字符串的字符。如果字符不相似，则循环中断，字符串不对称，否则字符串对称。如果字符串长度是奇数，那么字符串会被分成两半，这样中间的元素就不会被选中，并重复上述相同的步骤。

下面是实现。

## 蟒蛇 3

```
# Python program to demonstrate
# symmetry and palindrome of the
# string

# Function to check whether the
# string is palindrome or not
def palindrome(a):

    # finding the mid, start
    # and last index of the string
    mid = (len(a)-1)//2     #you can remove the -1 or you add <= sign in line 21 
    start = 0                #so that you can compare the middle elements also.
    last = len(a)-1
    flag = 0

    # A loop till the mid of the
    # string
    while(start <= mid):

        # comparing letters from right
        # from the letters from left
        if (a[start]== a[last]):

            start += 1
            last -= 1

        else:
            flag = 1
            break;

    # Checking the flag variable to
    # check if the string is palindrome
    # or not
    if flag == 0:
        print("The entered string is palindrome")
    else:
        print("The entered string is not palindrome")

# Function to check whether the
# string is symmetrical or not       
def symmetry(a):

    n = len(a)
    flag = 0

    # Check if the string's length
    # is odd or even
    if n%2:
        mid = n//2 +1
    else:
        mid = n//2

    start1 = 0
    start2 = mid

    while(start1 < mid and start2 < n):

        if (a[start1]== a[start2]):
            start1 = start1 + 1
            start2 = start2 + 1
        else:
            flag = 1
            break

    # Checking the flag variable to
    # check if the string is symmetrical
    # or not
    if flag == 0:
        print("The entered string is symmetrical")
    else:
        print("The entered string is not symmetrical")

# Driver code
string = 'amaama'
palindrome(string)
symmetry(string)
```

**Output**

```
The entered string is palindrome
The entered string is symmetrical

```

**方法 2:**

我们在这个方法中使用切片。

## 蟒蛇 3

```
string = 'amaama'
half = int(len(string) / 2)

if len(string) % 2 == 0:  # even
    first_str = string[:half]
    second_str = string[half:]
else:  # odd
    first_str = string[:half]
    second_str = string[half+1:]

# symmetric
if first_str == second_str:
    print(string, 'string is symmertical')
else:
    print(string, 'string is not symmertical')

# palindrome
if first_str == second_str[::-1]:  # ''.join(reversed(second_str)) [slower]
    print(string, 'string is palindrome')
else:
    print(string, 'string is not palindrome')
```

**Output**

```
amaama string is symmertical
amaama string is palindrome

```