# 使用 Python 向电报用户发送消息

> 原文:[https://www . geesforgeks . org/send-message-to-telegram-user-use-python/](https://www.geeksforgeeks.org/send-message-to-telegram-user-using-python/)

你有没有想过人们是如何在 Telegram 上实现自动化的？你可能知道 Telegram 拥有庞大的用户群，因此它是阅读人群的首选社交媒体之一。Telegram 的好处是它提供了一堆 API 的方法，不像 Whatsapp 那样限制这些东西。因此，在这篇文章中，我们将分享如何使用 Python 向 Telegram 用户发送消息。

## 入门指南

首先，使用电报机器人创建一个机器人。要创建机器人父亲，请遵循以下步骤–

*   打开电报应用，搜索@ BotFather。
*   点击开始按钮或发送/开始。
*   然后发送“/newbot”消息来设置名称和用户名。
*   设置名称和用户名后，机器人爸爸会给你一个应用编程接口令牌，这是你的机器人令牌。

然后在电报上创建一个应用程序。遵循以下步骤–

*   登录电报核心:[https://my.telegram.org](https://my.telegram.org)
*   转到“应用编程接口开发工具”并填写表格。
*   您将获得用户授权所需的 *api_id* 和 *api_hash* 参数。

### 需要的模块

脚本运行需要几个 Python 库导入。

*   **telebot:** 要安装该模块，请在终端中键入以下命令。

```py
pip install telebot
```

*   **电传:**要安装该模块，在终端中键入以下命令。

```py
pip install telethon
```

下面是实现。

## 蟒蛇 3

```py
# importing all required libraries
import telebot
from telethon.sync import TelegramClient
from telethon.tl.types import InputPeerUser, InputPeerChannel
from telethon import TelegramClient, sync, events

# get your api_id, api_hash, token
# from telegram as described above
api_id = 'API_id'
api_hash = 'API_hash'
token = 'bot token'
message = "Working..."

# your phone number
phone = 'YOUR_PHONE_NUMBER_WTH_COUNTRY_CODE'

# creating a telegram session and assigning
# it to a variable client
client = TelegramClient('session', api_id, api_hash)

# connecting and building the session
client.connect()

# in case of script ran first time it will
# ask either to input token or otp sent to
# number or sent or your telegram id
if not client.is_user_authorized():

    client.send_code_request(phone)

    # signing in the client
    client.sign_in(phone, input('Enter the code: '))

try:
    # receiver user_id and access_hash, use
    # my user_id and access_hash for reference
    receiver = InputPeerUser('user_id', 'user_hash')

    # sending message using telegram client
    client.send_message(receiver, message, parse_mode='html')
except Exception as e:

    # there may be many error coming in while like peer
    # error, wrong access_hash, flood_error, etc
    print(e);

# disconnecting the telegram session
client.disconnect()
```