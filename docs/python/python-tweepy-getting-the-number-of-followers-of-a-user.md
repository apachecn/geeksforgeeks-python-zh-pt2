# Python Tweepy–获取用户的关注人数

> 原文:[https://www . geesforgeks . org/python-tweepy-获取用户关注人数/](https://www.geeksforgeeks.org/python-tweepy-getting-the-number-of-followers-of-a-user/)

在本文中，我们将看到如何获得用户的追随者数量。followers_count 属性为我们提供了一个整数，贡献了用户帐户的追随者数量。

**确定 GUI 中追随者的数量:**
![](img/fd37220c9d71db08ad8e13785ed4b443.png)

在上面提到的配置文件中，追随者的数量是:17.8 千(17，800+)

> 为了获得关注者的数量，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从这个对象中，获取其中存在的 followers_count 属性。

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

# fetching the followers_count
followers_count = user.followers_count

print("The number of followers of the user are : " + str(followers_count))
```

**输出:**

```
The number of followers of the user are : 17814

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the followers_count
followers_count = user.followers_count

print("The number of followers of the user are : " + str(followers_count))
```

**输出:**

```
The number of followers of the user are : 2204

```