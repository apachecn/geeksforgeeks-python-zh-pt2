# 硒蟒专用键

> 原文:[https://www . geesforgeks . org/special-key-in-selenium-python/](https://www.geeksforgeeks.org/special-keys-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。Special Keys 是 Selenium 在 python 中的专属功能，允许通过键盘按键，比如 ctrl+f，或者 shift+c+v 等。类 Selenium . web driver . common . Keys . Keys 处理 Selenium Python 中的所有 key。它包含了在 Selenium Python 中可以使用的大量关键方法。

## 如何在 Selenium Python 中使用特殊键

为了演示，特殊键，让我们使用硒 Python 中动作链的键向上方法。这个机器人访问 https://www.geeksforgeeks.org/，按 ctrl+f 打开搜索栏。
**程序–**

## 蟒蛇 3

```py
# import webdriver
from selenium import webdriver

# import Action chains
from selenium.webdriver.common.action_chains import ActionChains

# import KEYS
from selenium.webdriver.common.keys import Keys

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# create action chain object
action = ActionChains(driver)

# perform the operation
action.key_down(Keys.CONTROL).send_keys('F').key_up(Keys.CONTROL).perform()
```

**输出–**

![action-chain-method-Selelnium-python](img/783b48d0f978e4f1c9472207ff4ca17f.png)

## 特殊键

Selenium Python 中可以使用的各种键有–

<figure class="table">

| 注意缺陷障碍 (Attention Deficit Disorder) | 中高音 | 向下箭头 |
| 向左箭头 | 向右箭头 | 向上箭头 |
| 退格键 | 后退 _ 空间 | 取消 |
| 清楚的 | 命令 | 控制 |
| 小数 | 删除 | 划分 |
| 向下 | 结束 | 进入 |
| 等于 | 逃跑 | 子一代 |
| F10 | F11 | F12 |
| 第二子代 | 第三子代 | 法乐四联症 |
| F5 | F6 | F7 |
| F8 | F9 | 帮助 |
| 家 | 插入 | 左边的 |
| 左 _ALT | 左 _ 控制 | 左移位 |
| 自指的 | 多样地 | 空 |
| NUMPAD0 | NUMPAD1 | NUMPAD2 |
| NUMPAD3 | NUMPAD4 | NUMPAD5 |
| NUMPAD6 | NUMPAD7 | NUMPAD8 |
| NUMPAD9 | 向下翻页 | 向上翻页 |
| 中止 | 返回 | 正确 |
| 分号 | 分离器 | 变化 |
| 空间 | 减去 | 标签 |

</figure>