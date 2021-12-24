# Python Tweepy–获取用户描述

> 原文:[https://www . geesforgeks . org/python-tweepy-get-description-a-user/](https://www.geeksforgeeks.org/python-tweepy-getting-the-description-of-a-user/)

在本文中，我们将了解如何获取用户的描述。的描述描述了一个用户帐户。描述属性是可选的，并且可以为空。

**识别 GUI 中的描述:**
![](img/798a5fa32e0d56de369b9f2523965532.png)

在上面提到的配置文件中，描述是:您实现编码涅槃的一站式目的地…

> 为了获得描述，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从这个对象中，获取其中存在的描述属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
我们将使用用户 ID 来获取用户。上述配置文件的用户标识为 57741058。

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

# fetching the description
description = user.description

print("The description of the user is : " + description)
```

**输出:**

```
The description of the user is : Your one-stop destination to attain Coding Nirvana...

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the description
description = user.description

print("The description of the user is : " + description)
```

**输出:**

```
The description of the user is : Platform to practice programming problems. Solve 
company interview questions and improve your coding intellect!

```