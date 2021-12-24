# 使用 Python 抓取天气数据获取邮件上的雨伞提醒

> 原文:[https://www . geesforgeks . org/scratch-weather-data-use-python-to-get-保护伞-邮件提醒/](https://www.geeksforgeeks.org/scraping-weather-data-using-python-to-get-umbrella-reminder-on-email/)

在本文中，我们将看到如何使用 Python 刮取天气数据，并在电子邮件上获得提醒。如果天气状况是阴雨天，这个程序会给你的邮件发送一个“雨伞提醒”，提醒你出门前带上雨伞。我们将使用 bs4 从谷歌抓取天气信息，并在 python 中请求库。

然后根据天气情况，我们将使用 smtplib 库发送电子邮件。为了每天在指定的时间运行这个程序，我们将使用 python 中的时间表库。

## **所需模块**

*   [**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)T4:美人汤(bs4)是一个从 HTML 和 XML 文件中提取数据的 Python 库。要安装此库，请在 IDE/终端中键入以下命令。

```py
pip install bs4
```

*   [**请求:**](https://www.geeksforgeeks.org/python-requests-tutorial/) 这个库可以让你非常轻松的发送 HTTP/1.1 请求。要安装此库，请在 IDE/终端中键入以下命令。

```py
pip install requests
```

*   [**smtplib:**](https://www.geeksforgeeks.org/send-mail-attachment-gmail-account-using-python/) smtplib 是一个定义了 SMTP 客户端会话对象的 Python 模块，可以用来向互联网上的任何机器发送邮件。要安装此库，请在集成开发环境/终端中键入以下命令。

```py
pip install smtplib
```

*   **日程:**日程是一个 Python 库，用于在一天中的特定时间或一周中的特定日期安排任务。要安装此库，请在集成开发环境/终端中键入以下命令。

```py
pip install schedule
```

## **分步实施**

**步骤 1:** 导入计划、smtplib、请求和 bs4 库。

## 蟒蛇 3

```py
import schedule
import smtplib   
import requests
from bs4 import BeautifulSoup
```

**步骤 2:** 用指定的城市名创建一个网址，并绕过该网址创建一个请求实例。

## 蟒 3

```py
city = "Hyderabad"
url = "https://www.google.com/search?q=" + "weather" + city
html = requests.get(url).content
```

**步骤 3:** 将检索到的 HTML 文档传递到美丽的汤，它将返回一个去除了 HTML 标签和元数据的字符串。使用 find 函数，我们将检索所有必要的数据。

## 蟒 3

```py
soup = BeautifulSoup(html,
                     'html.parser')
temperature = soup.find(
  'div', attrs={'class': 'BNeawe iBp4i AP7Wnd'}).text
time_sky = soup.find(
  'div', attrs={'class': 'BNeawe tAd8D AP7Wnd'}).text

# formatting data
sky = time_sky.split('\n')[1]
```

**第四步:**如果天气情况变成阴雨天，这个程序会给收件人发送一封带有“雨伞提醒”信息的邮件。为了封装一个 SMTP 连接，我创建了一个参数为“smtp.gmail.com”和 587 的 SMTP 对象。创建 SMTP 对象后，您可以使用您的电子邮件地址和密码登录。

**注意:**不同的网站使用不同的端口号。在本文中，我们使用 Gmail 帐户发送电子邮件。这里使用的端口号是“587”。如果你想使用 Gmail 以外的网站发送邮件，你需要获取相应的信息。

## 蟒 3

```py
if sky == "Rainy" or sky == "Rain And Snow" or sky == "Showers" or sky == "Haze" or sky == "Cloudy":
    smtp_object = smtplib.SMTP('smtp.gmail.com', 587)
```