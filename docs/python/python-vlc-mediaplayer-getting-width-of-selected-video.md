# Python VLC MediaPlayer–获取所选视频的宽度

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-width-of-selected-video/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-width-of-selected-video/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的宽度。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。我们可以通过传递视频的索引来获得所选视频的宽度，如果没有指定索引，则返回正在进行的视频宽度。

> 为此，我们将对 MediaPlayer 对象使用`video_get_width`方法
> 
> **语法:**media _ player . video _ get _ width(n)
> 
> **参数:**取整数作为可选参数
> 
> **返回:**返回整数

下面是实现

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

# getting width at index 0
value = media_player.video_get_width(0)

# printing width
print("Width at Index 0 : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```
Width at Index 0 : 
1280

```

下面是另一个例子
的实现

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

# getting width at index 0
value = media_player.video_get_width(0)

# printing width
print("Width at Index 0 : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```
Width at Index 0 : 
854
```