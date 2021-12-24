# Python VLC MediaPlayer–获取所选视频的高度

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-high-of-selected-video/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-height-of-selected-video/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的高度。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。MediaPlayer 对象是 vlc 模块中播放视频的基本对象。我们可以借助 MediaPlayer 方法创建一个 MediaPlayer 对象。我们可以通过传递视频的索引来获得所选视频的高度，如果没有指定索引，则返回正在进行的视频高度。

> 为此，我们将对 MediaPlayer 对象
> **使用 video_get_height 方法语法:**media _ player . video _ get _ height(n)
> **参数:**它将整数作为可选参数
> **返回:**它返回整数

下面是实现

## 蟒蛇 3

```
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media resource locator
mrl = "death_note.mkv"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting height at index 0
value = media_player.video_get_height(0)

# printing height
print("Height at Index 0 : ")
print(value)
```

**输出:**

![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```
Height at Index 0 : 
720
```

另一个例子

下面是实现

## 蟒蛇 3

```
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media resource locator
mrl = "1.mp4"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting height at index 0
value = media_player.video_get_height(0)

# printing height
print("Height at Index 0 : ")
print(value)
```

**输出:**

![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```
Height at Index 0 : 
480
```