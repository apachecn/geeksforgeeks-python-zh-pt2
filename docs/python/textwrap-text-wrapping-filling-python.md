# 文本换行–Python 中的文本换行和填充

> 原文:[https://www . geesforgeks . org/text wrap-text-wrap-filling-python/](https://www.geeksforgeeks.org/textwrap-text-wrapping-filling-python/)

textwrap 模块可用于纯文本的换行和格式化。该模块通过调整输入段落中的换行符来设置文本格式。

TextWrapper 实例属性(以及构造函数的关键字参数)如下:

*   **宽度:**这是指包裹线允许的最大长度。它的默认值设置为 70。
*   **expand _ tab:**默认值为真。如果该值等于 true，则使用此方法将示例输入中的所有制表符扩展为空格。
*   **tabsize:** 默认值为 8。如果 expand _ tabs 的值为 TRUE，则此方法会根据当前列和给定的制表符大小，将文本中的所有制表符扩展为零或更多空格。
*   **replace _ 空白:**默认值为真。如果该值为真，则在制表符扩展之后但在换行之前，wrap()方法将每个空白字符替换为一个空格。这些空白字符被替换:制表符、换行符、垂直制表符、换行符和回车符(' \t\n\v\f\r ')。
*   **drop _ 空白:**默认值为真。如果该值设置为真，则每行开头和结尾(换行后但缩进前)的空格将被删除。
*   **initial_indent:** 默认值设置为“”。此方法将给定的字符串添加到包装输出的第一行。
*   **后续 _ 缩进:**默认值设置为“”。此方法将给定字符串添加到除第一行之外的所有包装输出行的前面。
*   **占位符:**默认值设置为“[……]”。如果字符串被截断，此方法会在输出文本的末尾追加该字符串。
*   **最大行数:**默认值为无。如果该值不是“无”，则输出文本最多包含 max_lines 行，在输出的末尾有一个占位符。
*   **break _ long _ word:**默认值为真。如果为真，则超过宽度的单词将被断开，以适合给定宽度的每一行。如果为 FALSE，长单词将不会被打断，并将被自己放在一行上，以最大限度地减少超出宽度的量。
*   **break _ on _ 连字符:**默认值设置为真。如果该值等于“真”，则在复合词中连字符后的空格和右方出现换行。如果该值等于 FALSE，则换行符仅出现在空白区域，但是如果您想要真正不安全的单词，则需要将 break_long_words 设置为 FALSE。

**Textwrap 模块提供的功能:**

1.  **textwrap.wrap(text, width=70, **kwargs)**: This function wraps the input paragraph such that each line in the paragraph is at most width characters long. The wrap method returns a list of output lines. The returned list is empty if the wrapped output has no content. Default width is taken as 70.

    ```py
    import textwrap

    value = """This function wraps the input paragraph such that each line
    in the paragraph is at most width characters long. The wrap method
    returns a list of output lines. The returned list
    is empty if the wrapped
    output has no content."""

    # Wrap this text.
    wrapper = textwrap.TextWrapper(width=50)

    word_list = wrapper.wrap(text=value)

    # Print each line.
    for element in word_list:
        print(element)
    ```

    **输出:**

    ```py
    This function wraps the input paragraph such that
    each line in the paragraph is at most width
    characters long. The wrap method returns a list of
    output lines. The returned list is empty if the
    wrapped output has no content.

    ```

2.  **textwrap.fill(text, width=70, **kwargs):** The fill() convenience function works similar to textwrap.wrap except it returns the data joined into a single, newline-separated string. This function wraps the input single paragraph in text, and returns a single string containing the wrapped paragraph.

    ```py
    import textwrap

    value = """This function returns the answer as STRING and not LIST."""

    # Wrap this text.
    wrapper = textwrap.TextWrapper(width=50)

    string = wrapper.fill(text=value)

    print (string)
    ```

    **输出:**

    ```py
    This function returns the answer as STRING and not LIST.

    ```

3.  **textwrap.dedent(text)**: This function is used to remove any common leading whitespace from every line in the input text. This allows to use docstrings or embedded multi-line strings line up with the left edge of the display, while removing the formatting of the code itself.

    **示例:**

    ```py
    import textwrap

    wrapper = textwrap.TextWrapper(width=50)

    s = '''\
        hello
          world
        '''
    print(repr(s)) # prints '    hello\n      world\n    '

    text = textwrap.dedent(s)
    print(repr(text)) # prints 'hello\n  world\n'
    ```

    **输出:**

    ```py
    '    hello\n      world\n    '
    'hello\n  world\n'

    ```

4.  **textwrap.shorten(text, width, **kwargs)**: This function truncates the input string so that the length of the string becomes equal to the given width. At first, all the whitespaces are collapsed in the string by removing the whitespaces with a single space. If the modified string fits in the given string, then it is returned otherwise, the characters from the end are dropped so that the remaining words plus the placeholder fit within width.

    ```py
    import textwrap

    sample_text = """This function wraps the input paragraph such that each line
    n the paragraph is at most width characters long. The wrap method
    returns a list of output lines. The returned list
    is empty if the wrapped
    output has no content."""

    wrapper = textwrap.TextWrapper(width=50)

    dedented_text = textwrap.dedent(text=sample_text)
    original = wrapper.fill(text=dedented_text)

    print('Original:\n')
    print(original)

    shortened = textwrap.shorten(text=original, width=100)
    shortened_wrapped = wrapper.fill(text=shortened)

    print('\nShortened:\n')
    print(shortened_wrapped)
    ```

    **输出:**

    ```py
    Original:

    This function wraps the input paragraph such that
    each line n the paragraph is at most width
    characters long. The wrap method returns a list of
    output lines. The returned list is empty if the
    wrapped output has no content.

    Shortened:

    This function wraps the input paragraph such that
    each line n the paragraph is at most width [...]

    ```

5.  **textwrap.indent(text, prefix, predicate=None)**: This function is used to add the given prefix to the beginning of the selected lines of the text. The predicate argument can be used to control which lines are indented.

    ```py
    import textwrap

    s = 'hello\n\n \nworld'
    s1 = textwrap.indent(text=s, prefix=' ')

    print (s1)
    print ("\n")

    s2 = textwrap.indent(text=s, prefix='+ ', predicate=lambda line: True)
    print (s2)
    ```

    **输出:**

    ```py
    hello

    world

    + hello
    + 
    +  
    + world

    ```

    本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。