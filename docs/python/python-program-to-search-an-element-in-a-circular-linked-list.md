# 在循环链表中搜索元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-search-一个循环链表中的元素/](https://www.geeksforgeeks.org/python-program-to-search-an-element-in-a-circular-linked-list/)

链表是一种线性数据结构，其中每个节点都有一个数据部分和指向下一个节点的地址部分。循环链表是一种链表，其中最后一个节点指向第一个节点，形成一个节点圈。

**例:**

```
Input: CList = 6->5->4->3->2, find = 3
Output: Element is present

Input: CList = 6->5->4->3->2, find = 1
Output: Element is not present
```

### 在循环链表中搜索元素

例如，如果要搜索的关键字是 30，链表是 5->4->3->2，那么函数应该返回 false。如果要搜索的关键字是 4，那么函数应该返回 true。

### **进场:**

1.  初始化节点指针，temp = head。
2.  初始化计数器 f=0(检查该元素是否存在于链表中)。
3.  如果标题为空，则打印列表为空。
4.  否则开始遍历链表，如果在链表中找到元素，则在 f 中递增
5.  如果计数器为零，则找不到打印元素。
6.  否则存在打印元素。

**以下是上述方法的实现:**

## 蟒 3

```
# Python program to Search an Element
# in a Circular Linked List

# Class to define node of the linked list    
class Node: 
    def __init__(self,data):    
        self.data = data;
        self.next = None;

class CircularLinkedList:

    # Declaring Circular Linked List
    def __init__(self):    
        self.head = Node(None);    
        self.tail = Node(None);    
        self.head.next = self.tail;    
        self.tail.next = self.head;    

    # Adds new nodes to the Circular Linked List
    def add(self,data):    

        # Declares a new node to be added
        newNode = Node(data); 

        # Checks if the Circular
        # Linked List is empty
        if self.head.data is None:

            # If list is empty then new node
            # will be the first node
            # to be added in the Circular Linked List
            self.head = newNode;
            self.tail = newNode;
            newNode.next = self.head;

        else:
            # If a node is already present then
            # tail of the last node will point to
            # new node
            self.tail.next = newNode;

            # New node will become new tail
            self.tail = newNode;

            # New Tail will point to the head
            self.tail.next = self.head;    

    # Function to search the element in the 
    # Circular Linked List
    def findNode(self,element):

        # Pointing the head to start the search
        current = self.head;
        i = 1;

        # Declaring f = 0
        f = 0;    
        # Check if the list is empty or not    
        if(self.head == None):
            print("Empty list"); 
        else:
            while(True):     
                # Comparing the elements
                # of each node to the
                # element to be searched
                if(current.data ==  element): 

                    # If the element is present
                    # then incrementing f
                    f += 1;    
                    break;

                # Jumping to next node
                current = current.next;    
                i = i + 1;    

                # If we reach the head
                # again then element is not 
                # present in the list so 
                # we will break the loop
                if(current == self.head):    
                    break;    

            # Checking the value of f
            if(f > 0):    
                print("element is present");    
            else:    
                print("element is not present");    

# Driver Code
if __name__ == '__main__':

    # Creating a Circular Linked List
    '''
    Circular Linked List we will be working on:
    1 -> 2 -> 3 -> 4 -> 5 -> 6
    '''
    circularLinkedList = CircularLinkedList();

    #Adding nodes to the list    
    circularLinkedList.add(1);
    circularLinkedList.add(2);
    circularLinkedList.add(3);
    circularLinkedList.add(4);
    circularLinkedList.add(5);
    circularLinkedList.add(6);

    # Searching for node 2 in the list    
    circularLinkedList.findNode(2);

    #Searching for node in the list    
    circularLinkedList.findNode(7);
```

**输出:**

```
element is present
element is not present
```

**时间复杂度:** O(N)，其中 N 为循环链表的长度。