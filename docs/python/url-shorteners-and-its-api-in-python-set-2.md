# Python 中的网址缩写及其应用编程接口| Set-2

> 原文:[https://www . geesforgeks . org/URL-shorteners-and-its-API-in-python-set-2/](https://www.geeksforgeeks.org/url-shorteners-and-its-api-in-python-set-2/)

先决条件:[网址缩写及其应用编程接口|设置-1](https://www.geeksforgeeks.org/url-shorteners-and-its-api-in-python-set-1/)

让我们使用相同的`pyshorteners` 模块来讨论更多的网址缩写。

1.  **Bitly URL Shortener:** We have seen Bitly API implementation. Now let’s see how this module can be used to shorten a URL using Bitly Services.

    **缩短网址的代码:**

    ```
    from pyshorteners import Shortener

    ACCESS_TOKEN = '82e8156..e4e12c6'

    url = 'http://www.google.com'
    url_shortener = Shortener('Bitly', bitly_token = ACCESS_TOKEN)

    print ("Short URL is {}".format(url_shortener.short(url)))
    ```

    **输出:**
    ![](img/92dcb2126ac35c4cecc91e3b78a369c2.png)

    **扩展网址的代码:**

    ```
    from pyshorteners import Shortener
    ACCESS_TOKEN = '82e8156...c1dce4e12c6'

    url = 'http://bit.ly/2OGRcfW'
    url_expander = Shortener('Bitly', bitly_token = ACCESS_TOKEN)

    print ("Long URL is {}".format(url_expander.expand(url)))
    ```

    **输出:**
    ![](img/e0680e94439807ecff9343f6f8e2eed6.png)

2.  **Adf.ly 网址缩短器:**这是网址缩短服务，根据访问您的缩短网址的访问者数量付费。您需要注册并创建一个应用编程接口密钥才能使用该服务。
    1.  您将在 Adf.ly 网页的右上角获得注册链接。有一个选项可以创建任何一种类型的帐户:创建帐户以缩短网址并赚钱，或者创建帐户并付费以在广告网页上宣传您的网站。
    2.  一旦您注册并确认您的电子邮件地址，您将被重定向到登录页面。
    3.  成功登录后，你的账户仪表盘会打开，你会看到一个选项**工具**。
    4.  Under **Tools** page, you will get your client id and API Key.

        **注意:**会有一条消息，**你的 API 访问当前被禁用。点击此处启用**。
        ![](img/84d9382309a732bb4b9ae608412623f7.png)

        ![](img/adcc63fbe7930d14382d13ac8119a5b1.png)

        **缩短网址的代码:**

        ```
        from pyshorteners import Shortener

        # uid means User Id and key means API Key.
        url = 'http://www.google.com'

        url_shortener = Shortener('Adfly',
                                  uid ='20727891',
                                  key ='b8de8e0...5a2381241c',
                                  type ='int')

        print ("Short URL is {}".format(url_shortener.short(url)))
        ```

        **输出:**
        ![](img/9652ffc81d57aa137bf5be5401499696.png)

3.  **Osdb URL Shortener:** This is another simple URL shortening service. You don’t need an API Key to use this. Just type the url and see the magic. This site does not provide features like tracking the visitors on the shortened URL.

    **缩短网址的代码:**

    ```
    from pyshorteners import Shortener

    url = 'http://www.google.com'

    url_shortener = Shortener('Osdb')

    print ("SHORT URL is {}".format(url_shortener.short(url)))
    ```

    **输出:**
    ![](img/86af84e01d4f4b7deef5dda5c7f48fcd.png)

4.  **da.gd URL Shortener:** This URL shortening service provides you the option to customise the shorten URL just like Bitly.

    **缩短网址的代码:**

    ```
    from pyshorteners import Shortener

    url = 'http://www.google.com'

    url_shortener = Shortener('Dagd')

    print ("Short URL is {}".format(url_shortener.short(url)))
    ```

    **输出:**
    ![](img/636c2ffe52b98021f19c2881d5bdbc78.png)

**参考文献:**

*   https://pypi.org/project/pyshorteners/
*   https://adf.ly/