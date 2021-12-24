# 刮网不堵塞

> 原文:[https://www . geeksforgeeks . org/web-刮擦-不被阻止/](https://www.geeksforgeeks.org/web-scraping-without-getting-blocked/)

**网页抓取**是指使用 HTTP 协议或网页浏览器从网站抓取/提取数据的过程。这个过程可以是手动的，也可以使用机器人或网络爬虫自动完成。此外，还有一种误解认为网页抓取是非法的，事实是它是完全合法的，除非您试图访问非公共数据(公众无法访问的数据，如登录凭据)。

当你浏览小网站时，你可能不会遇到任何问题。但是当你尝试在一些大网站甚至谷歌上进行网页抓取时，你可能会发现你的请求被忽略，甚至你的知识产权被屏蔽。

在本文中，我们将向您建议一些最佳实践，在从网络上抓取数据时可以遵循这些实践，而不会使您自己(您的 IP)被阻止。

### **方法 1:使用旋转代理**

如果您从同一个 IP 发送重复的请求，网站所有者可以检测到您的足迹，并可能通过检查服务器日志文件来阻止您的网页抓取器。为了避免这种情况，您可以使用旋转代理。

一个*旋转代理*是一个代理服务器，它从存储在代理池中的一组代理中分配一个新的 IP 地址。我们需要使用代理和轮换我们的 IP 地址，以避免被网站所有者发现。我们只需要编写一个脚本，让我们使用池中的任何 IP 地址，并让我们使用相同的 IP 请求。使用旋转 IPs 概念的目的是让它看起来你不是机器人，而是人类，从世界不同地方访问不同位置的数据。

第一步包括找到代理:有许多网站通过互联网提供免费代理。其中之一就是[https://free-proxy-list.net/](https://free-proxy-list.net/)。

**这里使用的代理:**

*   IP:180.179.98.22
*   Port: 3128

类似地，我们可以从[https://free-proxy-list.net/](https://free-proxy-list.net/)手动或使用刮刀自动获取代理列表。

**程序:**

## 蟒蛇

```
import requests

# use to parse html text
from lxml.html import fromstring 
from itertools import cycle
import traceback

def to_get_proxies():
    # website to get free proxies
    url = 'https://free-proxy-list.net/' 

    response = requests.get(url)

    parser = fromstring(response.text)
    # using a set to avoid duplicate IP entries.
    proxies = set() 

    for i in parser.xpath('//tbody/tr')[:10]:

        # to check if the corresponding IP is of type HTTPS
        if i.xpath('.//td[7][contains(text(),"yes")]'):

            # Grabbing IP and corresponding PORT
            proxy = ":".join([i.xpath('.//td[1]/text()')[0],
                              i.xpath('.//td[2]/text()')[0]])

            proxies.add(proxy)
        return proxies
```

**输出:**

> 代理={'160.16.77.108:3128 '，' 20.195.17.90:3128 '，' 14.225.5.68:80 '，' 158.46.127.222:52574 '，' 159.192.130.233:8080 '，' 124.106.224.5:8080 '，' 51.79.157

现在我们有了代理 IP 地址列表。我们将使用循环方法旋转 IP。

**程序:**

## 蟒蛇

```
proxies = to_get_proxies()

# to rotate through the list of IPs
proxyPool = cycle(proxies) 

# insert the url of the website you want to scrape.
url = '' 

for i in range(1, 11):

    # Get a proxy from the pool
    proxy = next(proxyPool)
    print("Request #%d" % i)

    try:
        response = requests.get(url, proxies={"http": proxy, "https": proxy})
        print(response.json())

    except:

        # One has to try the entire process as most
        # free proxies will get connection errors
        # We will just skip retries.
    print("Skipping.  Connection error")
```

**输出:**

```
Request #1
Skipping.  Connection error
Request #2
Skipping.  Connection error
Request #3
Skipping.  Connection error
Request #4
Skipping.  Connection error
Request #5
Skipping.  Connection error
Request #6
Skipping.  Connection error
Request #7
Skipping.  Connection error
Request #8
Skipping.  Connection error
Request #9
Skipping.  Connection error
Request #10
Skipping.  Connection error
```

**使用代理轮换时要记住的事项:**

*   **Avoid using proxy IP addresses arranged in a certain order** :

如果请求来自相似的子网或连续不断，任何防刮插件都会检测到刮擦器。例如:132.12.12.1、132.12.12.2、132.12.12.3、132.12.12.4 都在同一个序列中。你应该避免使用像这样的入侵防御系统，因为大多数防刮插件都是设计来阻止在某个范围内或某个特定顺序的入侵防御系统的。

*   **Use payment agent:**

自由代理人往往很快就会消亡。此外，免费代理在互联网上被过度使用，并且已经被大多数防刮工具列入黑名单。此外，如果您使用免费代理来防止刮擦过程的中断，您可以自动化该过程。

### 方法二:使用谷歌云平台的 IPs

结合将用户代理改为谷歌机器人，使用谷歌云功能作为你的网页抓取器的托管平台可能会有所帮助。网站会显示你是一个谷歌机器人，而不是一个刮刀。谷歌机器人(GoogleBot)是由谷歌设计的网络爬虫，每隔几秒钟访问一次网站，并从网站收集文档，为谷歌搜索引擎建立一个可搜索的索引。由于大多数网站不屏蔽谷歌机器人，如果你使用谷歌云功能作为托管平台，你的爬虫不被屏蔽的可能性更高。

### 方法 3:缓慢刮网

当我们使用自动刮擦器刮擦数据时，刮擦器以不人道的速度刮擦数据，这很容易被防刮擦器插件检测到。通过给我们的刮板添加随机延迟和动作，我们可以使它像一个人，所以网站所有者不会察觉到它。发送请求太快会让所有用户的网站崩溃。把请求的数量控制在一个限度之内，这样你就不会让网站服务器过载，让你的 IP 被屏蔽。

此外，您可以通过使用站点的 robot.txt 来检查两个请求之间的延迟应该是多少。通常，您可以在 robot.txt 页面上找到一个爬网延迟字段，该字段确切地告诉请求之间的延迟应该是多少，以避免被识别为爬网程序。

### 方法 4:在不同的时间刮网

在不同的时间登录同一个网站也会减少你的足迹。例如:如果你每天早上 8:00 开始刮，那么接下来几天在早上 8:20 或 8:25 开始刮。每天在开始时间增加几分钟可以证明对逃避爬虫的检测算法非常有帮助。

### 方法 5:使用验证码解决服务

大多数网站使用验证码来检测机器人流量。我们可以使用验证码解决服务来轻松绕过这一额外的安全层。有一些验证码解决服务，比如:

*   Anti-verification code

需要记住的一点是，这些服务需要额外的费用，可能会增加从网站上抓取数据的时间。因此，如果您选择使用验证码解决服务，应该考虑您可能必须承担的额外时间和费用。

### 方法 6:从谷歌缓存中抓取:

为了从那些数据变化不频繁的网站上抓取数据，我们可以使用谷歌缓存。谷歌保存了一些网站的缓存副本。您可以向其缓存的数据发出请求，而不是向原始数据发出请求。为了访问任何网页上的缓存，请在此 URL 前面添加网站的 URL

**语法:**

> http://webcache.googleusercontent.com/search?q =缓存:URL(你想刮的网站的 URL)。

### 方法 7:用户代理

它是一个字符串，允许服务器和对等方识别应用程序或请求用户操作系统的版本。如果不是来自主要浏览器，一些网站会阻止用户代理。如果没有设置，许多网站将不允许访问内容。你可以通过两种方式找到你的用户代理:

*   Type–"What is my user agent on Google?"
*   You can find the user agent string- [http://www.whatsmyuseragent.com/](http://www.whatsmyuseragent.com/) on this website.

这个问题的解决方案是，您需要创建一个用户代理列表，或者使用像 fake-useragent(python)这样的库。

### 方法 8:无头浏览器

网站会根据您请求数据的浏览器来更改其内容。抓取某些网站时的问题是，内容是由 JavaScript 代码呈现的(抓取时)，而不是 HTML。要刮擦这样的网站，你可能需要部署自己的自定义无头浏览器。像 Selenium 和 Puppeteer 这样的自动化浏览器也可以用来控制和抓取这样的动态网站。这是很大的努力，但这是最有效的方法。