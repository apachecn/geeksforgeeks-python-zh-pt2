# 使用 Python 中的 Selenium 将表格数据刮存到 CSV 文件中

> 原文:[https://www . geeksforgeeks . org/scratch-and-save-table-data-in-CSV-file-use-selenium-in-python/](https://www.geeksforgeeks.org/scrape-and-save-table-data-in-csv-file-using-selenium-in-python/)

**Selenium WebDriver** 是一个开源 API，允许你以真实用户的方式与浏览器交互，其脚本是用各种语言编写的，即 Python、Java、C#等。在这里，我们将使用 python 从 web 上的表中抓取数据，并将其存储为 CSV 文件。由于谷歌浏览器是最受欢迎的浏览器，为了让事情变得简单，我们将使用它。为了进一步存储数据，我们将使用 python 的 [**【熊猫】**](https://www.geeksforgeeks.org/python-pandas-dataframe/) 和 [**csv**](https://www.geeksforgeeks.org/export-pandas-dataframe-to-a-csv-file/) 模块。

**注意:**确保系统中安装了 chromedriver，并且它必须与 python 文件位于同一文件夹中。在这里可以找到 chromedriver】。

首先，我们需要[定位表格的元素，对于这个 selenium WebDriver](https://www.geeksforgeeks.org/locating-multiple-elements-in-selenium-python/)。我们将使用 **xpath** 方法，因为网页中的大多数元素都有一个独特的 [xpath](https://www.geeksforgeeks.org/locating-multiple-elements-in-selenium-python/#find_elements_by_xpath) 。

### 逐步实施:

**步骤 1:** 导入所需模块。

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.support.ui import WebDriverWait 
import time
import pandas as pd
from selenium.webdriver.support.ui import Select
from selenium.common.exceptions import NoSuchElementException
from selenium.webdriver.common.keys import Keys
import csv
```

**第二步:**用变量**驱动**初始化网页浏览器，提到[可执行文件 _ 路径](https://www.geeksforgeeks.org/selenium-python-tricks/) 作为你拥有 chromedriver 文件的位置，指向需要的 URL。

## 蟒蛇 3

```
driver = webdriver.Chrome(
  executable_path='/usr/lib/chromium-browser/chromedriver') 
driver.get('https://www.geeksforgeeks.org/selenium-python-tutorial/')
```

**第三步:**等待网页加载。您可以通过[隐式 _wait( )](https://www.geeksforgeeks.org/implicitly_wait-driver-method-selenium-python/) 方法来实现。满载时，最大化窗口使用[最大化 _ 窗口()](https://www.geeksforgeeks.org/maximize_window-driver-method-selenium-python/)。

## 蟒蛇 3

```
driver.implicitly_wait(10)
driver.maximize_window()
```

**步骤 4:** 尝试在行的 xpath 中找到一个模式，并使用 [find_element_by_xpath()](https://www.geeksforgeeks.org/find_element_by_xpath-driver-method-selenium-python/) 定位它们，并运行一个循环来找到所有的表格单元格，并通过添加**将其转换为文本。text()** 位于通过广义 xpath 定位的每个元素的末尾。

## 蟒蛇 3

```
while(1): 

    try:
        method=driver.find_element_by_xpath('//*[@id="post-427949"]\
        /div[3]/table[2]/tbody/tr['+str(r)+']/td[1]').text  
        Desc=driver.find_element_by_xpath('//*[@id="post-427949"]\
        /div[3]/table[2]/tbody/tr['+str(r)+']/td[2]').text 
        Table_dict={
        'Method':method,
        'Description':Desc
        }
        templist.append(Table_dict) 
        df=pd.DataFrame(templist)
        r+=1

    except NoSuchElementException: 
        break
```

**第 5 步:**将数据框导出到 CSV 文件，关闭浏览器的出口。

## 蟒蛇 3

```
df.to_csv('table.csv')
driver.close()
```

下面是完整的实现:

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.support.ui import WebDriverWait 
import time
import pandas as pd
from selenium.webdriver.support.ui import Select
from selenium.common.exceptions import NoSuchElementException
from selenium.webdriver.common.keys import Keys
import csv

driver = webdriver.Chrome(executable_path = 
                          '/usr/lib/chromium-browser/chromedriver') 

driver.get('https://www.geeksforgeeks.org/selenium-python-tutorial/')
driver.implicitly_wait(10)
driver.maximize_window()
r=1
templist = [] 

while(1): 
    try:
        method=driver.find_element_by_xpath('//*[@id="post-427949"]\
        /div[3]/table[2]/tbody/tr['+str(r)+']/td[1]').text 
        Desc=driver.find_element_by_xpath('//*[@id="post-427949"]/\
        div[3]/table[2]/tbody/tr['+str(r)+']/td[2]').text

        Table_dict={ 'Method': method,
                    'Description':Desc}

        templist.append(Table_dict) 
        df = pd.DataFrame(templist)

        r + = 1

    # if there are no more table data to scrape
    except NoSuchElementException: 
        break

# saving the dataframe to a csv
df.to_csv('table.csv') 
driver.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-634922-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210622043728/table.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210622043728/table.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210622043728/table.mp4)</video>