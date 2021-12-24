# 释放方法–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/release-method-action-chains-in-selenium-python/](https://www.geeksforgeeks.org/release-method-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`release`方法展开。release 方法用于释放元素上的鼠标按钮。

**语法–**

```
release(on_element=None)
```

**Args –**`on_element` – The element to mouse up. If None, releases on current mouse position.

**示例–**

```
<input type ="text" name ="passwd" id ="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
```

现在，您可以使用发布方法作为行动链，如下所示–

```
action.click(on_element=element)
action.release(element)

```

## 硒 Python 中如何使用释放动作链方法？

演示一下，硒蟒的`release`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

**程序–**

```
# import webdriver
from selenium import webdriver

# import Action chains 
from selenium.webdriver.common.action_chains import ActionChains

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element 
element = driver.find_element_by_link_text("Courses")

# create action chain object
action = ActionChains(driver)

# click the item
action.click(on_element = element)

# release the item
action.release(on_element = element)

# perform the operation
action.perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)