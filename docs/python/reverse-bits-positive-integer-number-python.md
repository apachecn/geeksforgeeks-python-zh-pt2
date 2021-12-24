# Python 中正整数的反转位

> 原文:[https://www . geesforgeks . org/reverse-bits-正整数-number-python/](https://www.geeksforgeeks.org/reverse-bits-positive-integer-number-python/)

给定一个正整数和位的大小，反转它的所有位，并返回具有反转位的数字。

示例:

```
Input : n = 1, bitSize=32
Output : 2147483648  
On a machine with size of 
bit as 32\. Reverse of 0....001 is
100....0.

Input : n = 2147483648, bitSize=32
Output : 1  

```

我们可以用 Python 快速解决这个问题。方法很简单，

1.  使用 [bin(num)](https://www.geeksforgeeks.org/bin-in-python/) 函数将整数转换为其二进制表示。
2.  **bin()** 函数追加 **0b** 作为数字二进制表示的前缀，跳过二进制表示的前两个字符，反转字符串的剩余部分。
3.  正如我们在内存中所知，一个数字的任何二进制表示都是在从左数最后一个设置位之后用前导零填充的，这意味着我们需要在反转剩余字符串之后追加**位大小–len(reversed Bits)**个零。
4.  现在使用 **int(string，base)** 方法将二进制表示转换为整数。

### int()方法如何工作？

**int(string，base)** 方法取一个 string 和 base 来标识这个 string 指的是什么数字系统(二进制=2，heaxadecimal=16，八进制=8 等。)并将字符串相应地转换为十进制数字系统。比如；int('1010 '，2) = 10。

```
# Function to reverse bits of positive  
# integer number 

def reverseBits(num,bitSize): 

     # convert number into binary representation 
     # output will be like bin(10) = '0b10101' 
     binary = bin(num) 

     # skip first two characters of binary 
     # representation string and reverse 
     # remaining string and then append zeros 
     # after it. binary[-1:1:-1]  --> start 
     # from last character and reverse it until 
     # second last character from left 
     reverse = binary[-1:1:-1] 
     reverse = reverse + (bitSize - len(reverse))*'0'

     # converts reversed binary string into integer 
     print (int(reverse,2)) 

# Driver program 
if __name__ == "__main__": 
    num = 1
    bitSize = 32
    reverseBits(num,bitSize)
```

输出:

```
2147483648

```