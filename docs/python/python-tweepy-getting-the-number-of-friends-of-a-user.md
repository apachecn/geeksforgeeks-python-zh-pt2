# Python Tweepy–获取用户的好友数量

> 原文:[https://www . geeksforgeeks . org/python-tweepy-获取用户好友数量/](https://www.geeksforgeeks.org/python-tweepy-getting-the-number-of-friends-of-a-user/)

在本文中，我们将了解如何获取用户的好友数量。朋友是用户正在关注的帐户。friends_count 属性为我们提供了一个整数，用于捐赠用户帐户的好友数量。

**在 GUI 中识别好友数量:**
![](img/c07c9127c0466ccd199c4a1b7589c7e7.png)

在上面提到的个人资料中，朋友的数量是:11

> 为了获得朋友的数量，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从这个对象中，获取其中的 friends_count 属性。

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

# fetching the friends_count
friends_count = user.friends_count

print("The number of friends of the user are : " + str(friends_count))
```

**输出:**

```py
The number of friends of the user are : 11

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the friends_count
friends_count = user.friends_count

print("The number of friends of the user are : " + str(friends_count))
```

**输出:**

```py
The number of friends of the user are : 5

```