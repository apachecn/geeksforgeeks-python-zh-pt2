# Python winsound 模块

> 原文:[https://www.geeksforgeeks.org/python-winsound-module/](https://www.geeksforgeeks.org/python-winsound-module/)

也许你刚刚开始用 Python 编码。也许整个开始看起来不确定，因为您一直在使用常规的 IDEs，并且希望从您的代码在各自的控制台上所做的事情中获得更多信息，也许一点音乐或曲调可能会让它活跃起来。

本文旨在向您介绍 **`winsound`** 模块，一个具有一组属性或功能的对象或文件，专门用于生成或播放声音或声音文件的任务。

**注:**模块定义为仅在**窗口**平台上执行，因此得名 **WINsound** 。

因为 winsound 模块是一个内置模块，所以您不需要在执行之前安装它。
基本操作是

```py
import winsound
```

，然后根据你想要的输出类型，输入以下函数:

*   **winsound.Beep( )**

    该方法的功能是产生“嘟嘟”声。但是，用户需要输入频率值和声音的持续时间(这些是调用函数时应该传递的参数)。

    **注意:**频率必须在 37 到 32，767 赫兹的范围内。

    ```py
    import winsound 

    # frequency is set to 500Hz
    freq = 500 

    # duration is set to 100 milliseconds             
    dur = 100

    winsound.Beep(freq, dur)
    ```

    **输出:**

    > Windows 系统将在给定的时间内以给定的频率发出“哔哔”声。

    在上面代码的基础上，通过实现一个“for”循环来增加频率和持续时间，事情可以发展到另一个层次。这已在下面的代码中完成:

    ```py
    import winsound

    freq = 100
    dur = 50

    # loop iterates 5 times i.e, 5 beeps will be produced.
    for i in range(0, 5):    
        winsound.Beep(freq, dur)    
        freq+= 100
        dur+= 50
    ```

    **输出:**

    > 产生频率差为 100 赫兹且持续时间比前一个持续时间大 50 毫秒的连续音符
    > 。

*   **winsound.PlaySound( )**
    With the PlaySound function, things can get slightly advanced, not to mention interesting. Keep in mind that this function is only compatible with `.wav` files. Two parameters are passed in the function: ‘filename’ and the flag – winsound.SND_FILENAME, which is required for the Platform API to refer to the output file. The flags are as defined below:

    | 旗帜 | 描述 |
    | --- | --- |
    | SND_FILENAME | 声音参数是 WAV 文件的名称。 |
    | SND_LOOP | 反复播放声音 |
    | SND_MEMORY | PlaySound()的声音参数是一个 WAV 文件的内存图像，是一个类似字节的对象。 |
    | S7-1200 可编程控制器 | 立即返回，允许声音异步播放。 |
    | snd _ nodefault-snd _ nodefault-snd _ nodefault-snd _ nodefault-snd _ nodefault-snd _ nodefault | 如果找不到指定的声音，请不要播放系统默认声音。 |
    | S7-1200 可编程控制器 | 不要中断当前播放的声音。 |

    **示例:**

    ```py
    import winsound

    print("Playing the file 'Welcome.wav'")

    # winsound.PlaySound('filename', flag)
    winsound.PlaySound('Welcome.wav', winsound.SND_FILENAME)       
    ```

    **输出:**

    ```py
    The respective audio file named 'Welcome.wav' is executed.

    ```

*   **SND_ALIAS**
    The sound parameter should be interpreted as a control panel sound association name. The Windows registry keys are associated with sound names. If the registry contains no such name, play the system default sound unless SND_NODEFAULT. All Win32 systems support the following:

    | PlaySound()名称 | 控制面板声音名称 |
    | --- | --- |
    | 系统星号 | 星号 |
    | 系统感叹 | 感叹 |
    | 系统退出 | 退出 windows |
    | 系统手 | 临界停止 |
    | 系统问题 | 问题 |

    **示例:**

    ```py
    import winsound

    # Play Windows question sound
    winsound.PlaySound("SystemQuestion", winsound.SND_ALIAS) 
    ```

    **输出:**

    ```py
    Play Windows question sound

    ```

还有各种其他 winsound 函数，其中大部分是特定任务的特定函数，有些函数处理运行时参数。尽管如此，上面提到的功能应该足够了，只要这个想法是玩一玩，了解使用这个模块可以完成什么。