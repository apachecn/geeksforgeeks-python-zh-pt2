# Python | Whatsapp 献上生日

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-whatsapp-bot/生日快乐

你有没有希望在你的朋友生日时自动祝福他们，或者给你的朋友(或任何 Whastapp 联系人)发送一组消息！)在预先设定的时间自动发送，或者通过在 whatsapp 上发送成千上万条随机文本发送给你的朋友！使用浏览器自动化，你可以做所有的事情，甚至更多！
首先您必须安装这些:-
1) **硒的 Python 绑定(浏览器自动化软件)**

```py
pip install selenium
```

2) **Chrome 网络驱动**
从这里下载 Chrome 驱动:[Chrome 驱动下载页面](https://sites.google.com/a/chromium.org/chromedriver/downloads)(选择你的具体版本)

#### 机器人是怎么做到的

该脚本使用 PySelenium 包打开一个 Chrome 网络驱动程序窗口，在该窗口上完成所有任务。它检查当前日期和月份是否与 json 文件中的日期和月份匹配。如果是，则返回其“名称”属性，用于在 Whatsapp web 中查找对应的聊天(通过 [xpath](https://www.geeksforgeeks.org/introduction-to-xpath/) 查找)。该脚本然后模拟点击聊天，打开它，在聊天框中键入消息，并模拟点击发送按钮。

#### 什么是 JSON？

JSON 代表 JavaScript 对象符号。这是一种非常简单和轻便的数据存储方式。虽然它源于 JavaScript，但它是独立于语言的，在外观上类似于 Python 字典
查看[这篇](https://www.geeksforgeeks.org/javascript-json/)文章了解更多关于 JSON 的信息。
以下是执行情况

## 蟒蛇 3

```py
# get current date in required format
import datetime

# store the birthdates of your contacts
import json

from selenium import webdriver

# add a delay so that all elements of
# the webpage are loaded before proceeding
import time

# Global variable Do not use elsewhere
eleNM = None

# This function is just to return a
# string of the message required
def wish_birth(name):
    return "Happy Birthday " + name.split(" ")[0] + "!!"

# This function returns a list of values of some
# attribute based on conditions on two attributes from the JSON file.
# use to return names of contacts having their birthday on current date.
def getJsonData(file, attr_ret, attr1, attr2, attr_val1, attr_val2):

    # Load the file's data in 'data' variable
    data = json.load(file)
    retv =[]

    # If the attributes' value conditions are satisfied,
    # append the name into the list to be returned.
    for i in data:
        if(i[attr1]== attr_val1 and i[attr2]== attr_val2):
           retv.append(i[attr_ret])
    return retv

# Opening the JSON file (birthdays.json) in read only mode.
data_file = open("birthdays.json", "r")
namev =[]
print("Script Running")

# This will keep rerunning the part of
# the code from 'while True' to 'break'.
# use to keep waiting for the JSON function
# to return a non empty list.
# In practice, this function will keep rerunning at
# 11:59pm a day before the birthday and break out at 12:00am.
while True:
    try:
        # to get current date
        datt = datetime.datetime.now()
        namev = getJsonData(data_file, "name", "birth_month", "birth_date",
                                           str(datt.month), str(datt.day))

    except json.decoder.JSONDecodeError:
        continue
    if(namev !=[]):
        break

# ChromeOptions allows us use the userdata of chrome
# so that you don't have to sign in manually everytime.
chropt = webdriver.ChromeOptions()

# adding userdata argument to ChromeOptions object
chropt.add_argument("user-data-<LOCATION TO YOUR CHROME USER DATA>")

# Creating a Chrome webdriver object
driver = webdriver.Chrome(executable_path ="<LOCATION TO CHROME WEBDRIVER>",
                                                          options = chropt)
driver.get("https://web.whatsapp.com/")

# delay added to give time for all elements to load
time.sleep(10)

print(namev)

# Finds the chat of your contacts (as in the namev list)
for inp in namev:
    try:
        eleNM = driver.find_element_by_xpath('//span[@title ="{}"]'.format(inp))
    except Exception as ex:
        print(ex)
        continue
    # Simulates a mouse click on the element
    eleNM.click()

    while(True):
        # Finds the chat box element
        eleTF = driver.find_element_by_class_name("_13mgZ")
        # Writes the message(function call to wish_birth())
        eleTF.send_keys(wish_birth(inp))
        # Finds the Send button
        eleSND = driver.find_element_by_class_name("_3M-N-")
        # Simulates a click on it
        eleSND.click()
        break
```

**JSON 文件的样子**

```py
[
  {
    "name": "NAME1",
    "birth_month": "1",
    "birth_date": "12"
  },
  {
    "name": "NAME2",
    "birth_month": "5",
    "birth_date": "15"
  }

]
```