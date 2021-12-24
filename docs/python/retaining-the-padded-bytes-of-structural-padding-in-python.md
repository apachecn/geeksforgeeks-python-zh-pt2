# 保留 Python 中结构填充的填充字节

> 原文:[https://www . geeksforgeeks . org/保留结构填充字节的 python/](https://www.geeksforgeeks.org/retaining-the-padded-bytes-of-structural-padding-in-python/)

结构填充是指将数据排列成固定大小的块，以便于特定计算机体系结构的操作，从而简化密码算法。我们填充(添加足够的字节)操作数据(不一定是结构化的)，以便为机器服务。填充字节可能会中断原始数据，要确定填充字节的数量，以下方法会有所帮助。

这是传统的结构填充，以“空白”作为填充实体，这不会帮助我们提取原始数据的精确字节

**例 1:**

```
# padding with 'white spaces' 
def pad(text, block_size):

    # Calculate the missing number of bytes
    pad_size = block_size - len(text)% block_size

    # Add missing bytes with 'white spaces'
    fit_text = text + (" "*pad_size)
    return (fit_text)
def main():

    # text already contains 'white spaces' to 
    # the Right, assumptions go wrong here 
    block_size = 20
    text = "HALL OF BYTES   "  
    print(pad(text, block_size))

main()
```

**输出:**

```
'HALL OF BYTES       '
```

**例 2:**

下面是如何保留填充的字节数

```
# Python Program to retain padded bytes
def pad(text, block_size):

    # Calculate the missing number of 
    # bytes, say N
    pad_size = block_size - len(text)% block_size

    # Pad with character of N
    fit_text = text + chr(pad_size)*pad_size

    return (fit_text, )

def main():
    text = "HALL OF BYTES"

    # structural unit of size 20
    block_size = 20
    print(pad(text, block_size))

# Driver Code
main()
```

**输出:**

```
'HALL OF BYTES\x07\x07\x07\x07\x07\x07\x07' 
# thus 7 bytes were padded. 
```

```
# appropriate method to retain padded bytes
def pad(text, block_size):

    # Calculate the missing number of 
    # bytes, say N
    pad_size = block_size - len(text)% block_size

    # Pad with character of N
    fit_text = text + chr(pad_size)*pad_size

    return (fit_text, )

def main():
    text = "PRECISELY RETAINED"

    # structural unit of size 20
    block_size = 20
    print(pad(text, block_size))

# Driver Code
main()
```

**输出:**

```
'PRECISELY RETAINED\x02\x02' 
# Thus two bytes were padded.
```