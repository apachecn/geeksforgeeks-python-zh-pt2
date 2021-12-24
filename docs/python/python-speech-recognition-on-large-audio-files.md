# Python |大型音频文件上的语音识别

> 原文:[https://www . geesforgeks . org/python-大型音频文件语音识别/](https://www.geeksforgeeks.org/python-speech-recognition-on-large-audio-files/)

 **语音识别**是将音频转换为文本的过程。这通常用于语音助手，如 Alexa、Siri 等。Python 提供了一个名为 SpeechRecognition 的 API，允许我们将音频转换成文本进行进一步处理。在本文中，我们将研究使用 python 中的 SpeechRecognition API 将大型或长音频文件转换为文本。

## 处理大型音频文件

当输入是长音频文件时，语音识别的准确性会降低。而且，谷歌语音识别 API 无法很好的识别长音频文件。因此，我们需要将音频文件处理成更小的块，然后将这些块馈送给应用编程接口。这样做可以提高准确性，并允许我们识别大型音频文件。

## 基于静音分割音频

处理音频文件的一种方法是将其分割成大小不变的块。例如，我们可以将一个 10 分钟长的音频文件分成 60 个块，每个块的长度为 10 秒。然后，我们可以将这些块馈送到应用编程接口，并通过连接所有这些块的结果将语音转换为文本。这种方法不准确。将音频文件分割成大小不变的块可能会打断中间的句子，并且我们可能会在这个过程中丢失一些重要的单词。这是因为音频文件可能在一个单词完全说出之前就结束了，谷歌将无法识别不完整的单词。

另一种方法是基于静音分割音频文件。人类在句子之间停顿一小段时间。如果我们可以根据这些沉默将音频文件分割成块，那么我们可以一句一句地处理文件，并将它们连接起来以获得结果。这种方法比前一种方法更准确，因为我们不在中间剪切句子，音频块将包含整个句子，没有任何中断。这样，我们就不需要把它分成固定长度的块。

这种方法的缺点是很难确定要分割的沉默时间长度，因为不同的用户说话方式不同，有些用户可能会在两句话之间停顿 1 秒钟，而有些用户可能只停顿 0.5 秒钟。

## 需要库

```py
Pydub: sudo pip3 install pydub
Speech recognition: sudo pip3 install SpeechRecognition

```

**示例:**

```py
 Input: peacock.wav 

 Output: 

exporting chunk0.wav
Processing chunk 0
exporting chunk1.wav
Processing chunk 1
exporting chunk2.wav
Processing chunk 2
exporting chunk3.wav
Processing chunk 3
exporting chunk4.wav
Processing chunk 4
exporting chunk5.wav
Processing chunk 5
exporting chunk6.wav
Processing chunk 6

```

**代码:**

```py
# importing libraries
import speech_recognition as sr

import os

from pydub import AudioSegment
from pydub.silence import split_on_silence

# a function that splits the audio file into chunks
# and applies speech recognition
def silence_based_conversion(path = "alice-medium.wav"):

    # open the audio file stored in
    # the local system as a wav file.
    song = AudioSegment.from_wav(path)

    # open a file where we will concatenate  
    # and store the recognized text
    fh = open("recognized.txt", "w+")

    # split track where silence is 0.5 seconds 
    # or more and get chunks
    chunks = split_on_silence(song,
        # must be silent for at least 0.5 seconds
        # or 500 ms. adjust this value based on user
        # requirement. if the speaker stays silent for 
        # longer, increase this value. else, decrease it.
        min_silence_len = 500,

        # consider it silent if quieter than -16 dBFS
        # adjust this per requirement
        silence_thresh = -16
    )

    # create a directory to store the audio chunks.
    try:
        os.mkdir('audio_chunks')
    except(FileExistsError):
        pass

    # move into the directory to
    # store the audio files.
    os.chdir('audio_chunks')

    i = 0
    # process each chunk
    for chunk in chunks:

        # Create 0.5 seconds silence chunk
        chunk_silent = AudioSegment.silent(duration = 10)

        # add 0.5 sec silence to beginning and 
        # end of audio chunk. This is done so that
        # it doesn't seem abruptly sliced.
        audio_chunk = chunk_silent + chunk + chunk_silent

        # export audio chunk and save it in 
        # the current directory.
        print("saving chunk{0}.wav".format(i))
        # specify the bitrate to be 192 k
        audio_chunk.export("./chunk{0}.wav".format(i), bitrate ='192k', format ="wav")

        # the name of the newly created chunk
        filename = 'chunk'+str(i)+'.wav'

        print("Processing chunk "+str(i))

        # get the name of the newly created chunk
        # in the AUDIO_FILE variable for later use.
        file = filename

        # create a speech recognition object
        r = sr.Recognizer()

        # recognize the chunk
        with sr.AudioFile(file) as source:
            # remove this if it is not working
            # correctly.
            r.adjust_for_ambient_noise(source)
            audio_listened = r.listen(source)

        try:
            # try converting it to text
            rec = r.recognize_google(audio_listened)
            # write the output to the file.
            fh.write(rec+". ")

        # catch any errors.
        except sr.UnknownValueError:
            print("Could not understand audio")

        except sr.RequestError as e:
            print("Could not request results. check your internet connection")

        i += 1

    os.chdir('..')

if __name__ == '__main__':

    print('Enter the audio file path')

    path = input()

    silence_based_conversion(path)
```

 **输出:**

```py

recognized.txt:

The peacock is the national bird of India. They have colourful feathers, two legs and 
a small beak. They are famous for their dance. When a peacock dances it spreads its 
feathers like a fan. It has a long shiny dark blue neck. Peacocks are mostly found in 
the fields they are very beautiful birds. The females are known as 'Peahen1\. Their 
feathers are used for making jackets, purses etc. We can see them in a zoo. 

```