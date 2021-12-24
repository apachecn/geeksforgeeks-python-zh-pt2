# 使用 Pydub 使用 Python 处理 wav 文件

> 原文:[https://www . geesforgeks . org/work-with-wav-files-in-python-using-py dub/](https://www.geeksforgeeks.org/working-with-wav-files-in-python-using-pydub/)

音频文件是一种广泛传播的信息传递方式。让我们看看如何使用 Python 处理音频文件。Python 提供了一个名为**的模块**来处理音频文件。 **pydub** 是一个 Python 库，只能和**一起使用。wav** 文件。通过使用这个库，我们可以播放、分割、合并、编辑我们的**。** wav 音频文件。

### **安装**

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```
pip install pydub

```

以下是 pydub 可以执行的一些功能:

1.  播放音频文件。
2.  我们可以获得文件的某些信息，如长度通道。
3.  增加/减少给定的音量。wav 文件。
4.  合并两个或多个音频文件。
5.  导出音频文件。
6.  拼接音频文件。

要访问输入的声音文件，请点击这里的[**。**](https://drive.google.com/drive/folders/1tyDjd_6sddoxoMZXncjyqU-Sly_6yHPD?usp=sharing) 我们来看看 pydub 库的一些功能的代码:

1) **播放音频文件:**这是使用 **play()** 方法完成的。

## 蟒蛇 3

```
# import required libraries
from pydub import AudioSegment 
from pydub.playback import play 

# Import an audio file 
# Format parameter only
# for readability 
wav_file = AudioSegment.from_file(file = "Sample.wav", 
                                  format = "wav") 

# Play the audio file
play(wav_file)
```

**输出:**

<audio class="wp-audio-shortcode" id="audio-467353-1" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20200811180636/Sample.wav?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200811180636/Sample.wav](https://media.geeksforgeeks.org/wp-content/uploads/20200811180636/Sample.wav)</audio>

2) **知乎。wav 文件:**为此我们将使用音频文件对象的**属性**。

## 蟒蛇 3

```
# import required library
from pydub import AudioSegment 

# import the audio file
wav_file = AudioSegment.from_file(file="Sample.wav", format="wav") 

# data type fo the file
print(type(wav_file)) 
# OUTPUT: <class 'pydub.audio_segment.AudioSegment'>

#  To find frame rate of song/file
print(wav_file.frame_rate)   
# OUTPUT: 22050 

# To know about channels of file
print(wav_file.channels) 
# OUTPUT: 1

# Find the number of bytes per sample 
print(wav_file.sample_width ) 
# OUTPUT : 2

# Find Maximum amplitude 
print(wav_file.max)
# OUTPUT 17106

# To know length of audio file
print(len(wav_file))
# OUTPUT 60000 

'''
We can change the attrinbutes of file by 
changeed_audio_segment = audio_segment.set_ATTRIBUTENAME(x) 
'''
wav_file_new = wav_file.set_frame_rate(50) 
print(wav_file_new.frame_rate)
```

**输出:**

```
<class 'pydub.audio_segment.AudioSegment'>
22050
1
2
17106
60000
50

```

3) **通过使用“**+“**和“**-“**运算符来增加/减少文件的音量:**。

## 蟒蛇 3

```
# import required library
import pydub 
from pydub.playback import play

wav_file =  pydub.AudioSegment.from_file(file = "Sample.wav", 
                                         format = "wav") 
# Increase the volume by 10 dB 
new_wav_file = wav_file + 10 

# Reducing volume by 5
silent_wav_file = wav_file - 5

#  Playing silent file
play(silent_wav_file)

#  Playing original file
play(wav_file)

#  Playing louder file
play(new_wav_file)

# Feel the difference!
```

**输出:**

<audio class="wp-audio-shortcode" id="audio-467353-2" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20200811182026/output2.wav?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200811182026/output2.wav](https://media.geeksforgeeks.org/wp-content/uploads/20200811182026/output2.wav)</audio>

4) **合并文件:**这是使用**“+”**运算符完成的。

## 蟒蛇 3

```
# import required libraries
from pydub import AudioSegment
from pydub.playback import play

wav_file_1 = AudioSegment.from_file("noice.wav") 
wav_file_2 = AudioSegment.from_file("Sample.wav")

# Combine the two audio files 
wav_file_3 = wav_file_1 + wav_file_2

# play the sound 
play(wav_file_3)
```

**输出:**

<audio class="wp-audio-shortcode" id="audio-467353-3" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20200811180732/Output3.wav?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200811180732/Output3.wav](https://media.geeksforgeeks.org/wp-content/uploads/20200811180732/Output3.wav)</audio>

**5)导出文件:**这是使用**导出()**方法完成的。

## 蟒蛇 3

```
# import library
from pydub import AudioSegment 

# Import audio file 
wav_file = AudioSegment.from_file("Sample.wav") 
'''
     You can do anything like remixing and export 
     I'm increasing volume just for sake of my simplicity
     Increase by 10 decibels 

'''
louder_wav_file = wav_file + 10 

# Export louder audio file 
louder_wav_file.export(out_f = "louder_wav_file.wav", 
                       format = "wav")
```

**输出:**

<audio class="wp-audio-shortcode" id="audio-467353-4" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20200811180631/louder_wav_file.wav?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20200811180631/louder_wav_file.wav](https://media.geeksforgeeks.org/wp-content/uploads/20200811180631/louder_wav_file.wav)</audio>

6) **拆分音频:**使用 **split_to_mono()** 方法拆分音频。

## 蟒蛇 3

```
# import required libraries
from pydub import AudioSegment 
from pydub.playback import play

# importing audio file
a = AudioSegment.from_file("pzm12.wav") 

# Split stereo to mono 
b = a.split_to_mono() 
print(b) 
print(b[0].channels )

b[0].export(out_f="outNow.wav",format="wav")
```

**输出:**

```
[<pydub.audio_segment.AudioSegment object at 0x000001358727E860>, <pydub.audio_segment.AudioSegment object at 0x000001358721F978>]
1

```

<audio class="wp-audio-shortcode" id="audio-467353-5" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20200811181753/outNow.wav?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/20200811181753/outNow.wav](https://media.geeksforgeeks.org/wp-content/uploads/20200811181753/outNow.wav)</audio>