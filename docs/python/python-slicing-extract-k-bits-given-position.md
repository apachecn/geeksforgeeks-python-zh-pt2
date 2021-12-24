# Python 切片|从给定位置提取“k”位

> 原文:[https://www . geesforgeks . org/python-slicing-extract-k-bits-给定位置/](https://www.geeksforgeeks.org/python-slicing-extract-k-bits-given-position/)

如何从数字中给定的位置“p”提取“k”位？

**示例:**

```
Input : number = 171
             k = 5 
             p = 2
Output : The extracted number is 21
171 is represented as 10101011 in binary,
so, you should get only 10101 i.e. 21.

Input : number = 72
            k = 5 
            p = 1
Output : The extracted number is 8
72 is represented as 1001000 in binary,
so, you should get only 01000 i.e 8.

```

对于这个问题，我们已经有了解决方案，请参考[从数字](https://www.geeksforgeeks.org/extract-k-bits-given-position-number/)链接中的给定位置提取“k”位。我们可以使用[切片](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 python 中快速解决这个问题。方法很简单，

1.  使用 [bin()](https://www.geeksforgeeks.org/bin-in-python/) 函数将给定的数字转换为它的二进制，并从中删除前两个字符' 0b '，因为 bin 函数在输出二进制字符串中追加' 0b '作为前缀。
2.  我们需要从右边的起始位置 p 开始提取 k 位，这意味着提取的子串的结束索引将是**end =(len(binary)–p)**，开始索引将是原始二进制串的**start = end–k+1**。
3.  再次将提取的子字符串转换为十进制。

```
# Function to extract ‘k’ bits from a given
# position in a number

def extractKBits(num,k,p):

     # convert number into binary first
     binary = bin(num)

     # remove first two characters
     binary = binary[2:]

     end = len(binary) - p
     start = end - k + 1

     # extract k  bit sub-string
     kBitSubStr = binary[start : end+1]

     # convert extracted sub-string into decimal again
     print (int(kBitSubStr,2))

# Driver program
if __name__ == "__main__":
    num = 171
    k = 5
    p = 2
    extractKBits(num,k,p)

```

**输出:**

```
21

```