# 使用 Python 中的 Selenium 在 Google 中进行文本搜索

> 原文:[https://www . geesforgeks . org/text-search-in-Google-use-selenium-in-python/](https://www.geeksforgeeks.org/text-searching-in-google-using-selenium-in-python/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

在本文中，我们将看到如何自动化我们的浏览器。我们只需选择单词/句子并说出搜索，单词/句子就会被自动搜索并为您提供准确的结果。

**要求:**

*   [pyautogui](https://www.geeksforgeeks.org/mouse-keyboard-automation-using-python/) : PyAutogui 是一个面向人类的跨平台 GUI 自动化 Python 模块。用于编程控制鼠标&键盘。
*   [selenium](https://www.geeksforgeeks.org/selenium-python-tutorial/) : Selenium 是通过程序控制网页浏览器，执行浏览器自动化的强大工具。
*   [语音 _ 识别](https://www.geeksforgeeks.org/python-convert-speech-to-text-and-text-to-speech/):语音识别是家庭自动化、人工智能等多个应用中使用的重要功能。
*   我们正在使用**chrome driver _ auto installer**，这样我们就可以看到搜索到的单词的意思。[在您的本地设备中安装 Chrome 最新版本]。

**分步方法:**

**步骤 1:** 导入所需模块

## 蟒蛇 3

```
# import module.

# Web browser Automation
from selenium import webdriver
from time import sleep 

# Support for chrome 
import chromedriver_autoinstaller 

# Invoking speech module
import speech_recognition as sr

# Support file for speech recognition
import pyttsx3

# Automating task
import pyautogui 
```

**第二步:**让我们调用语音识别模块，启动我们的内部扬声器，这样它就可以听到我们的声音作为输入，并可以启动这个过程。**我的文本**将我们的语音命令存储为文本。

## 计算机编程语言

```
r = sr.Recognizer() 
with sr.Microphone() as source2: 
    r.adjust_for_ambient_noise(source2, duration = 0.2) 
      audio2 = r.listen(source2)
    MyText = r.recognize_google(audio2) 
    MyText = str(MyText.lower())
```

**第三步:**选择并说出**后，用你的声音搜索**将启动该过程。使用 selenium 和 pyautogui 会自动获取该单词并给出适当的搜索结果。

## 蟒蛇 3

```
if MyText == "search":

    # Automates 'copy' internally
    pyautogui.hotkey('ctrl', 'c')

    chrome_options = webdriver.ChromeOptions()

    capabilities = {'browserName': 'chrome',
                    'javascriptEnabled': True}

    capabilities.update(chrome_options.to_capabilities())

    chromedriver_autoinstaller.install()

    # Invoking the chrome
    driver = webdriver.Chrome()

    # Adjusting the size of the window
    driver.set_window_size(1920, 1080)

    driver.implicitly_wait(10)

    driver.get("https://www.google.com/") 

    #Place where our selected word gets pasted
    driver.find_element_by_xpath(
      "/html/body//form[@role='search']/div[2]/div[1]//div[@class='a4bIc']/input[@role='combobox']")
           .send_keys(pyautogui.hotkey('ctrl', 'v'))
```

**以下是完整实现:**

## 计算机编程语言

```
from selenium import webdriver 
from time import sleep 
import chromedriver_autoinstaller
import speech_recognition as sr 
import pyttsx3 
import pyautogui

while(True):

    try:
        r = sr.Recognizer() 
        with sr.Microphone() as source2: 

            r.adjust_for_ambient_noise(source2, duration = 0.2) 
              audio2 = r.listen(source2) 
            MyText = r.recognize_google(audio2) 
            MyText = str(MyText.lower())

        if MyText == "search":
              pyautogui.hotkey('ctrl', 'c')
              chrome_options = webdriver.ChromeOptions()
            capabilities = {'browserName': 'chrome', 'javascriptEnabled': True}
            capabilities.update(chrome_options.to_capabilities())
            chromedriver_autoinstaller.install()
            driver = webdriver.Chrome()
            driver.set_window_size(1920, 1080)
            driver.implicitly_wait(10)
            driver.get("https://www.google.com/") 
            driver.find_element_by_xpath(
              "/html/body//form[@role='search']/div[2]/div[1]//div[@class='a4bIc']/input[@role='combobox']")
              .send_keys(pyautogui.hotkey('ctrl', 'v'))

        elif MyText == "stop":
            break

    except Exception as e:

        pyautogui.press('enter')
```

***<u>演示:</u>***

<video class="wp-video-shortcode" id="video-537320-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201228181551/For_article.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201228181551/For_article.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201228181551/For_article.mp4)</video>