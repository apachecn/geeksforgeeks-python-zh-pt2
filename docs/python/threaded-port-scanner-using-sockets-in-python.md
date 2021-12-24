# Python 中使用套接字的线程端口扫描器

> 原文:[https://www . geesforgeks . org/threaded-port-scanner-use-sockets-in-python/](https://www.geeksforgeeks.org/threaded-port-scanner-using-sockets-in-python/)

端口扫描可能真的很慢，但在大多数情况下，它不是过程密集型的。因此，我们可以使用线程来提高我们的速度。可能有数千个可能的端口。如果每个端口扫描需要 5-15 秒，那么如果不使用线程，我们可能会有很长的等待时间。

### **穿线**

线程是一个复杂的话题，但它可以被分解并概念化为一种方法，在这种方法中，如果处理器经历空闲时间，我们可以告诉计算机执行另一项任务。在端口扫描的情况下，我们花费大量时间等待服务器的响应。当我们等待的时候，我们可以做别的事情。这就是线程的用途。

**例:**在这个程序中，我们可以扫描一定范围内的多个端口。

## 蟒蛇 3

```
import threading
from queue import Queue
import time
import socket

# a print_lock is used to prevent "double"
# modification of shared variables this is
# used so that while one thread is using a
# variable others cannot access it Once it
# is done, the thread releases the print_lock.
# In order to use it, we want to specify a
# print_lock per thing you wish to print_lock.
print_lock = threading.Lock()

# ip = socket.gethostbyname(target)
target = 'localhost'

def portscan(port):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    try:
        con = s.connect((target, port))
        with print_lock:
            print('port is open', port)
        con.close()
    except:
        print('port is close', port)

# The threader thread pulls a worker 
# from a queue and processes it
def threader():
    while True:
        # gets a worker from the queue
        worker = q.get()

        # Run the example job with the available 
        # worker in queue (thread)
        portscan(worker)

        # completed with the job
        q.task_done()

# Creating the queue and threader
q = Queue()

# number of threads are we going to allow for
for x in range(4):
    t = threading.Thread(target=threader)

    # classifying as a daemon, so they it will
    # die when the main dies
    t.daemon = True

    # begins, must come after daemon definition
    t.start()

start = time.time()

# 10 jobs assigned.
for worker in range(1, 10):
    q.put(worker)

# wait till the thread terminates.
q.join()
```

**输出:**

```
port is close 2
port is close port is close 4
port is closeport is close 1
 53

port is close 6port is close
 7
port is close 8
port is close 9
```