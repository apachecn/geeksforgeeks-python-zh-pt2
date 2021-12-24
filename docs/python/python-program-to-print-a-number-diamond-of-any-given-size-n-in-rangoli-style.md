# Python 程序以 Rangoli 样式

打印任意给定大小 N 的数字钻石

> 原文:[https://www . geesforgeks . org/python-program-to-print-a-number-of-diamond-of-no-in-rangoli-style/](https://www.geeksforgeeks.org/python-program-to-print-a-number-diamond-of-any-given-size-n-in-rangoli-style/)

给定一个整数 N，任务是以 rangoli 样式打印一个大小为 N 的数字菱形，其中 N 表示从数字“1”到第 N 个数字。

**示例:**

```
Input : 
2
Output :
--2--
2-1-2
--2--

Input : 
3
Output :
----3----
--3-2-3--
3-2-1-2-3
--3-2-3--
----3----

Input :
4
Output :
------4------
----4-3-4----
--4-3-2-3-4--
4-3-2-1-2-3-4
--4-3-2-3-4--
----4-3-4----
------4------

```

**进场:**
首先从第一行打印到中间一行，然后从中间一行后一行打印到最后一行。每行的位置总数将为`4(N-1) + 1`。行数将为`2(N-1) + 1`。时间的复杂性是`O(N^2)`。

下面是实现。

```
def print_diamond(size):

    # print the first triangle
    # (the upper half)
    for i in range (size):

        # print from first row till
        # middle row
        rownum = i + 1
        num_alphabet = 2 * rownum - 1
        space_in_between_alphabets = num_alphabet - 1

        total_spots = (2 * size - 1) * 2 - 1
        total_space = total_spots - num_alphabet

        space_leading_trailing = total_space - space_in_between_alphabets
        lead_space = int(space_leading_trailing / 2)
        trail_space = int(space_leading_trailing / 2)

        # print the leading spaces
        for j in range(lead_space):
            print('-', end ='')

        # determine the middle character
        mid_char = (1 + size - 1) - int(num_alphabet / 2)

        # start with the last character 
        k = 1 + size - 1
        is_alphabet_printed = False
        mid_char_reached = False

        # print the numbers alternated by '-'
        for j in range(num_alphabet + space_in_between_alphabets):

            if not is_alphabet_printed:
                print(str(k), end ='')
                is_alphabet_printed = True

                if k == mid_char:
                    mid_char_reached = True

                if mid_char_reached == True:
                    k += 1

                else:
                    k -= 1

            else:
                print('-', end ='')
                is_alphabet_printed = False

        # print the trailing spaces
        for j in range(trail_space):
            print('-', end ='')

        # go to the next line
        print('')

    # print the rows after middle row 
    # till last row (the second triangle 
    # which is inverted, i.e., the lower half)
    for i in range(size + 1, 2 * size):

        rownum = i
        num_alphabet = 2 * (2 * size - rownum) - 1
        space_in_between_alphabets = num_alphabet - 1

        total_spots = (2 * size - 1) * 2 - 1
        total_space = total_spots - num_alphabet

        space_leading_trailing = total_space - space_in_between_alphabets
        lead_space = int(space_leading_trailing / 2)
        trail_space = int(space_leading_trailing / 2)

        # print the leading spaces
        for j in range(lead_space):
            print('-', end ='')

        mid_char = (1 + size - 1) - int(num_alphabet / 2)

        # start with the last char
        k = 1 + size - 1
        is_alphabet_printed = False
        mid_char_reached = False

        # print the numbers alternated by '-'
        for j in range(num_alphabet + space_in_between_alphabets):

            if not is_alphabet_printed:
                print(str(k), end ='')
                is_alphabet_printed = True

                if k == mid_char:
                    mid_char_reached = True

                if mid_char_reached == True:
                    k += 1

                else:
                    k -= 1

            else:
                print('-', end ='')
                is_alphabet_printed = False

        # print the trailing spaces
        for j in range(trail_space):
            print('-', end ='')

        # go to the next line
        print('')

# Driver Code
if __name__ == '__main__':

    n = 5
    print_diamond(n)
```

**输出:**

```
--------5--------
------5-4-5------
----5-4-3-4-5----
--5-4-3-2-3-4-5--
5-4-3-2-1-2-3-4-5
--5-4-3-2-3-4-5--
----5-4-3-4-5----
------5-4-5------
--------5--------

```