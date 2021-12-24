# Python Tweepy–获取用户位置

> 原文:[https://www . geesforgeks . org/python-tweepy-get-location-a-user/](https://www.geeksforgeeks.org/python-tweepy-getting-the-location-of-a-user/)

在本文中，我们将了解如何获取用户的位置。用户帐户的位置不必是用户的确切物理位置。由于用户可以自由改变自己的位置，账户的位置甚至可以由一个假想的地点来确定。位置属性是可选的，并且可以为空。

**在图形用户界面中识别位置:**
![](img/1e9eef95cb5d987cd208b729b6a54323.png)

在上面提到的配置文件中，印度是配置文件的位置。

> 为了获得位置，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从该对象中，获取其中存在的位置属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
我们将使用用户 ID 来获取用户。上述配置文件的用户标识为 57741058。

## 蟒蛇 3

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

# fetching the location
location = user.location

print("The location of the user is : " + location)
```

**输出:**

```py
The location of the user is : India

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。这里没有提到位置。

## 蟒蛇 3

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the name
name = user.name

if location == "":
    print("The user has not mentioned their location.")
else:
    print("The location of the user is : " + location)
```

**输出:**

```py
The user has not mentioned their location.

```