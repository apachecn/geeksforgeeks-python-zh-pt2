# Python VLC 媒体列表–检查它是否是只读的

> 原文:[https://www . geesforgeks . org/python-VLC-medialist-checking-if-it-read-only/](https://www.geeksforgeeks.org/python-vlc-medialist-checking-if-it-is-read-only/)

在本文中，我们将看到如何在 python vlc 模块中检查 MediaList 对象是否是只读的。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。MediaList 对象包含多个媒体，换句话说，它有一个媒体列表，可以与 MediaListPlayer 对象一起使用来播放这些多个媒体对象。借助`add_media`方法，可以将多个媒体添加到媒体列表对象中。只读表示从用户角度来看，此媒体列表是否为只读。

> 为此，我们将对 MediaList 对象使用`is_readonly`方法
> 
> **语法:** media_list.is_readonly()
> 
> **论证:**不需要论证
> 
> **返回:**只读时返回 1，读写时返回 0。

下面是实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating a media player object
media_player = vlc.MediaListPlayer()

# creating Instance class object
player = vlc.Instance()

# creating a media list object
media_list = vlc.MediaList()

# creating a new media
media1 = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media1)

# creating a new media
media2 = player.media_new("1.mp4")

# adding another media
media_list.add_media(media2)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# checking if the media list is read only
value = media_list.is_readonly()

# printing value
print(value)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)

```
0

```

另一个例子

```
# importing vlc module
import vlc

# importing time module
import time

# creating a media player object
media_player = vlc.MediaListPlayer()

# creating Instance class object
player = vlc.Instance()

# creating a media list object
media_list = vlc.MediaList()

# creating a new media
media1 = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media1)

# creating a new media
media2 = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media2)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# checking if the media list is read only
value = media_list.is_readonly()

# printing value
print(value)
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)

```
0

```