# Python Tweepy–获取用户的屏幕名称

> 原文:[https://www . geesforgeks . org/python-tweepy-get-screen-用户名/](https://www.geeksforgeeks.org/python-tweepy-getting-the-screen-name-of-a-user/)

在本文中，我们将了解如何获取用户的屏幕名称。屏幕名称是 twitter 账户的用户名。它是用户选择在网络上用来表明自己身份的名称。许多用户选择使用他们的真实姓名作为他们的屏幕名称的基础，通常是缩短的版本。所有屏幕名称必须唯一。

**在 GUI 中识别屏幕名称:**
![](img/1c8d73c6f34d1a093abbcb57de48866f.png)

在上面提到的配置文件中，geeksforgeeks 是配置文件的屏幕名称。

> 为了获得屏幕名称，我们必须执行以下操作:
> 
> 1.  标识配置文件的用户标识。
> 2.  使用`get_user()`方法和用户标识获取配置文件的用户对象。
> 3.  从这个对象中，获取其中存在的 screen_name 属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
上述配置文件的用户 ID 为 57741058。

```
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret 
auth.set_access_token(access_token, access_token_secret)

# calling the api 
api = tweepy.API(auth)

# the ID of the user
id = 57741058

# fetching the user
user = api.get_user(id)

# fetching the screen name
screen_name = user.screen_name

print("The screen name of the user is : " + screen_name)
```

**输出:**

```
The screen name of the user is : geeksforgeeks

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
上述配置文件的用户 ID 为 4802800777。

```
# the ID of the user
id = 4802800777

# fetching the user
user = api.get_user(id)

# fetching the screen name
screen_name = user.screen_name

print("The screen name of the user is : " + screen_name)
```

**输出:**

```
The screen name of the user is : PracticeGfG

```