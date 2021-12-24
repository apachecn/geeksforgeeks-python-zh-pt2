# Python Tweepy–获取创建用户的时间

> 原文:[https://www . geesforgeks . org/python-tweepy-get-time-a-user-created/](https://www.geeksforgeeks.org/python-tweepy-getting-the-time-when-a-user-was-created/)

在本文中，我们将了解如何获取用户创建其推特账户的时间和日期。created_at 属性为我们提供了一个 datetime 对象，表示创建用户帐户的确切时间。

**识别用户在 GUI 中创建的日期:**
![](img/bf75f32121fad59ae75e8073d39e774f.png)

在上面提到的配置文件中，用户是在 2009 年 7 月创建的。

> 为了获得创建用户的日期和时间，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从该对象中，获取其中存在的 created_at 属性。

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

# fetching the create_at attribute
created_at = user.created_at

print("The user was created on : " + str(created_at))
```

**输出:**

```
The user was created on : 2009-07-17 20:02:09

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the create_at attribute
created_at = user.created_at

print("The user was created on : " + str(created_at))
```

**输出:**

```
The user was created on : 2016-01-23 12:03:47

```