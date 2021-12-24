# Python 中的 Sched 模块

> 原文:[https://www.geeksforgeeks.org/sched-module-in-python/](https://www.geeksforgeeks.org/sched-module-in-python/)

**Sched** 模块是标准库，可用于创建僵尸工具等监控和自动化应用。sched 模块实现了一个通用的事件调度器，用于在特定时间运行任务。它提供了类似于 windows 或 Linux 中的任务调度器这样的工具，但主要优势是有了 Python 自带的 sched 模块**平台差异可以忽略**。

**示例:**

```py
# Python program for Creating 
# an event scheduler

import sched
import time

# Creating an instance of the
# scheduler class
scheduler = sched.scheduler(time.time, 
                            time.sleep)
```

#### 调度程序实例可用的基本方法

*   **scheduler.enter():** Events can be scheduled to run after a delay, or at a specific time. To schedule them with a delay, `enter()` method is used.

    > **语法:** scheduler.enter(延迟、优先级、动作、参数=()、kwargs={})
    > 
    > **参数:**
    > **延迟:**代表延迟时间的数字
    > **优先级:**优先级值
    > **动作:**调用函数
    > **参数:**一组参数

    **示例:**

    ```py
    import sched
    import time

    # instance is created
    scheduler = sched.scheduler(time.time,
                                time.sleep)

    # function to print time 
    # and name of the event
    def print_event(name):
        print('EVENT:', time.time(), name)

    # printing starting time
    print ('START:', time.time())

    # first event with delay of
    # 1 second
    e1 = scheduler.enter(1, 1, 
                         print_event, ('1 st', ))

    # second event with delay of
    # 2 seconds
    e1 = scheduler.enter(2, 1, 
                         print_event, (' 2nd', ))

    # executing the events
    scheduler.run()
    ```

    **输出:**

    ```py
    START: 1580389814.152131
    EVENT: 1580389815.1548214 1 st
    EVENT: 1580389816.1533117  2nd

    ```

*   **scheduler.enterabs()** The `enterabs()` time adds an event to the internal queue of the scheduler, as the `run()` method of a scheduler is called, the entries in the queue of a scheduler are executed one by one.

    > **语法:** scheduler.enterabs(时间、优先级、动作、参数=()、kwargs={})
    > 
    > **参数:**
    > **时间:**必须执行事件/动作的时间
    > **优先级:**事件的优先级
    > **动作:**构成事件的函数
    > **参数:**事件函数的位置参数
    > **kwargs:** 事件函数的关键字参数字典

    **示例:**

    ```py
    # library imported
    import sched
    import time

    # instance is created
    scheduler = sched.scheduler(time.time,
                                time.sleep)

    # function to print time and
    # name of the event
    def print_event(name):
        print('EVENT:', time.time(), name)

    # printing starting time
    print ('START:', time.time())

    # event x with delay of 1 second
    # enters queue using enterabs method
    e_x = scheduler.enterabs(time.time()+1, 1,
                             print_event, 
                             argument = ("Event X", ));

    # executing the events
    scheduler.run()
    ```

    **输出:**

    ```py
    START: 1580389960.5845037
    EVENT: 1580389961.5875661 Event X

    ```

*   **scheduler.cancel()** Remove the event from the queue. If the event is not an event currently in the queue, this method will raise a `ValueError`.

    > **语法:**调度程序.取消(事件)
    > 
    > **参数:**
    > **事件:**应该移除的事件。

    ```py
    import sched
    import time

    # instance is created
    scheduler = sched.scheduler(time.time,
                                time.sleep)

    # function to print time and
    # name of the event
    def print_event(name):
        print('EVENT:', time.time(), name)

    # printing starting time
    print ('START:', time.time())

    # first event with delay 
    # of 1 second
    e1 = scheduler.enter(1, 1, 
                         print_event,
                         ('1 st', ))

    # second event with delay 
    # of 2 seconds
    e2 = scheduler.enter(2, 1, 
                         print_event,
                         (' 2nd', ))

    # removing 1st event from 
    # the event queue
    scheduler.cancel(e1)

    # executing the events
    scheduler.run()
    ```

    **输出:**

    ```py
    START: 1580390119.54074
    EVENT: 1580390121.5439944  2nd

    ```

*   **scheduler.empty()** It return True if the event queue is empty. It takes no argument.

    **示例:**

    ```py
    import sched
    import time

    # instance is created
    scheduler = sched.scheduler(time.time,
                                time.sleep)

    # function to print time 
    # and name of the event
    def print_event(name):
        print('EVENT:', time.time(), name)

    # printing starting time
    print ('START:', time.time())

    # checking if event queue is
    # empty or not
    print(scheduler.empty())

    # event entering into queue
    e1 = scheduler.enter(2, 1,
                         print_event,
                         ('1 st', ))

    # checking if event queue is 
    # empty or not
    print(scheduler.empty())

    # executing the events
    scheduler.run()
    ```

    **输出:**

    ```py
    START: 1580390318.1343799
    True
    False
    EVENT: 1580390320.136075 1 st

    ```

*   **scheduler.queue** Read-only attribute returning a list of upcoming events in the order they will be run. Each event is shown as a named tuple with the following fields: time, priority, action, argument, kwargs.

    ```py
    # library imported
    import sched
    import time

    # instance is created
    scheduler = sched.scheduler(time.time,
                                time.sleep)

    # function to print time 
    # and name of the event
    def print_event(name):
        print('EVENT:', time.time(), name)

    # printing starting time
    print ('START:', time.time())

    # event entering into queue
    e1 = scheduler.enter(2, 1,
                         print_event, 
                         ('1 st', ))

    # printing the details of
    # upcoming events in event queue
    print(scheduler.queue)

    # executing the events
    scheduler.run()
    ```

    **输出:**

    > START: 1580390446.8743565
    > 【事件(时间=1580390448.8743565，优先级=1，动作=，参数=('第 1 '，)，kwargs = { })】
    > 事件:1580390448.876916 第 1