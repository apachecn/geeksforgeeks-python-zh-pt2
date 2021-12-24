# Python 程序使用集合

在三个列表中查找公共元素

> 原文:[https://www . geesforgeks . org/python-program-find-common-elements-三个列表-使用-set/](https://www.geeksforgeeks.org/python-program-find-common-elements-three-lists-using-sets/)

先决条件:[Python 中的集合](https://www.geeksforgeeks.org/sets-in-python/)

给定三个数组，我们必须使用集合在三个排序列表中找到公共元素。

示例:

```py
Input : ar1 = [1, 5, 10, 20, 40, 80]
        ar2 = [6, 7, 20, 80, 100]
        ar3 = [3, 4, 15, 20, 30, 70, 80, 120]

Output : [80, 20]

Input : ar1 = [1, 5, 5]
        ar2 = [3, 4, 5, 5, 10]
        ar3 = [5, 5, 10, 20]

Output : [5]

```

**方法:**
我们给出了三个数组，借助集合可以很容易地找出这些数组的交集。

交集方法只是提供两个数组的交集，您希望在这两个数组上执行交集操作(或者，它只是给出两个数组中的公共元素)。我们将取三个数组，然后取出交集。

下面是上述方法的实现:

```py
# Python3 program to find common elements 
# in three lists using sets

def IntersecOfSets(arr1, arr2, arr3):
    # Converting the arrays into sets
    s1 = set(arr1)
    s2 = set(arr2)
    s3 = set(arr3)

    # Calculates intersection of 
    # sets on s1 and s2
    set1 = s1.intersection(s2)         #[80, 20, 100]

    # Calculates intersection of sets
    # on set1 and s3
    result_set = set1.intersection(s3)

    # Converts resulting set to list
    final_list = list(result_set)
    print(final_list)

# Driver Code
if __name__ == '__main__' :

    # Elements in Array1
    arr1 = [1, 5, 10, 20, 40, 80, 100]

    # Elements in Array2
    arr2 = [6, 7, 20, 80, 100]

    # Elements in Array3
    arr3 = [3, 4, 15, 20, 30, 70, 80, 120]

    # Calling Function
    IntersecOfSets(arr1, arr2, arr3)
```

输出:

```py
[80, 20]

```