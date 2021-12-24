# Python 程序打印数组中所有元素合并形成的排序数

> 原文:[https://www . geesforgeks . org/python-程序-打印-排序-数字-通过合并数组中的所有元素形成/](https://www.geeksforgeeks.org/python-program-to-print-sorted-number-formed-by-merging-all-elements-in-array/)

给定一个数组 arr[]，任务是按顺序组合数组中的所有元素，并按升序对这个数字的数字进行排序。

**注意:**忽略前导零。

**示例:**

> **输入:** arr =[7，845，69，60]
> 
> **输出:** 4566789
> 
> **说明:**所有元素组合而成的数字，排序后得到的数字是“78456960”我们得到 4566789
> 
> **输入:** arr =[8，5603，109，53209]
> 
> **输出:** 1233556899
> 
> **说明:**将所有元素组合而成的数字，排序后得到“12335556899”，即为“8560310953209”

**进场:**

*   使用 [map()](https://www.geeksforgeeks.org/python-map-function/) 函数将列表中的每个元素转换为字符串。
*   使用 [join()](https://www.geeksforgeeks.org/join-function-python/) 功能加入列表。
*   使用 join()和排序的[(](https://www.geeksforgeeks.org/sorted-function-python/))对字符串进行排序
*   使用类型转换将字符串转换为整数
*   返回结果

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# python program to print sorted number by merging
# all the elements in array function to print
# sorted number

def getSortedNumber(number):

    # sorting the string
    number = ''.join(sorted(number))

    # converting string to integer
    number = int(number)

    # returning the result
    print(number)

# function to merge elements in array
def mergeArray(lis):

    # convert the elements of list to string
    lis = list(map(str, lis))

    # converting list to string
    string = ''.join(lis)

    # passing this string to sortednumber function
    getSortedNumber(string)

# Driver code
lis = [7, 845, 69,  60]

# passing list to merge array function to merge
# the elements
mergeArray(lis)
```

**输出:**

```py
4566789
```