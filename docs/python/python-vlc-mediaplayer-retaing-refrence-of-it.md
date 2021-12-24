# Python VLC MediaPlayer–保留对它的引用

> 原文:[https://www . geesforgeks . org/python-VLC-media player-retaining-reference-of-it/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-retaing-refrence-of-it/)

在本文中，我们将看到如何在 python vlc 模块中保留对 MediaPlayer 对象的引用。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。MediaPlayer 对象是 vlc 模块中播放视频的基本对象。我们可以借助 MediaPlayer 方法创建一个 MediaPlayer 对象。我们可以借助 release 方法来释放这个对象。

> 为此，我们将对 MediaPlayer 对象使用 retain 方法
> **语法:**media _ player . retain()
> **参数:**它不接受参数
> **返回:**它返回 None

下面是实现

## 蟒蛇 3

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media object
media = vlc.Media("death_note.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# retaining object of media player
media_player.retain()
```

**输出:**

![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

下面再举一个例子
就是实现

## 蟒蛇 3

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media object
media = vlc.Media("1mp4.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting media
value = media_player.get_media()

# retaining object of media player
media_player.retain()
```

**输出:**

![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)