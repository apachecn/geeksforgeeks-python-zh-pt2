# 秘密|生成安全随机数的 Python 模块

> 原文:[https://www . geesforgeks . org/secrets-python-module-generate-secure-random-numbers/](https://www.geeksforgeeks.org/secrets-python-module-generate-secure-random-numbers/)

机密模块用于生成随机数，以管理密码、帐户身份验证、安全令牌和相关机密等重要数据，这些数据具有很强的加密能力。该模块负责提供对最安全的随机性来源的访问。该模块存在于 **Python 3.6** 及以上版本中。

**随机数:阶级机密。系统随机**

这个类使用 os.urandom()函数从操作系统提供的源中生成随机数。

1.  **secrets.choice(sequence):** This function returns a randomly-chosen element from a non-empty sequence to manage a basic level of security.
    **Example 1 :** Generate a ten-character alphanumeric password.

    ```py
    import secrets
    import string

    alphabet = string.ascii_letters + string.digits
    password = ''.join(secrets.choice(alphabet) for i in range(10))

    print(password)
    ```

    **输出:**

    ```py
    'tmX47l1uo4'

    ```

    **示例 2 :** 生成十个字符的字母数字密码，至少包含一个小写字符、至少一个大写字符和至少三个数字。

    ```py
    import secrets
    import string

    alphabet = string.ascii_letters + string.digits
    while True:
        password = ''.join(secrets.choice(alphabet) for i in range(10))
        if (any(c.islower() for c in password) and any(c.isupper() 
        for c in password) and sum(c.isdigit() for c in password) >= 3):
            print(password)
            break
    ```

    **输出:**

    ```py
    Tx8LppU05Q

    ```

2.  **secrets.randbelow(n)**: This function returns a random integer in the range [0, n).

    ```py
    import secrets

    passwd = secrets.randbelow(20)
    print(passwd)
    ```

    **输出:**

    ```py
    2

    ```

3.  **secrets.randbits(k):** This function returns an int with k random bits.

    ```py
    import secrets

    passwd = secrets.randbits(7)
    print(passwd)
    ```

    **输出:**

    ```py
    61

    ```

**生成代币**

这个模块提供了几个为应用程序生成安全令牌的功能，如密码重置、难以猜测的网址等。

1.  **secrets.token_bytes([nbytes=None]) :** This function is responsible for generating a random byte string containing nbytes number of bytes. If no value is provided, a reasonable default is used.

    ```py
    import secrets

    token1 = secrets.token_bytes()
    token2 = secrets.token_bytes(10)

    print(token1)
    print(token2)
    ```

    **输出:**

    ```py
    b"\x86?\x85\xcf\x8ek8ud\x8a\x92\x8b>R\xc7\x89_\xc4x\xce'u]\x95\x0c\x05*?HG8\xfb"
    b'Dx\xe8\x7f\xc05\xdf\xe0\xf6\xe1'

    ```

2.  **secrets.token_hex([nbytes=None]) :** This function is responsible for generating a random text string in hexadecimal containing nbytes random bytes. If no value is provided, a reasonable default is used.

    ```py
    import secrets

    token1 = secrets.token_hex(16)
    token2 = secrets.token_hex(9)

    print(token1)
    print(token2)
    ```

    **输出:**

    ```py
    5d894a501c88fbe735c6ff496a6d3e51
    78baed9057e597dce4

    ```

3.  **secrets.token_urlsafe([nbytes=None]) :** This function is responsible for generating a random URL-safe text string containing nbytes random bytes. This is suitable for password recovery applications.
    **Example :** Generate a hard-to-guess temporary URL containing a security token.

    ```py
    import secrets

    url = 'https://mydomain.com/reset=' + secrets.token_urlsafe()
    print(url)
    ```

    **输出:**

    ```py
    https://mydomain.com/reset=GbOiFIvhMoqWsfaTQKbj8ydbo8G1lsMx1ECa6SXjb1s

    ```

    **令牌应该使用多少字节？**
    应该使用至少 32 字节的令牌来抵御暴力攻击。

**参考:** [官方 Python 文档](https://docs.python.org/3/library/secrets.html#module-secrets)
本文由 **Aditi Gupta** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。