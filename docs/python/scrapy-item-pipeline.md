# 报废–项目管道

> 原文:[https://www.geeksforgeeks.org/scrapy-item-pipeline/](https://www.geeksforgeeks.org/scrapy-item-pipeline/)

**Scrapy** 是一个网页抓取库，用于抓取、解析和收集网页数据。对于所有这些功能，我们有一个 **pipelines.py** 文件，该文件用于通过顺序执行的各种组件(称为**类**)来处理刮擦的数据。

在本文中，我们将学习为这个管道文件定义的方法，并将展示不同的例子。

## 设置项目

让我们，首先，创建一个剪贴簿项目。为此，请确保系统中安装了 Python 和 PIP。然后一个接一个地运行下面给定的命令，创建一个类似于我们将在本文中使用的项目。

**步骤 1:** 我们首先在一个名为 GFGScrapy 的文件夹中创建一个虚拟环境，并在那里激活该虚拟环境。

```py
# To create a folder named GFGScrapy
mkdir GFGScrapy
cd GFGScrapy

# making virtual env there.
virtualenv
cd scripts

# activating it
activate
cd..
```

因此，在运行所有这些命令后，我们将获得如下所示的输出:

![](img/80e0a362bdd2211ca1cd31cdea0dc8c5.png)

创建虚拟环境

**第二步:**现在是时候创建一个剪贴簿项目了。为此，请确保系统中是否安装了 scrapy。如果没有安装，请使用下面给出的命令进行安装。

```py
pip install scrapy
```

现在要创建一个剪贴簿项目，使用下面给出的命令，并创建一个蜘蛛。

```py
# projEct name is scrapytutorial
scrapy startproject scrapytutorial
cd scrapytutorial
scrapy genspider spider_to_crawl https://quotes.toscrape.com
```

然后项目目录的输出看起来像图像中给出的一样。(如果你想更多地了解和熟悉一个剪贴簿项目，请参考[这个](https://www.geeksforgeeks.org/scrapy-command-line-tools/))。

![](img/38c528d93d57ae803f6bc5341792e582.png)

目录结构

让我们看看蜘蛛文件夹中的文件。这是我们在其中编写我们的蜘蛛必须爬行的网址的文件，也是一个名为 parse()的方法，用于描述应该如何处理蜘蛛抓取的数据。

该文件由上面使用的 **scrapy genspider** 命令自动生成。该文件以蜘蛛的名字命名。下面给出的是生成的默认文件。

![](img/960837dfca8205e1e4cf0d936a2747d0.png)

spider_to_crawl.py

**项目管道**是一种写在 pipelines.py 文件中的管道方法，用于对刮出的数据依次进行下述操作。下面列出了我们可以对刮下的物品执行的各种操作:

*   解析抓取的文件或数据。
*   将收集到的数据存储在数据库中。
*   验证和检查获得的数据。
*   将文件从一种格式转换为另一种格式。例如到 JSON。

我们将在下面的示例中执行其中一些操作。

操作按顺序执行**，因为我们使用**设置. py** 文件来描述操作的执行顺序。即，我们可以提到首先执行哪个操作，然后执行哪个操作。这通常是在我们对项目执行几个操作时完成的。**

**让我们首先看看默认管道文件的内部结构。下面是该文件中提到的默认类。**

**![](img/083ec2ee5a8e28f6cd647bba92a83edb.png)

默认管道. py 文件** 

**为了对项目执行不同的操作，我们必须声明一个独立的组件(文件中的类)，它由各种方法组成，用于执行操作。默认情况下，管道文件有一个以项目名称命名的类。我们还可以创建自己的类来编写它们必须执行的操作。如果任何管道文件包含多个类，那么我们应该明确地提到它们的执行顺序。组件的结构定义如下:**

**每个组件(类)必须有一个名为 **process_item()的**默认**函数。**这是默认方法，总是在管道文件的类或组件中调用。**

> ****语法:** process_item(自身、项目、蜘蛛)**
> 
> ****参数:****
> 
> *   ****self :** 这是对调用方法的 self 对象的引用。**
> *   ****物品:**这些是蜘蛛刮的物品清单**
> *   ****蜘蛛:**提到了用来刮的蜘蛛。**
> 
> **此方法的返回类型是已修改或未修改的项对象，否则如果在项中发现任何错误，将会引发错误。**
> 
> **此方法还用于调用此类中可用于修改或存储数据的其他方法。**

****附加方法:**这些方法与上面提到的自身对象方法一起使用，以获得对项目的额外控制。**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| open_spider(自我，蜘蛛) | 打开的蜘蛛对象和对自身对象的引用是参数。(这些是 python 语言的默认情况)。除了用于进行某些更改、打开文件或关闭文件之外，不返回任何内容。 |
| close_spider(自我，蜘蛛) | 关闭的蜘蛛对象和对自身对象的引用。它也用于修改文件或打开或关闭文件。 |
| from_crawler(cls，crawler) | 指定的爬网程序对象。此方法用于为 scrapy 设置的所有核心组件提供管道可访问性，以便管道可以增强其功能， |

</figure>

**除了所有这些方法之外，我们还可以创建自己的方法来执行更多的操作，比如如果我们想存储一些数据，那么我们可以有一个组件来初始化数据库并在其中创建表，另一个组件可能会在那里将数据添加到数据库中。**

**在我们继续并参考示例之前，需要注意的一点是，我们应该在文件夹结构的**设置. py** 中注册**管道. py** 文件的所有组件(类)。这样做是为了维护要执行的组件的顺序，从而产生准确的结果。**

### ****创建要在文件中传递的项目。****

**还有一点需要注意的是，我们将要求描述我们的项目将包含在 **items.py** 文件中。因此我们的 **items.py** 文件包含下面给出的代码:**

## **蟒蛇 3**

```py
# Define here the models for your scraped items
import scrapy

class ScrapytutorialItem(scrapy.Item):

    # define the fields for your item here like:
    # name = scrapy.Field()
    Quote = scrapy.Field()     #only one field that it of Quote.
```