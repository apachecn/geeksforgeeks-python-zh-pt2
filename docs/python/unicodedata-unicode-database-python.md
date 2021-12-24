# Unicode 数据–Python 中的 Unicode 数据库

> 原文:[https://www . geeksforgeeks . org/unicode data-unicode-database-python/](https://www.geeksforgeeks.org/unicodedata-unicode-database-python/)

**Unicode 字符数据库(UCD)** 由 Unicode 标准附录#44 定义，该附录定义了所有 Unicode 字符的字符属性。该模块提供对 UCD 的访问，并使用由 Unicode 字符数据库定义的相同符号和名称。

**模块定义的功能:**

*   **unicodedata . lookup(name)**
    这个函数通过名字查找字符。如果在数据库中找到具有给定名称的字符，则返回相应的字符，否则将引发 Keyerror。

**示例:**

```
import unicodedata

print (unicodedata.lookup('LEFT CURLY BRACKET'))
print (unicodedata.lookup('RIGHT CURLY BRACKET'))
print (unicodedata.lookup('ASTERISK'))

# gives error as there is 
# no symbol called ASTER
# print (unicodedata.lookup('ASTER'))
```

**输出:**

```
{
}
*

```

*   **unicodedata.name(chr[, default])**
    This function returns the name assigned to the given character as a string. If no name is defined, default is returned by the function otherwise ValueError is raised if name is not given.

    **示例:**

    ```
    import unicodedata

    print (unicodedata.name(u'/'))
    print (unicodedata.name(u'|'))
    print (unicodedata.name(u':'))
    ```

    **输出:**

    ```
    SOLIDUS
    VERTICAL LINE
    COLON

    ```

    *   **unicodedata.decimal(chr[, default])**
    This function returns the decimal value assigned to the given character as integer. If no value is defined, default is returned by the function otherwise ValueError is raised if value is not given.

    **示例:**

    ```
    import unicodedata

    print (unicodedata.decimal(u'9'))
    print (unicodedata.decimal(u'a'))
    ```

    **输出:**

    ```
    9
    Traceback (most recent call last):
      File "7e736755dd176cd0169eeea6f5d32057.py", line 4, in 
        print unicodedata.decimal(u'a')
    ValueError: not a decimal

    ```

    *   **unicodedata.digit(chr[, default])**
    This function returns the digit value assigned to the given character as integer. If no value is defined, default is returned by the function otherwise ValueError is raised if value is not given.

    **示例:**

    ```
    import unicodedata

    print (unicodedata.decimal(u'9'))
    print (unicodedata.decimal(u'143'))
    ```

    **输出:**

    ```
    9
    Traceback (most recent call last):
      File "ad47ae996380a777426cc1431ec4a8cd.py", line 4, in 
        print unicodedata.decimal(u'143')
    TypeError: need a single Unicode character as parameter

    ```

    *   **unicodedata.numeric(chr[, default])**
    This function returns the numeric value assigned to the given character as integer. If no value is defined, default is returned by the function otherwise ValueError is raised if value is not given.

    **示例:**

    ```
    import unicodedata

    print (unicodedata.decimal(u'9'))
    print (unicodedata.decimal(u'143'))
    ```

    **输出:**

    ```
    9
    Traceback (most recent call last):
      File "ad47ae996380a777426cc1431ec4a8cd.py", line 4, in 
        print unicodedata.decimal(u'143')
    TypeError: need a single Unicode character as parameter

    ```

    *   **unicodedata.category(chr)**
    This function returns the general category assigned to the given character as string. For example, it returns ‘L’ for letter and ‘u’ for uppercase.

    **示例:**

    ```
    import unicodedata

    print (unicodedata.category(u'A'))
    print (unicodedata.category(u'b'))
    ```

    **输出:**

    ```
    Lu
    Ll

    ```

    *   **unicodedata .双向(chr)**
    这个函数返回指定给字符串的双向类。例如，它返回阿拉伯语的“A”和数字的“N”。如果没有定义这样的值，这个函数将返回一个空字符串。

**示例:**

```
import unicodedata

print (unicodedata.bidirectional(u'\u0660'))
```

**输出:**

```
AN

```

*   **unicodedata.normalize(form, unistr)**
    This function returns the normal form for the Unicode string unistr. Valid values for form are ‘NFC’, ‘NFKC’, ‘NFD’, and ‘NFKD’.

    **示例:**

    ```
    from unicodedata import normalize

    print ('%r' % normalize('NFD', u'\u00C7'))
    print ('%r' % normalize('NFC', u'C\u0327'))
    print ('%r' % normalize('NFKD', u'\u2460'))
    ```

    **输出:**

    ```
    u'C\u0327'
    u'\xc7'
    u'1'

    ```

    本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。