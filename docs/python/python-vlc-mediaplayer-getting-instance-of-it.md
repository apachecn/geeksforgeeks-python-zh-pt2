# Python VLC MediaPlayer–获取它的实例

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-instance-it/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-instance-of-it/)

在本文中，我们将看到如何在 python vlc 模块中获取 MediaPlayer 对象的实例。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。MediaPlayer 类是基本类，它用于一次播放单个视频。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。

> 为此，我们将对 MediaPlayer 对象使用`get_instance`方法
> 
> **语法:** media_player.get_instance()
> 
> **论证:**不需要论证
> 
> **返回:**返回与之关联的实例

下面是实现

```
# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer("death_note.mkv")

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting instance of the media player
inst = media_player.get_instance()
print("Media player Instance : " + str(inst))
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```
Media player Instance : <vlc.Instance object at 0x000001DE3184EE08

```

另一个例子

```
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# getting instance of the media player
inst = media_player.get_instance()
print("Media player Instance : " + str(inst))
```

**输出:**

```
Media player Instance : <vlc.Instance object at 0x000001AD5452ED48

```