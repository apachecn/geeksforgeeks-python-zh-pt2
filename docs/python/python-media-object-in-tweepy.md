# Python–Tweepy 中的媒体对象

> 原文:[https://www . geesforgeks . org/python-media-object-in-tweepy/](https://www.geeksforgeeks.org/python-media-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 媒体

Tweepy 模块中的 **`Media`** 对象包含了一个上传到 Twitter 上的媒体文件的信息。

以下是媒体对象中的属性列表:

> *   **Media _ id:** ID of the media object.
> *   **Media _ id _ str:** The ID of the media object is a string.
> *   **Size:** The size of the media object in bytes.
> *   [T0】 expires _ after _ secs: 【T1] The time (in seconds) when the media object expires.
> *   **Image _ Type:** The type of image.
> *   **w:** The width of the media object.
> *   **h:** The height of the media object.

**示例:**我们将使用`media_upload()`方法上传和获取媒体对象。

考虑以下图像:
![](img/4e8b447ebedae418847a759efe70c809.png)

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

# uploading the media and fetching the Media object
media = api.media_upload("gfg.png")

# printing the information
print("The media_id is : " + str(media.media_id))
print("The media_id_string is : " + media.media_id_string)
print("The size is : " + str(media.size))
print("The expires_after_secs is : " + str(media.expires_after_secs))
print("The image_type is : " + str(media.image["image_type"]))
print("The w is : " + str(media.image["w"]))
print("The h is : " + str(media.image["h"]))
```

**输出:**

```py
The media_id is : 1273526215773573121
The media_id_string is : 1273526215773573121
The size is : 3346
The expires_after_secs is : 86400
The image_type is : image/png
The w is : 225
The h is : 225

```