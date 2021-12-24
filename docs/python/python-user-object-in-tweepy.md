# Python–Tweepy 中的用户对象

> 原文:[https://www.geeksforgeeks.org/python-user-object-in-tweepy/](https://www.geeksforgeeks.org/python-user-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 用户

Tweepy 模块中的 **`User`** 对象包含用户的信息。

以下是用户对象中的属性列表:

> *   **id:** The ID of the user.
> *   **id _ str:** The user's ID is a string.
> *   **Name:** The name of the user.
> *   **Screen _ name:** The screen name of the user.
> *   **Location:** The user's location.
> *   **Section _ position:** The position of the section.
> *   **Description:** Description of the user account.
> *   **url:** The URL of the user account.
> *   **Entity:** A dictionary containing URLs.
> *   **Protected:** indicates whether the user file is protected.
> *   **Followers _ Count:** The number of followers this account has.
> *   **Friends _ Count:** The number of friends in the account.
> *   [T0】 listed _ count: 【T1] Number of public lists to which the account has been added.
> *   **Creation time:** The time when the account was created.
> *   **Favorites _ Count:** The number of preferred states of this account.
> *   **utc _ offset:** UTC offset of the profile.
> *   **geo _ enabled:** indicates whether geo is enabled for the account.
> *   **Verified:** indicates whether the user has been verified.
> *   **Status Number:** The status number updated by the user.
> *   **Lang:** The language of Li Shimin.
> *   **Status:** Get the latest status updated by the user.
> *   **Contributor _ Enabled:** indicates whether the contributor has been enabled.
> *   [T0】 is _ translator: 【T1] indicates whether there is translation.
> *   [T0】 is _ translation _ enabled: 【T1] indicates whether translation is available.
> *   **outline _ background _ color:** background color of outline.
> *   **Introduction _ background _ image _ url:** The URL of the introduction background image.
> *   **profile _ background _ image _ URL _ https:**配置文件背景图像的安全网址.
> *   **Introduction _ Background _ Tile:** The title of the background introduction.
> *   [T0】 profile _ image _ url: 【T1] The URL of the profile image.
> *   [T0】 profile _ image _ url _ https: 【T1] The secure URL of the profile image.
> *   **profile _ banner _ url:** 中文 url。
> *   **profile _ link _ color:**profile 链接的颜色。
> *   **Profile _ sidebar _ border _ color:** The color of the sidebar border of the profile.
> *   **Personal data _ sidebar _ padding _ color:** The color of the personal data sidebar.
> *   [T0】 profile _ text _ color: 【T1] The color of the profile text.
> *   **Profile _ use _ background _ image:** Indicates whether the profile uses the background image.
> *   **has _ extended _ profile:** indicates whether the configuration file is extended or not.
> *   **默认 _ 配置文件:**默认的简介.
> *   **Default _ outline _ image:** The image of the default outline.
> *   **Follow:** indicates whether the authentication user follows the user.
> *   [T0】 follow _ request _ send: 【T1] Indicates whether the authenticated user requests to follow the user.
> *   **Notification:** indicates whether the authentication user has opened a notification for the user.

**例如:**考虑一下[极客的推特账户](https://twitter.com/geeksforgeeks)。使用`get_user()`方法获取用户。

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

# printing the information
print("The id is : " + str(user.id))
print("The id_str is : " + user.id_str)
print("The name is : " + user.name)
print("The screen_name is : " + user.screen_name)
print("The location is : " + str(user.location))
print("The profile_location is : " + str(user.profile_location))
print("The description is : " + user.description)

print("The url is : " + user.url)
print("The entities are : " + str(user.entities))
print("Is the account protected? : " + str(user.protected))

print("The followers_count is : " + str(user.followers_count))
print("The friends_count is : " + str(user.friends_count))
print("The listed_count is : " + str(user.listed_count))
print("The account was created on : " + str(user.created_at))
print("The favourites_count is : " + str(user.favourites_count))
print("The utc_offset is : " + str(user.utc_offset))
print("The geo_enabled is : " + str(user.geo_enabled))
print("The verified is : " + str(user.verified))
print("The statuses_count is : " + str(user.statuses_count))
print("The lang is : " + str(user.lang))
print("The status ID is : " + str(user.status.id))
print("The contributors_enabled is : " + str(user.contributors_enabled))
print("The is_translator is : " + str(user.is_translator))
print("The is_translation_enabled is : " + str(user.is_translation_enabled))

print("The profile_background_color is : " + user.profile_background_color)
print("The profile_background_image_url is : " + user.profile_background_image_url)
print("The profile_background_image_url_https is : " + user.profile_background_image_url_https)
print("The profile_background_tile is : " + str(user.profile_background_tile))
print("The profile_image_url is : " + user.profile_image_url)
print("The profile_image_url_https is : " + user.profile_image_url_https)
print("The profile_banner_url is : " + user.profile_banner_url)
print("The profile_link_color is : " + user.profile_link_color)
print("The profile_sidebar_border_color is : " + user.profile_sidebar_border_color)
print("The profile_sidebar_fill_color is : " + user.profile_sidebar_fill_color)
print("The profile_text_color is : " + user.profile_text_color)
print("The profile_use_background_image is : " + str(user.profile_use_background_image))

print("The has_extended_profile is : " + str(user.has_extended_profile))
print("The default_profile is : " + str(user.default_profile))
print("The default_profile_image is : " + str(user.default_profile_image))
print("Is the authenticated user following the account? : " + str(user.following))

print("Has the authenticated user requested to follow the account? : " + str(user.follow_request_sent))
print("Are notifications of the authenticated user turned on for the account? : " + str(user.notifications))
```

**输出:**

> id 为:57741058
> id _ str 为:57741058
> 名称为:geesforgeks
> 屏幕名称为:geesforgeks
> 位置为:印度
> 简介位置为:无
> 描述为:您实现编码涅槃的一站式目的地……
> URL 为:http://t.co/k2iUfxLRBj
> 实体为:{“URL”:{“URL”:[{“URL”:“http://t:False
> 关注者 _ 计数为:17706
> 好友 _ 计数为:11
> 列出的 _ 计数为:142
> 账户创建时间:2009-07-17 20:02:09
> 收藏夹 _ 计数为:465
> utc _ offset 为:None
> geo _ enabled 为:False
> 已验证为:False
> 状态 _ 计数为:11 is:False
> is _ translation _ enabled 为:False
> profile _ background _ color 为:fffdf 7
> profile _ background _ image _ URL 为:http://abs.twimg.com/images/themes/theme13/bg.gif
> profile _ background _ image _ URL _ https 为:https://abs.twimg.com/images/themes/theme13/bg.gif
> profile _ background _ tile 为:False
> profile _ image _ URL 为:http://PBS . twimg . com/profile _ images/113837557472695008/11113837574726