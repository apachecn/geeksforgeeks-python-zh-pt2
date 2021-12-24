# Python |在 Regex 中使用组捕获来交换名称和日期

> 原文:[https://www . geesforgeks . org/python-swap-name-date-use-group-capture-in-regex/](https://www.geeksforgeeks.org/python-swap-name-and-date-using-group-capturing-in-regex/)

在本文中，我们将学习如何使用 Regex 中的组捕获和数字反向引用功能来交换列表中每个项目的名称和日期。

**捕获组**:括号将它们之间的正则表达式分组，并将它们内部的正则表达式匹配的文本捕获到一个编号组**即[\w ]+)** 中，该编号组可以与一个编号的反向引用(即

```py
\g<Group Number>
```

我们得到一个列表，其中每一项都是一个字符串，包含一本书的名字，后跟它的发行年份。
我们必须使用 Regex 中的 Capturing 组为列表中的每个项目交换**名称**和**日期**，并按时间顺序显示输出。让我们考虑几个例子:

**示例:**

```py
Input  : Name (Date) 
Output : Date - Name

Input  : City of Glass (2009) 
Output : 2009 - City of Glass

Input  : Pride and Prejudice (1813)
Output : 1813 - Pride and Prejudice

```

**注意:**在输出中，日期没有括在括号中，日期和名称之间有一个破折号。

**Regex _ Pattern:**([\ w]+)\(\ d { 4 })\)

**说明:**

1.  上述模式中的括号将它们之间的正则表达式分组。([\w ]+)是第一个被

    ```py
    \g<1>
    ```

    反向引用的**名称**
2.  (\d{4}) is the second group capturing **Date** which is back-referenced by

    ```py
    \g<2>
    ```

    对于每个字符串。

3.  我们使用**。sub()** 用新的替换替换字符串中最左边不重叠的 regex_pattern。

    ```py
    .subl(\g<2> - \g<1>,string)
    ```

4.  一旦交换了名称和日期，新的字符串就会附加到新的列表中。
5.  然后新列表被排序，我们遍历新列表并打印其中的每一项。

**代码:Python3 使用 Regex** 为列表中的每个项目交换名称和日期的程序

```py
# Python3 program to swap Name and Date for each item
# in the list using Regex
# sort the list after swapping to display the output
# in a chronological order

#Importing re package
import re

def swap_name_date(books=[]):
    # new empty list to store swapped data
    ordered_book_list=[]

    # RegexObject = re.compile( Regular expression, flag )
   # Compiles a regular expression pattern into a regular expression object
    regex_pattern = re.compile(r'([\w ]+) \((\d{4})\)')

    # Iterating through each item in unordered_books_list    
   # and swapping group 2 of date with group 1 of name
    for book in books:
        # Result after swapping is stored in res
        res = regex_pattern.sub('\g<2> - \g<1>' ,book)
        # res is appended to ordered_book_list
        ordered_book_list.append(res)

    # After all items of unordered_books_list are swapped
        # and appended to ordered_book_list
    # ordered_book_list is sorted
    ordered_book_list.sort()

    # Iterating through each item of ordered_book_list and printing it
    for book in ordered_book_list:
        print(book)

# Driver Code
if __name__=="__main__":
    #unordered_books_list stores data to be swapped
    unordered_books_list = [
         "City of Glass (2009)",
         "The Great Gatsby (1925)",
         "Pride and Prejudice (1813)",
         "The Hunger Games (2008)",
         "To Kill a Mockingbird (1960)",
         "The Notebook (1996)",
         "Jane Eyre (1847)",
         "The Catcher in the Rye (1951)",
         "The Lord of the Rings (1954)",
         "All the light We Cannot See (2014)",
         "Immortals of Meluha (2010)"
         ]

    swap_name_date(unordered_books_list)
```

**输出:**

```py
1813 - Pride and Prejudice 
1847 - Jane Eyre
1925 - The Great Gatsby
1951 - The Catcher in the Rye
1954 - The Lord of the Rings
1960 - To Kill a Mockingbird
1996 - The Notebook
2008 - The Hunger Games
2009 - City of Glass
2010 - Immortals of Meluha
2014 - All the light We Cannot See

```