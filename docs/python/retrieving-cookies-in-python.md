# 在 Python 中检索 Cookies】

> 原文:[https://www.geeksforgeeks.org/retrieving-cookies-in-python/](https://www.geeksforgeeks.org/retrieving-cookies-in-python/)

在 Python 中检索 cookies 可以通过使用[请求库](https://www.geeksforgeeks.org/python-requests-tutorial/)来完成。请求库是 Python 的一个组成部分，用于向指定的网址发出 HTTP 请求。下面的代码显示了不同的方法:

**1。通过请求会话:**

```
# import the requests library
import requests

# initialize a session
session = requests.Session()

# send a get request to the server
response = session.get('http://google.com')

# print the response dictionary
print(session.cookies.get_dict())
```

 **输出:**

> { ' 1p _ jar ':2020-04-30-07 '，' NID ':203 = gilzlnytcsgjmtv-ml 49 xgkqx4 nacmgfzi 56 sbq 3 TSD 9 udql 7 ewz 6 KC _ guqpsk-xsdica 8 elqhjshgrpwbbfxxcgl _ G5 JD 0 gzdyhco-qalszm 4 ziqieilbbtp _ tdogrquoi 0 D2 hsnerxmkljluhia 3 qgllnm

**2。通过向服务器请求 cookies 列表:**

```
import requests

r = requests.get('http://google.com')

for c in r.cookies:
    print(c.name +"==>>", c.value)
```

**输出:**

> 1P_JAR==>> 2020-04-30-07
> 
> NID = = > > 203 = yvfckkiehs4 svptv8 jw 6 migeu 54 iln 8v _ 1 qzrxmou7 zdj 74 qzdw 69 E3 a 38 ksp-gre5xlm r 40 ozrhtfxkxm4-iatmidhu4 wmvowhes1 zeli 8 h8 kqlcmblcxcxcxcuht 07 qqq2mqc-ppbyxchtoc 7 idvc9 rwd 2 kmnpdmr-yml 4