# Python 图|给定整数的二进制表示中最长连续 1 的长度

> 原文:[https://www . geesforgeks . org/python-map-length-最长-连续-1s-二进制-表示-给定-整数/](https://www.geeksforgeeks.org/python-map-length-longest-consecutive-1s-binary-representation-given-integer/)

给定一个数 n，求其二进制表示中最长的连续 1 的长度。

示例:

```py
Input : n = 14
Output : 3
The binary representation of 14 is 1110.

Input : n = 222
Output : 4
The binary representation of 222 is 11011110.

```

这个问题我们已经有了解决方案，请参考链接中的[二进制表示中最长连续 1 的长度。我们可以用 python 快速解决这个问题。方法很简单，](https://www.geeksforgeeks.org/length-longest-consecutive-1s-binary-representation/)

[](https://www.geeksforgeeks.org/length-longest-consecutive-1s-binary-representation/)
2.  [Use](https://www.geeksforgeeks.org/length-longest-consecutive-1s-binary-representation/) [bin ()](https://www.geeksforgeeks.org/bin-in-python/) function to convert decimal numbers into binary numbers, and delete the first two characters "0b", because **bin ()** function returns the binary representation of numbers in the form of strings with "0b" as prefix.
3.  Use the **split ()** method of strings to separate all substrings of consecutive 1s separated by zeros.
4.  The maximum length of the split substring of 1.

```py
# Function to find Length of the Longest Consecutive
# 1's in Binary Representation

def maxConsecutive1(input):
     # convert number into it's binary
     input = bin(input)

     # remove first two characters of output string
     input = input[2:]

     # input.split('0') --> splits all sub-strings of 
     # consecutive 1's separated by 0's, output will 
     # be like ['11','1111']
     # map(len,input.split('0'))  --> map function maps
     # len function on each sub-string of consecutive 1's
     # max() returns maximum element from a list
     print (max(map(len, input.split('0'))))

# Driver program
if __name__ == '__main__':
    input = 222
    maxConsecutive1(input)
```

输出:

```py
4

```