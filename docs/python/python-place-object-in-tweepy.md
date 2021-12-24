# Python–将对象放入 Tweepy

> 原文:[https://www . geesforgeks . org/python-place-object-in-tweepy/](https://www.geeksforgeeks.org/python-place-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 地方

Tweepy 模块中的 **`Place`** 对象包含一个地方的信息。

以下是放置对象中的属性列表:

> *   **id:** The ID of the place.
> *   **Website:** The website representing the location.
> *   **Location _ Type:** The location type represented by the location.
> *   **Name:** Place name.
> *   **Full name:** Full name of place name.
> *   **country _ code: the code of the country where** is located.
> *   **Country:** The name of the country.
> *   [T0】 contained _ in: 【T1] The location object containing the location.
> *   **Geometry:** The geometry of the place.
> *   **polyline:** The polyline here.
> *   **Center of Mass:** The center of mass here.
> *   **The coordinates surrounding the place.**

**例:**用`geo_id()`法取地方。以伦敦为例。

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

# Twitter ID of London 
id = "457b4814b4240d87"

# fetching the location 
place = api.geo_id(id) 

# printing the information 
print("The id is : " + place.id)
print("The url is : " + place.url)
print("The place_type is : " + place.place_type)
print("The name is : " + place.name)
print("The full_name is : " + place.full_name)
print("The country_code is : " + place.country_code)
print("The country is : " + place.country)
print("The contained_within is : " + str(place.contained_within))
print("The geometry is : " + str(place.geometry))
print("The polylines are : " + str(place.polylines))
print("The centroid is : " + str(place.centroid))
print("The bounding_box is : " + str(place.bounding_box))
```

**输出:**

> id 为:457 b 4814 b 4240d 87
> URL 为:https://api.twitter.com/1.1/geo/id/457b4814b4240d87.json
> Place _ type 为:city
> 名称为:伦敦
> 全称为:英国伦敦
> country _ code 为:GB
> 国家为:英国
> contained _ in 为:【Place(_api=，id = ' 1090 D3 ced 4 b 75d 04′，URL = ' https://API . Twitter . com/1.1/geo/id 属性={})]
> 几何图形为:无
> 折线为:[]
> 形心为:[-0.14032122753075282，51.50009175]
> 边界框为:边界框(_api=，类型= '多边形'，坐标=[[-0.187894，51.483718]，[-0.187894，