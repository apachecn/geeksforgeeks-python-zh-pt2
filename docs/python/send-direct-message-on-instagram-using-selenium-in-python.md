# 使用 Python 中的硒在 Instagram 上直接发送消息

> 原文:[https://www . geesforgeks . org/send-direct-message-on-insta gram-use-selenium in-python/](https://www.geeksforgeeks.org/send-direct-message-on-instagram-using-selenium-in-python/)

在本文中，我们将学习如何在 Instagram 上向用户发送直接消息，而无需任何手动操作。我们将使用硒模块来完成这项任务。

### 要求:

1.  Chrome 浏览器的 Chrome 驱动([https://chromedriver.chromium.org/](https://chromedriver.chromium.org/))或火狐的 Gecko 驱动([https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases))
2.  硒包。要安装此软件，请在终端中键入以下命令。

```
pip install selenium

```

**注意:**更多信息请参考[如何在 Python 中安装 Selenium](https://www.geeksforgeeks.org/how-to-install-selenium-in-python/)

**进场:**

**第一步:**导入模块，输入登录信息以及您想要发送消息的用户的用户名。

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import selenium.common.exceptions
import time
import random

# Login Credentials
username = input('Enter your Username ')
password = input('Enter your Password ')
url = 'https://instagram.com/' + input('Enter username of user whome you want to send message')
```

**第二步:**功能初始化火狐或者 chrome 会话。您可能需要添加 web 驱动程序的路径。Chrome 功能，就看你的安装了。

## 蟒蛇 3

```
def path():
        global chrome

        # starts a new chrome session
        chrome = webdriver.Chrome() # Add path if required
```

**第三步:**功能输入页面的网址

## 蟒蛇 3

```
def url_name(url):
  chrome.get(url)

  # adjust sleep if you want
  time.sleep(4)
```

**步骤 4:** 登录 Instagram 的功能

## 蟒蛇 3

```
def login(username, your_password):
    log_but = chrome.find_element_by_class_name("L3NKy")
    time.sleep(2)
    log_but.click()
    time.sleep(4)

    # finds the username box
    usern = chrome.find_element_by_name("username")

    # sends the entered username
    usern.send_keys(username)

    # finds the password box
    passw = chrome.find_element_by_name("password")

    # sends the entered password
    passw.send_keys(your_password)

    # press enter after sending password
    passw.send_keys(Keys.RETURN)
    time.sleep(5.5)

    # Finding Not Now button
    notk = chrome.find_element_by_class_name("yWX7d") 
    notk.click()
    time.sleep(3)
```

**第五步:**在用户档案页面找到消息按钮，然后向用户发送随机消息

## 蟒蛇 3

```
def send_message():

    # Find message button
    message = chrome.find_element_by_class_name('_862NM ')
    message.click()
    time.sleep(2)
    chrome.find_element_by_class_name('HoLwm ').click()
    time.sleep(1)
    l = ['hello', 'Hi', 'How are You', 'Hey', 'Bro whats up']
    for x in range(10):
        mbox = chrome.find_element_by_tag_name('textarea')
        mbox.send_keys(random.choice(l))
        mbox.send_keys(Keys.RETURN)
        time.sleep(1.2)
```

**步骤 6:** 调用函数

## 蟒蛇 3

```
path()
time.sleep(1)
url_name(url)
login(username, password)
send_message()
chrome.close()
```

就这样！该脚本将自动向您所爱的人发送消息。您可以通过修改这个脚本做很多事情，比如安排自动消息、向批量用户发送消息等等。

**输出:**

<video class="wp-video-shortcode" id="video-505746-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201028214041/WhatsApp-Video-2020-10-28-at-8.54.39-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201028214041/WhatsApp-Video-2020-10-28-at-8.54.39-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201028214041/WhatsApp-Video-2020-10-28-at-8.54.39-PM.mp4)</video>