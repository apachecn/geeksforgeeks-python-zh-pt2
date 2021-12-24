# Python 程序拆分并连接字符串

> 原文:[https://www . geesforgeks . org/python-program-split-join-string/](https://www.geeksforgeeks.org/python-program-split-join-string/)

Python 程序，用于根据分隔符拆分字符串，并使用另一个分隔符连接字符串。

拆分字符串有时非常有用，尤其是当您只需要字符串的某些部分时。一个简单而有效的例子是把一个人的名和姓分开。另一个应用程序是 CSV(逗号分隔文件)。我们使用 split 从 CSV 获取数据，使用 join 将数据写入 CSV。

在 Python 中，我们可以使用函数 ***split()*** 来拆分一个字符串，使用函数 ***join()*** 来连接一个字符串。有关 split()和 join()函数的详细文章，请参考 Python 中的 [split()和 Python 中的](https://www.geeksforgeeks.org/python-string-split/) [join()。](https://www.geeksforgeeks.org/join-function-python/)

示例:

```py
Split the string into list of strings

Input : Geeks for Geeks
Output : ['Geeks', 'for', 'Geeks']

Join the list of strings into a string based on delimiter ('-')

Input :  ['Geeks', 'for', 'Geeks']
Output : Geeks-for-Geeks

```

下面是基于分隔符拆分和连接字符串的 Python 代码:

```py
# Python program to split a string and  
# join it using different delimiter

def split_string(string):

    # Split the string based on space delimiter
    list_string = string.split(' ')

    return list_string

def join_string(list_string):

    # Join the string based on '-' delimiter
    string = '-'.join(list_string)

    return string

# Driver Function
if __name__ == '__main__':
    string = 'Geeks for Geeks'

    # Splitting a string
    list_string = split_string(string)
    print(list_string)

     # Join list of strings into one
    new_string = join_string(list_string)
    print(new_string)
```

输出:

```py
['Geeks', 'for', 'Geeks']
Geeks-for-Geeks

```