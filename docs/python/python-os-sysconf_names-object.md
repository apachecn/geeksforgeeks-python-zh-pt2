# Python | OS . sysconf _ name 对象

> 原文:[https://www . geesforgeks . org/python-OS-sysconf _ names-object/](https://www.geeksforgeeks.org/python-os-sysconf_names-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***Python 中的 os.sysconf_names*** 对象是由 ***os.sysconf()*** 方法接受为参数的名称到主机操作系统为这些名称定义的整数值的字典映射。该对象用于确定系统已知的一组名称。
**注意:*****OS . sysconf _ name***对象仅在 UNIX 平台上可用。

> ***语法:***OS . sysconf _ name
> ***参数:*** 这是一个不可调用的对象。因此，不需要任何参数。
> ***返回类型:*** 该对象返回一个字典，该字典将操作系统已知的一组名称作为键，将它们对应的整数值(由操作系统定义)作为值。

**代码:**使用 os.sysconf_names 对象

## 蟒蛇 3

```py
# Python program to explain os.sysconf_names object

# importing os module
import os

# importing pprint module
import pprint

# Get the dictionary mapping of
# names accepted by os.sysconf() method
# to their corresponding integer values
# defined by host OS
names = os.sysconf_names

# print the dictionary mapping
# using pprint
print("The list of names known to the operating system:")
pprint.pprint(names, width = 1, height = 1)
```

**Output:** 

```py
The list of names known to the operating system:
{'SC_2_CHAR_TERM': 95,
 'SC_2_C_BIND': 47,
 'SC_2_C_DEV': 48,
 'SC_2_C_VERSION': 96,
 'SC_2_FORT_DEV': 49,
 'SC_2_FORT_RUN': 50,
 'SC_2_LOCALEDEF': 52,
 'SC_2_SW_DEV': 51,
 'SC_2_UPE': 97,
 'SC_2_VERSION': 46,
 'SC_AIO_LISTIO_MAX': 23,
 'SC_AIO_MAX': 24,
 'SC_AIO_PRIO_DELTA_MAX': 25,
 'SC_ARG_MAX': 0,
 'SC_ASYNCHRONOUS_IO': 12,
 'SC_ATEXIT_MAX': 87,
 'SC_AVPHYS_PAGES': 86,
 'SC_BC_BASE_MAX': 36,
 'SC_BC_DIM_MAX': 37,
 'SC_BC_SCALE_MAX': 38,
 'SC_BC_STRING_MAX': 39,
 'SC_CHARCLASS_NAME_MAX': 45,
 'SC_CHAR_BIT': 101,
 'SC_CHAR_MAX': 102,
 'SC_CHAR_MIN': 103,
 'SC_CHILD_MAX': 1,
 'SC_CLK_TCK': 2,
 'SC_COLL_WEIGHTS_MAX': 40,
 'SC_DELAYTIMER_MAX': 26,
 'SC_EQUIV_CLASS_MAX': 41,
 'SC_EXPR_NEST_MAX': 42,
 'SC_FSYNC': 15,
 'SC_GETGR_R_SIZE_MAX': 69,
 'SC_GETPW_R_SIZE_MAX': 70,
 'SC_INT_MAX': 104,
 'SC_INT_MIN': 105,
 'SC_IOV_MAX': 60,
 'SC_JOB_CONTROL': 7,
 'SC_LINE_MAX': 43,
 'SC_LOGIN_NAME_MAX': 71,
 'SC_LONG_BIT': 106,
 'SC_MAPPED_FILES': 16,
 'SC_MB_LEN_MAX': 108,
 'SC_MEMLOCK': 17,
 'SC_MEMLOCK_RANGE': 18,
 'SC_MEMORY_PROTECTION': 19,
 'SC_MESSAGE_PASSING': 20,
 'SC_MQ_OPEN_MAX': 27,
 'SC_MQ_PRIO_MAX': 28,
 'SC_NGROUPS_MAX': 3,
 'SC_NL_ARGMAX': 119,
 'SC_NL_LANGMAX': 120,
 'SC_NL_MSGMAX': 121,
 'SC_NL_NMAX': 122,
 'SC_NL_SETMAX': 123,
 'SC_NL_TEXTMAX': 124,
 'SC_NPROCESSORS_CONF': 83,
 'SC_NPROCESSORS_ONLN': 84,
 'SC_NZERO': 109,
 'SC_OPEN_MAX': 4,
 'SC_PAGESIZE': 30,
 'SC_PAGE_SIZE': 30,
 'SC_PASS_MAX': 88,
 'SC_PHYS_PAGES': 85,
 'SC_PII': 53,
 'SC_PII_INTERNET': 56,
 'SC_PII_INTERNET_DGRAM': 62,
 'SC_PII_INTERNET_STREAM': 61,
 'SC_PII_OSI': 57,
 'SC_PII_OSI_CLTS': 64,
 'SC_PII_OSI_COTS': 63,
 'SC_PII_OSI_M': 65,
 'SC_PII_SOCKET': 55,
 'SC_PII_XTI': 54,
 'SC_POLL': 58,
 'SC_PRIORITIZED_IO': 13,
 'SC_PRIORITY_SCHEDULING': 10,
 'SC_REALTIME_SIGNALS': 9,
 'SC_RE_DUP_MAX': 44,
 'SC_RTSIG_MAX': 31,
 'SC_SAVED_IDS': 8,
 'SC_SCHAR_MAX': 111,
 'SC_SCHAR_MIN': 112,
 'SC_SELECT': 59,
 'SC_SEMAPHORES': 21,
 'SC_SEM_NSEMS_MAX': 32,
 'SC_SEM_VALUE_MAX': 33,
 'SC_SHARED_MEMORY_OBJECTS': 22,
 'SC_SHRT_MAX': 113,
 'SC_SHRT_MIN': 114,
 'SC_SIGQUEUE_MAX': 34,
 'SC_SSIZE_MAX': 110,
 'SC_STREAM_MAX': 5,
 'SC_SYNCHRONIZED_IO': 14,
 'SC_THREADS': 67,
 'SC_THREAD_ATTR_STACKADDR': 77,
 'SC_THREAD_ATTR_STACKSIZE': 78,
 'SC_THREAD_DESTRUCTOR_ITERATIONS': 73,
 'SC_THREAD_KEYS_MAX': 74,
 'SC_THREAD_PRIORITY_SCHEDULING': 79,
 'SC_THREAD_PRIO_INHERIT': 80,
 'SC_THREAD_PRIO_PROTECT': 81,
 'SC_THREAD_PROCESS_SHARED': 82,
 'SC_THREAD_SAFE_FUNCTIONS': 68,
 'SC_THREAD_STACK_MIN': 75,
 'SC_THREAD_THREADS_MAX': 76,
 'SC_TIMERS': 11,
 'SC_TIMER_MAX': 35,
 'SC_TTY_NAME_MAX': 72,
 'SC_TZNAME_MAX': 6,
 'SC_T_IOV_MAX': 66,
 'SC_UCHAR_MAX': 115,
 'SC_UINT_MAX': 116,
 'SC_UIO_MAXIOV': 60,
 'SC_ULONG_MAX': 117,
 'SC_USHRT_MAX': 118,
 'SC_VERSION': 29,
 'SC_WORD_BIT': 107,
 'SC_XBS5_ILP32_OFF32': 125,
 'SC_XBS5_ILP32_OFFBIG': 126,
 'SC_XBS5_LP64_OFF64': 127,
 'SC_XBS5_LPBIG_OFFBIG': 128,
 'SC_XOPEN_CRYPT': 92,
 'SC_XOPEN_ENH_I18N': 93,
 'SC_XOPEN_LEGACY': 129,
 'SC_XOPEN_REALTIME': 130,
 'SC_XOPEN_REALTIME_THREADS': 131,
 'SC_XOPEN_SHM': 94,
 'SC_XOPEN_UNIX': 91,
 'SC_XOPEN_VERSION': 89,
 'SC_XOPEN_XCU_VERSION': 90,
 'SC_XOPEN_XPG2': 98,
 'SC_XOPEN_XPG3': 99,
 'SC_XOPEN_XPG4': 100}
```