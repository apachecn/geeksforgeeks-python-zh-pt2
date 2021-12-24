# 使用 Python Selenium 登录极客博客

> 原文:[https://www . geesforgeks . org/sign-in-geesforgeks-using-python-selenium/](https://www.geeksforgeeks.org/sign-in-geeksforgeeks-using-python-selenium/)

**项目描述:**
在这里，我们要学习一个简单的如何通过硒登录***【GFG】***。Selenium 是一个免费工具，可以在不同的浏览器上自动试用。然后是一个简单的需求 id 和密码。

**要求:**

*   **Selenium –** [Selenium Python Introduction and Installation](https://www.geeksforgeeks.org/selenium-python-introduction-and-installation/)

    **设置步骤–**

    *   首先，使用 [***<u>链接</u>***](https://auth.geeksforgeeks.org/) 进入**极客网站。**
    *   然后通过紧急 ctrl + shift + i 或进入浏览器设置并手动点击调查细节来点击调查元素。
    *   然后导航到填写**电子邮件或用户名**的框，然后复制 x_path。
        T3】
    *   然后导航**密码**然后复制 x_path。
        T3】
    *   然后导航**登录**按钮，然后复制 x_path。
        T3】

    **实施:**

    ```py
    from selenium import webdriver
    from selenium.webdriver.common.keys import Keys
    import time

    # create instance of Chrome webdriver
    driver = webdriver.Chrome() 

    driver.get("https://auth.geeksforgeeks.org/")

    # find the element where we have to 
    # enter the xpath
    # fill user or mail id
    driver.find_element_by_xpath('//*[@id ="luser"]').send_keys('praveeny182')

    # find the element where we have to 
    # enter the xpath
    # fill password
    driver.find_element_by_xpath('//*[@id ="password"]').send_keys('xXXXXX')

    # find the element sign in 
    # request using xpath 
    # clicking on that element 
    driver.find_element_by_xpath('//*[@id ="Login"]/button').click()

    ```

    **输出–**
    你最终会在运行 selenium 的浏览器中登录到 geeksforgeeks。