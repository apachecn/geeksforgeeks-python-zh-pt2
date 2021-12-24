# 使用 Python 中的 Instabot 模块在 Instagram 上发送消息

> 原文:[https://www . geesforgeks . org/send-message-on-insta gram-using-insta bot-module-in-python/](https://www.geeksforgeeks.org/send-message-on-instagram-using-instabot-module-in-python/)

在本文中，我们将看到如何使用 Python 中的 Instabot 模块在 Instagram 上发送消息。

Instagram 是一个很好的聊天平台，但是当涉及到向所有朋友发送相同的消息时，这是一个非常无聊和耗时的任务，尤其是如果你有大量的粉丝。为了让这变得简单，我们用 Python 制作了一个机器人，在 Instagram 上发送消息。所以不再拖延，让我们马上开始。

## 所需模块:

**Instabot 库:**是 Instagram 的一个推广脚本和 API Python 包装器。

```py
pip install instabot
```

## 逐步实施:

**步骤 1:** 首先我们从 Instabot 库中导入 bot，并制作一个变量 Bot。

## 蟒 3

```py
# importing Bot form instabot library.
from instabot import Bot

bot = Bot()
```

**第二步:**现在我们需要使用机器人登录我们的账户。

## 蟒 3

```py
# Login using bot
bot.login(username="Your_username",
          password="Your_password")
```

**第三步:**是时候列一个好友/关注者的名单了，这些信息将被发送给他们。不要忘记任何名字，因为每个人都很重要。

## 蟒 3

```py
# Make a list of followers/friends
urer_ids = ["username1", "username2", "....."]
```

**第四步:**写消息

T3

## 蟒 3

T6T8】

```py
# Message
text = "I like GFG"
```