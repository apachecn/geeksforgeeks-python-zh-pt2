# Python Tweepy–获取用户 ID

> 原文:[https://www . geesforgeks . org/python-tweepy-get-id-of-user/](https://www.geeksforgeeks.org/python-tweepy-getting-the-id-of-a-user/)

在本文中，我们将看到如何获取用户的 ID。ID 是推特账户的唯一识别标记。ID 是 Twitter 给用户的，用户不能选择或更改自己的 ID。

> 为了获得该标识，我们必须执行以下操作:
> 
> 1.  标识配置文件的用户屏幕名称。
> 2.  使用`get_user()`方法和用户名获取配置文件的用户对象。
> 3.  从这个对象中，获取其中存在的 id 或 id_str 属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
上面提到的配置文件的屏幕名称是 geeksforgeeks。

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

# the screen name of the user
screen_name = "geeksforgeeks"

# fetching the user
user = api.get_user(screen_name)

# fetching the ID
ID = user.id_str

print("The ID of the user is : " + ID)
```

**输出:**

```py
The ID of the user is : 57741058

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
上面提到的配置文件的屏幕名称是 PracticeGfG。

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the ID
ID = user.id_str

print("The ID of the user is : " + ID)
```

**输出:**

```py
The ID of the user is : 4802800777

```