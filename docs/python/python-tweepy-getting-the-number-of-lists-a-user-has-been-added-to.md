# Python Tweepy–获取用户已添加到的列表数量

> 原文:[https://www . geesforgeks . org/python-tweepy-get-list-number-a-user-add-to/](https://www.geeksforgeeks.org/python-tweepy-getting-the-number-of-lists-a-user-has-been-added-to/)

在本文中，我们将了解如何获取用户已添加到的列表数量。listed _ count 属性为我们提供了一个整数，表示用户已被添加到的公共列表的数量。个人分发名单不计算在内。

> 为了获得用户已被添加到的公共列表的数量，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从该对象中，获取其中存在的 listed _ count 属性。

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

# fetching the listed_count
listed_count = user.listed_count

print("The number of lists the user has been added to are : " + str(listed_count))
```

**输出:**

```py
The number of lists the user has been added to are : 141

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the listed_count
listed_count = user.listed_count

print("The number of lists the user has been added to are : " + str(listed_count))
```

**输出:**

```py
The number of lists the user has been added to are : 6

```