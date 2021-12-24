# Python 程序打印列表中的奇数

> 原文:[https://www . geesforgeks . org/python-程序到打印-列表中的奇数/](https://www.geeksforgeeks.org/python-program-to-print-odd-numbers-in-a-list/)

给定一个数字列表，编写一个 Python 程序来打印给定列表中的所有奇数。

**示例:**

```
Input: list1 = [2, 7, 5, 64, 14]
Output: [7, 5]

Input: list2 = [12, 14, 95, 3, 73]
Output: [95, 3, 73]
```

1.  **[Using for loop :](https://www.geeksforgeeks.org/loops-in-python/)** Iterate each element in the list using for loop and check if num % 2 != 0\. If the condition satisfies, then only print the number.

    ```
    # Python program to print odd Numbers in a List

    # list of numbers
    list1 = [10, 21, 4, 45, 66, 93]

    # iterating each number in list
    for num in list1:

        # checking condition
        if num % 2 != 0:
           print(num, end = " ")
    ```

    **输出:**

    ```
    21 45 93 
    ```

2.  **[Using while loop](https://www.geeksforgeeks.org/loops-in-python/) :**

    ```
    # Python program to print odd Numbers in a List

    # list of numbers
    list1 = [10, 21, 4, 45, 66, 93]
    i = 0

    # using while loop        
    while(i < len(list1)):

        # checking condition
        if list1[i] % 2 != 0:
            print(list1[i], end = " ")

        # increment i  
        i += 1

    ```

    **输出:**

    ```
    21 45 93 
    ```

3.  **[Using list comprehension](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) :**

    ```
    # Python program to print odd Numbers in a List

    # list of numbers
    list1 = [10, 21, 4, 45, 66, 93]

    only_odd = [num for num in list1 if num % 2 == 1]

    print(only_odd)
    ```

    **输出:**

    ```
    21 45 93 
    ```

4.  **[Using lambda expressions :](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**

    ```
    # Python program to print odd numbers in a List

    # list of numbers 
    list1 = [10, 21, 4, 45, 66, 93, 11] 

    # we can also print odd no's using lambda exp. 
    odd_nos = list(filter(lambda x: (x % 2 != 0), list1))

    print("Odd numbers in the list: ", odd_nos) 
    ```

    **输出:**

    ```
    Odd numbers in the list:  [21, 45, 93, 11]
    ```