# 用 Python 拍摄截图并转换成 PDF

> 原文:[https://www . geesforgeks . org/take-and-convert-截图-pdf-使用-python/](https://www.geeksforgeeks.org/take-and-convert-screenshot-to-pdf-using-python/)

为了拍摄截图并转换成 PDF，首先可以使用[](https://www.geeksforgeeks.org/mouse-keyboard-automation-using-python/)**PyAutoGUI，这是 python 中的一个自动化库，可以控制鼠标、键盘，可以处理很多 GUI 控制任务。其次，转换可以使用 Python 的[**【PIL】(Python 图像库)**](https://www.geeksforgeeks.org/python-pil-image-open-method/) ，提供图像处理设施，支持多种文件格式及其转换。第二个可以用于转换的库是 [**img2pdf**](https://www.geeksforgeeks.org/python-convert-image-to-pdf-using-img2pdf-module/) ，顾名思义，它提供了图像到 pdf 的无损和更快的转换。**

### **装置**

**要安装库，请使用以下命令:**

*   ****pyautoui:****

```py
pip install PyAutoGUI
```

*   ****PIL(Python 图像库):****

```py
pip install Pillow
```

*   ****img2pdf****

```py
pip install img2pdf
```

### **方法 1**

**在这种方法中，我们使用了 PIL python 库。首先，截图是使用 python 库 **PyAutoGUI** 的**截图()** 功能拍摄的。之后，屏幕截图的输出被保存。使用 PIL 图书馆的 **open()方法**打开图像，然后 **convert()方法**将图像转换为 RGB，然后保存。给定路径中的 pdf 扩展名。或者，您也可以通过在 open()方法中提供路径来提供屏幕截图/图像。**

****注意:**使用 *r'* 是为了将字符串视为原始字符串。**

****实施:****

## **蟒蛇 3**

```py
import pyautogui
from PIL import Image

# Taking Screenshot
takeScreenshot = pyautogui.screenshot()

# The path of Screenshot and r' is used for specifying raw string
screenshotPath = r'C:\Users\Pranjal\Desktop\gfgarticle\PDF\screenshot.png'

# Saving the screenshot in the given Path
takeScreenshot.save(screenshotPath)

# Opening image
open_image = Image.open(screenshotPath)
convert_image = open_image.convert('RGB')

# Output Pdf Path
outputpdfPath = r'C:\Users\Pranjal\Desktop\gfgarticle\PDF\output.pdf'

# Saving the pdf
open_image.save(outputpdfPath)
```

****输出:****

**<video class="wp-video-shortcode" id="video-558088-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214232255/method_1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210214232255/method_1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214232255/method_1.mp4)</video>**

### **方法 2**

**在这种方法中，img2pdf 库用于转换。首先截图是使用 python**PyAutoGUI**库的截图()方法拍摄的。使用 **open()方法**和**打开截图后，传递“Rb”**作为以二进制格式打开文件的参数。之后，通过**“WB”参数**(用于二进制写入)，使用 **open()方法** bt 打开 pdf 输出文件。调用 write()函数，并将 img2pdf 的 convert()方法与截图对象一起传递。最后，两个对象都被关闭，以便刷新任何未写的信息。**

**该方法的*主要优点是与 PIL 相比速度快，并且是小尺寸无损转换。或者，您也可以通过在 open()方法中提供路径来提供屏幕截图/图像。***

****注意:**截图/图像不包含 alpha 通道，因为没有方法可以将 img2pdf 中的 RGBA 转换为 RGB。**

****实施:****

## **蟒蛇 3**

```py
import pyautogui
import img2pdf

# Taking Screenshot
takeScreenshot = pyautogui.screenshot()

# The path of Screenshot and r' is used for specifying raw string
screenshotPath = r'C:\Users\Pranjal\Desktop\gfgarticle\PDF\screenshot.png'

# Saving the screenshot in the given Path
takeScreenshot.save(screenshotPath)

# Opening Img file obj
ImgFile = open(screenshotPath, "rb")

# Opening the Pdf file obj
PdfFile = open("output.pdf", "wb")

# Converting Image File to PDF
PdfFile.write(img2pdf.convert(ImgFile))

# Closing Image File Object
ImgFile.close()

# Closing PDF File Object
PdfFile.close()
```

****输出:****

**<video class="wp-video-shortcode" id="video-558088-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214232317/method_2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210214232317/method_2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214232317/method_2.mp4)</video>**