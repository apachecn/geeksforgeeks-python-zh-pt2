# 基于 Python 中使用硒的像素方法滚动网页

> 原文:[https://www . geesforgeks . org/scroll-web-page-base-on-pixel-method-use-selenium in-python/](https://www.geeksforgeeks.org/scroll-web-page-base-on-pixel-method-using-selenium-in-python/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

如果现代网页滚动不再是显示的可见位置，滚动条可以帮助您在**垂直路线**中循环显示。它用来上下移动窗户。硒网络驱动现在不再需要滚动来执行移动，因为它操纵 DOM。但是在正面的网页中，人们一滚动到这些因素，这些因素就会显现出来。在这种情况下，滚动是必要的。

**要求:**

*   硒
*   您需要安装 chromedriver 并设置路径。 [**点击此处**](https://sites.google.com/a/chromium.org/chromedriver/downloads) 下载。

**分步方法:**

**步骤 1:** 导入所需模块

## 蟒蛇 3

```py
from selenium import webdriver
import time
from webdriver_manager.chrome import ChromeDriverManager

# create instance of Chrome webdriver
driver=webdriver.Chrome(ChromeDriverManager().install())
```

**第二步:**获取任意[网址](https://www.countries-ofthe-world.com/flags-of-the-world.html)。

## 蟒蛇 3

```py
from selenium import webdriver
import time
from webdriver_manager.chrome import ChromeDriverManager

# create instance of Chrome webdriver
driver=webdriver.Chrome(ChromeDriverManager().install())

#url
driver.get("https://www.countries-ofthe-world.com/flags-of-the-world.html")
```

**第三步:**最大化窗口。

## 蟒蛇 3

```py
driver.maximize_window()
```

**第 4 步:**基于像素滚动。

## 蟒蛇 3

```py
driver.execute_script("window.scrollBy(0,2000)","")
```

**以下是全部实现:**

## 蟒蛇 3

```py
from selenium import webdriver
import time
from webdriver_manager.chrome import ChromeDriverManager

# create instance of Chrome webdriver
driver=webdriver.Chrome(ChromeDriverManager().install())

#url
driver.get("https://www.countries-ofthe-world.com/flags-of-the-world.html")

#maximize window
driver.maximize_window()

#scroll by pixcel
driver.execute_script("window.scrollBy(0,2000)","")
time.sleep(4)
```

**输出:**

<video class="wp-video-shortcode" id="video-526432-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201214134716/d.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201214134716/d.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201214134716/d.mp4)</video>