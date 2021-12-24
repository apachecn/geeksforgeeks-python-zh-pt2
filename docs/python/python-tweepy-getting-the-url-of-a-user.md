# Python Tweepy–获取用户的网址

> 原文:[https://www . geesforgeks . org/python-tweepy-get-the-URL-of-a-user/](https://www.geeksforgeeks.org/python-tweepy-getting-the-url-of-a-user/)

在本文中，我们将了解如何获取用户的网址。url 属性是用户提供的与其配置文件相关联的 URL。网址属性是可选的，可以为空。

**识别图形用户界面中的网址:**
![](img/8b271836d8f297b32057712d165e7e0f.png)

在上面提到的简介中，网址是:geeksforgeeks.org

> 为了获取网址，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从这个对象中，获取其中存在的 url 属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
我们将使用用户 ID 来获取用户。上述配置文件的用户标识为 57741058。

```py
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

# fetching the url
url = user.url

print("The URL of the user is : " + url)
```

**输出:**

```py
The URL of the user is : http://t.co/k2iUfxLRBj

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the url
url = user.url

print("The URL of the user is : " + url)
```

**输出:**

```py
The URL of the user is : https://t.co/C5SOw0qMo4

```