# Python 列表理解|给定范围内数组的三向分区

> 原文:[https://www . geesforgeks . org/python-list-understance-三路-分区-数组-围绕给定范围/](https://www.geeksforgeeks.org/python-list-comprehension-three-way-partitioning-array-around-given-range/)

给定一个数组和一个范围**【low val，high val】**，围绕该范围对数组进行划分，使数组分为三部分。
1)所有比**小的元素都是第一位的。
2)范围内的所有元素**低值到高值**接下来。
3)所有大于**高值**的元素出现在最后。
三套单个元素可以任意顺序出现。**

示例:

```
Input: arr = [1, 14, 5, 20, 4, 2, 54, 20, 87, 98, 3, 1, 32]  
        lowVal = 14, highVal = 20
Output: arr = [1, 5, 4, 2, 3, 1, 14, 20, 20, 54, 87, 98, 32]

Input: arr = [1, 14, 5, 20, 4, 2, 54, 20, 87, 98, 3, 1, 32]  
       lowVal = 20, highVal = 20       
Output: arr = [1, 14, 5, 4, 2, 3, 1, 20, 20, 54, 87, 98, 32] 

```

这个问题我们已经有了解决方案，请参考[给定范围内数组的三向分区](https://www.geeksforgeeks.org/three-way-partitioning-of-an-array-around-a-given-range/)链接。我们可以使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 python 中快速解决这个问题。方法很简单，

1.  将列表分为三部分，第一部分包含小于 **lowVal** 的元素，第二部分包含介于 **lowVal** 和 **highVal** 之间的元素，第三部分包含大于 **highVal** 的元素。
2.  将所有三个部分连接在一起。

```
# Function for Three way partitioning of an
# array around a given range

def threeWay(input, lowVal, highVal):

# separate input list in three parts
     first = [ num for num in input if num<lowVal ]
     second = [ num for num in input if (num>=lowVal and num<=highVal) ]
     third = [ num for num in input if num>highVal ]

# concatenate all three parts
     print(first + second + third)

# Driver program
if __name__ == "__main__":
    input = [1, 14, 5, 20, 4, 2, 54, 20, 87, 98, 3, 1, 32]
    lowVal = 14
    highVal = 20
    threeWay(input, lowVal, highVal)
```

输出:

```
[1, 5, 4, 2, 3, 1, 14, 20, 20, 54, 87, 98, 32]

```