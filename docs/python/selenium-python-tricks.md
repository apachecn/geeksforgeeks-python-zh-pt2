# 硒蟒招数

> 原文:[https://www.geeksforgeeks.org/selenium-python-tricks/](https://www.geeksforgeeks.org/selenium-python-tricks/)

[**Selenium**](https://www.geeksforgeeks.org/browser-automation-using-selenium/):Selenium Python 绑定提供了一个便捷的 API，可以像火狐、Chrome 等一样访问 Selenium Web Driver。
**什么是网络驱动？**
Selenium WebDriver 是一款自动化测试工具。当我说自动化时，它意味着自动化用 Selenium 编写的测试脚本。
**网络驱动安装**

```py
Chrome:    https://sites.google.com/a/chromium.org/chromedriver/downloads
```

**库导入**

```py
from selenium import webdriver
import time
```

(I)硒库:
–用于自动化
–控制网络驱动程序
–执行诸如–元素点击、刷新页面、转到网站链接等动作
(ii)时间库:
-用于使用睡眠功能，因为硒仅在页面的所有元素都被加载时才起作用。
**小技巧 1:如何增加网站浏览量？**
#注意:这并不适用于所有网站，比如 youtube。
我们将学习的是在特定的时间间隔后一次又一次地刷新网页。

## 计算机编程语言

```py
#!/usr / bin / env python
from selenium import webdriver
import time

# set webdriver path here it may vary
browser = webdriver.Chrome(executable_path ="C:\Program Files (x86)\Google\Chrome\chromedriver.exe")

website_URL ="https://www.google.co.in/"
browser.get(website_URL)

# After how many seconds you want to refresh the webpage
# Few website count view if you stay there
# for a particular time
# you have to figure that out
refreshrate = int(15)

# This would keep running until you stop the compiler.
while True:
    time.sleep(refreshrate)
    browser.refresh()
```

**小技巧 2:如何登录网站，这里我们以 Zomato**
为例

## 计算机编程语言

```py
from selenium import webdriver
# For using sleep function because selenium
# works only when all the elements of the
# page is loaded.
import time
# webdriver path set
browser = webdriver.Chrome("C:\Program Files (x86)\Google\Chrome\chromedriver.exe")

# To maximize the browser window
browser.maximize_window()

# zomato link set
browser.get('https://www.zomato.com / ncr')

time.sleep(3)
# Enter your user name and password here.
username = "test"
password = "test"

# signin element clicked
browser.find_element_by_xpath("//a[@id ='signin-link']").click()
time.sleep(2)

# Login clicked
browser.find_element_by_xpath("//a[@id ='login-email']").click()

# username send
a = browser.find_element_by_xpath("//input[@id ='ld-email']")
a.send_keys(username)

# password send
b = browser.find_element_by_xpath("//input[@id ='ld-password']")
b.send_keys(password)

# submit button clicked
browser.find_element_by_xpath("//input[@id ='ld-submit-global']").click()

print('Login Successful')
browser.close()
```

**Trick3: Instagram 登录自动化脚本。**
我们知道 Instagram 将从 2020 年 6 月 29 日起停止其 Legacy API。
所以学习自动化脚本可能是一个更好的主意。

## 蟒蛇 3

```py
from selenium import webdriver
# sleep() function is required because
# selenium needs a page to be fully loaded first
# otherwise errors may occur
from time import sleep
# Usage sleep(x) Where x is time in seconds and
# may vary according to your connection

# I have made class so that extra methods can be added later on
# if required
class instagramBot:
    def __init__(self, username, password):
        # these lines will help if someone faces issues like
        # chrome closes after execution
        self.opts = webdriver.ChromeOptions()
        self.opts.add_experimental_option("detach", True)
        self.driver  = webdriver.Chrome(options=self.opts)

        # Username and password
        self.username = username
        self.password = password

        # Opens Instagram login page
        self.driver.get("https://instagram.com")
        sleep(2) # 1 Second Wait

        # Automatically enters your username and
        # password to instagram's username field
        self.driver.find_element_by_xpath("//input[@name = 'username']").send_keys(self.username)
        self.driver.find_element_by_xpath("//input[@name = 'password']").send_keys(self.password)

        # Clicks on Log In Button
        self.driver.find_element_by_xpath("//div[contains(text(), 'Log In')]").click()
        sleep(2)

        # Bonus: Automatically clicks on 'Not Now'
        # when Instagram asks to show notifications
        self.driver.find_element_by_xpath("//button[contains(text(), 'Not Now')]").click()

# Testing Your Code
instagramBot('Sample Username','Sample Password')
```