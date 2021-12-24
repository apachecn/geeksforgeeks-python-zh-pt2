# Python |时间表库

> 原文:[https://www.geeksforgeeks.org/python-schedule-library/](https://www.geeksforgeeks.org/python-schedule-library/)

**`Schedule`** 是使用构建器模式进行配置的周期性作业的进程内调度程序。Schedule 允许您使用简单、人性化的语法，以预定的时间间隔定期运行 Python 函数(或任何其他可调用的函数)。

计划库用于在每天的特定时间或一周的特定日期计划任务。我们还可以设置 24 小时格式的时间，即任务应该运行的时间。基本上，计划库将您的系统时间与您设置的计划时间相匹配。一旦计划时间和系统时间匹配，就调用作业功能(计划的命令功能)。

**安装**

```
 $ pip install schedule 
```

#### 时间表。调度程序*类*

*   **`schedule.every(interval=1)` :** 在默认调度程序实例上调用每。安排新的定期作业。
*   **`schedule.run_pending()` :** 调用在默认调度程序实例上运行 _ 挂起。运行所有计划运行的作业。
*   **`schedule.run_all(delay_seconds=0)` :** 调用在默认调度程序实例上运行。运行所有作业，无论它们是否计划运行。
*   **`schedule.idle_seconds()` :** 在默认调度程序实例上调用 idle_seconds。
*   **`schedule.next_run()` :** 调用默认调度程序实例上的 next_run。下一个作业应该运行的日期时间。
*   **`schedule.cancel_job(job)` :** 调用默认调度程序实例上的 cancel_job。删除计划的作业。

#### 时间表。作业(间隔，调度程序=无)*类*

调度程序使用的定期作业。

> **参数:**
> 
> **间隔:**某个时间单位的数量
> **调度程序:**一旦在 Job.do()中完成配置，该作业将向其注册的调度程序实例。

**计划工作的基本方法**

*   **`at(time_str)` :** Schedule the job every day at a specific time. Calling this is only valid for jobs scheduled to run every N day(s).

    **参数:**time _ str–XX:YY 格式的字符串。
    **返回:**调用的作业实例

*   **`do(job_func, *args, **kwargs)` :** Specifies the job_func that should be called every time the job runs. Any additional arguments are passed on to job_func when the job runs.

    **参数:**job _ func–要调度的函数
    **返回:**被调用的作业实例

*   **`run()` :** 运行作业并立即重新计划。
    **返回:**job _ func 返回的返回值
*   **`to(latest)` :** 安排作业以不规则(随机)间隔运行。比如每(A)。至(B)。秒每 N 秒执行一次作业功能，使得 A < = N < = B。

让我们看看实现

```
# Schedule Library imported
import schedule
import time

# Functions setup
def sudo_placement():
    print("Get ready for Sudo Placement at Geeksforgeeks")

def good_luck():
    print("Good Luck for Test")

def work():
    print("Study and work hard")

def bedtime():
    print("It is bed time go rest")

def geeks():
    print("Shaurya says Geeksforgeeks")

# Task scheduling
# After every 10mins geeks() is called. 
schedule.every(10).minutes.do(geeks)

# After every hour geeks() is called.
schedule.every().hour.do(geeks)

# Every day at 12am or 00:00 time bedtime() is called.
schedule.every().day.at("00:00").do(bedtime)

# After every 5 to 10mins in between run work()
schedule.every(5).to(10).minutes.do(work)

# Every monday good_luck() is called
schedule.every().monday.do(good_luck)

# Every tuesday at 18:00 sudo_placement() is called
schedule.every().tuesday.at("18:00").do(sudo_placement)

# Loop so that the scheduling task
# keeps on running all time.
while True:

    # Checks whether a scheduled task 
    # is pending to run or not
    schedule.run_pending()
    time.sleep(1)
```

**参考:**[https://schedule.readthedocs.io/en/stable/api.html](https://schedule.readthedocs.io/en/stable/api.html)