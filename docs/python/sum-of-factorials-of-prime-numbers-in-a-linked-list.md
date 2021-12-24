# 链表中素数的阶乘之和

> 原文:[https://www . geeksforgeeks . org/链表中素数的阶乘和/](https://www.geeksforgeeks.org/sum-of-factorials-of-prime-numbers-in-a-linked-list/)

给定一个由 **N** 个整数组成的[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)，任务是找出链表中每个素元素的阶乘之和。
**例:**

> **输入:**L1 = 4->6->2->12->3
> T3】输出:8
> T6】说明:
> 质数为 2 和 3，遂为 2！+ 3!= 2 + 6 = 8.
> **输入:**L1 = 7->4->5
> **输出:** 5160
> **解释:**
> 质数为 7 和 5，故名 7！+ 5!= 5160.

**方法:**按照以下步骤解决上述问题:

*   实现一个函数**阶乘(n)** ，使得[找到 **N** 的阶乘](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)。
*   初始化一个变量**和= 0** 。现在，遍历给定的列表，检查每个节点是否是[素数](https://www.geeksforgeeks.org/prime-numbers/)。
*   如果节点是质数，则更新 **sum = sum +阶乘(节点)**，否则将节点移到下一个。
*   最后打印计算出的**和**。

以下是上述方法的实现:

## C++

```py
// C++ implementation to fine Sum of
// prime factorials in a Linked list

#include <bits/stdc++.h>
using namespace std;

// Node of the singly linked list
struct Node {
    int data;
    Node* next;
};

// Function to insert a node
// at the beginning
// of the singly Linked List
void push(Node** head_ref, int new_data)
{
    // allocate node
    Node* new_node
        = (Node*)malloc(
            sizeof(struct Node));

    // put in the data
    new_node->data = new_data;

    // link the old list
    // off the new node
    new_node->next = (*head_ref);

    // move the head to point
    // to the new node
    (*head_ref) = new_node;
}

// Function to return the factorial of N
int factorial(int n)
{
    int f = 1;
    for (int i = 1; i <= n; i++) {
        f *= i;
    }
    return f;
}

// Function to check if number is prime
bool isPrime(int n)
{
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for (int i = 5; i * i <= n; i = i + 6)
        if (n % i == 0
            || n % (i + 2) == 0)
            return false;

    return true;
}

// Function to return the sum of
// factorials of the LL elements
int sumFactorial(Node* head_1)
{

    // To store the required sum
    Node* ptr = head_1;
    int s = 0;
    while (ptr != NULL) {

        // Add factorial of all the elements
        if (isPrime(ptr->data)) {
            s += factorial(ptr->data);
            ptr = ptr->next;
        }
        else
            ptr = ptr->next;
    }
    return s;
}

// Driver code
int main()
{
    Node* head1 = NULL;

    push(&head1, 4);
    push(&head1, 6);
    push(&head1, 2);
    push(&head1, 12);
    push(&head1, 3);

    cout << sumFactorial(head1);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation to find Sum of
// prime factorials in a Linked list

import java.util.*;

class GFG {

    // Node of the singly linked list
    static class Node {
        int data;
        Node next;
    };

    // Function to insert a
    // node at the beginning
    // of the singly Linked List
    static Node push(
        Node head_ref,
        int new_data)
    {
        // allocate node
        Node new_node = new Node();

        // put in the data
        new_node.data = new_data;

        // link the old list
        // off the new node
        new_node.next = (head_ref);

        // move the head to point
        // to the new node
        (head_ref) = new_node;
        return head_ref;
    }

    // Function to return
    // the factorial of n
    static int factorial(int n)
    {
        int f = 1;
        for (int i = 1; i <= n; i++) {
            f *= i;
        }
        return f;
    }

    // Function to check if number is prime
    static boolean isPrime(int n)
    {
        // Corner cases
        if (n <= 1)
            return false;
        if (n <= 3)
            return true;

        if (n % 2 == 0 || n % 3 == 0)
            return false;

        for (int i = 5; i * i <= n; i = i + 6)
            if (n % i == 0
                || n % (i + 2) == 0)
                return false;

        return true;
    }

    // Function to return the sum of
    // factorials of the LL elements
    static int sumFactorial(Node head_1)
    {
        Node ptr = head_1;
        // To store the required sum
        int s = 0;
        while (ptr != null) {

            // Add factorial of
            // all the elements
            if (isPrime(ptr.data)) {
                s += factorial(ptr.data);
                ptr = ptr.next;
            }
            else {
                ptr = ptr.next;
            }
        }
        return s;
    }

    // Driver Code
    public static void main(String args[])
    {

        Node head1 = null;

        head1 = push(head1, 4);
        head1 = push(head1, 6);
        head1 = push(head1, 2);
        head1 = push(head1, 12);
        head1 = push(head1, 3);
        int ans = sumFactorial(head1);

        System.out.println(ans);
    }
}
```

## 蟒蛇 3

```py
# Python implementation of the approach
class Node: 

    def __init__(self, data): 
        self.data = data 
        self.next = next

# Function to insert a
# node at the beginning 
# of the singly Linked List 
def push( head_ref, new_data) :

    # allocate node 
    new_node = Node(0) 

    # put in the data 
    new_node.data = new_data 

    # link the old list
    # off the new node 
    new_node.next = (head_ref) 

    # move the head to
    # point to the new node 
    (head_ref) = new_node
    return head_ref

def factorial(n):
    f = 1;
    for i in range(1, n + 1):
        f *= i;
    return f;
  # prime for def 
def isPrime(n):

    # Corner cases
    if (n <= 1):
        return False
    if (n <= 3):
        return True

    # This is checked so that we can skip
    # middle five numbers in below loop
    if (n % 2 == 0 or n % 3 == 0):
        return False
    i = 5
    while ( i * i <= n ):
        if (n % i == 0
            or n % (i + 2) == 0):
            return False
        i += 6;

    return True

# Function to return the sum of
# factorials of the LL elements
def sumFactorial(head_ref1):

    # To store the required sum
    s = 0;
    ptr1 = head_ref1
    while (ptr1 != None) :

        # Add factorial of all the elements
        if(isPrime(ptr1.data)):
            s += factorial(ptr1.data);
            ptr1 = ptr1.next
        else:
            ptr1 = ptr1.next
    return s;
# Driver code 
# start with the empty list 
head1 = None
# create the linked list 
head1 = push(head1, 4) 
head1 = push(head1, 6) 
head1 = push(head1, 2) 
head1 = push(head1, 12) 
head1 = push(head1, 3)
ans = sumFactorial(head1)
print(ans)
```

## C#

```py
// C# implementation to find Sum of
// prime factorials in a Linked list
using System;

class GFG{

// Node of the singly linked list
class Node
{
    public int data;
    public Node next;
};

// Function to insert a node
// at the beginning of the
// singly Linked List
static Node push(Node head_ref,
                 int new_data)
{

    // Allocate node
    Node new_node = new Node();

    // Put in the data
    new_node.data = new_data;

    // Link the old list
    // off the new node
    new_node.next = (head_ref);

    // Move the head to point
    // to the new node
    (head_ref) = new_node;
    return head_ref;
}

// Function to return
// the factorial of n
static int factorial(int n)
{
    int f = 1;
    for(int i = 1; i <= n; i++)
    {
       f *= i;
    }
    return f;
}

// Function to check if number
// is prime
static bool isPrime(int n)
{

    // Corner cases
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for(int i = 5; i * i <= n;
            i = i + 6)
       if (n % i == 0 ||
           n % (i + 2) == 0)
           return false;

    return true;
}

// Function to return the sum of
// factorials of the LL elements
static int sumFactorial(Node head_1)
{
    Node ptr = head_1;

    // To store the required sum
    int s = 0;
    while (ptr != null)
    {

        // Add factorial of
        // all the elements
        if (isPrime(ptr.data))
        {
            s += factorial(ptr.data);
            ptr = ptr.next;
        }
        else
        {
            ptr = ptr.next;
        }
    }
    return s;
}

// Driver Code
public static void Main(String []args)
{
    Node head1 = null;

    head1 = push(head1, 4);
    head1 = push(head1, 6);
    head1 = push(head1, 2);
    head1 = push(head1, 12);
    head1 = push(head1, 3);

    int ans = sumFactorial(head1);

    Console.WriteLine(ans);
}
}

// This code is contributed by Amit Katiyar
```

## java 描述语言

```py
<script>
      // JavaScript implementation to find Sum of
      // prime factorials in a Linked list
      // Node of the singly linked list
      class Node {
        constructor() {
          this.data = 0;
          this.next = null;
        }
      }

      // Function to insert a node
      // at the beginning of the
      // singly Linked List
      function push(head_ref, new_data)
      {

        // Allocate node
        var new_node = new Node();

        // Put in the data
        new_node.data = new_data;

        // Link the old list
        // off the new node
        new_node.next = head_ref;

        // Move the head to point
        // to the new node
        head_ref = new_node;
        return head_ref;
      }

      // Function to return
      // the factorial of n
      function factorial(n) {
        var f = 1;
        for (var i = 1; i <= n; i++) {
          f *= i;
        }
        return f;
      }

      // Function to check if number
      // is prime
      function isPrime(n) {
        // Corner cases
        if (n <= 1) return false;
        if (n <= 3) return true;

        if (n % 2 == 0 || n % 3 == 0) return false;

        for (var i = 5; i * i <= n; i = i + 6)
          if (n % i == 0 || n % (i + 2) == 0) return false;

        return true;
      }

      // Function to return the sum of
      // factorials of the LL elements
      function sumFactorial(head_1) {
        var ptr = head_1;

        // To store the required sum
        var s = 0;
        while (ptr != null)
        {

          // Add factorial of
          // all the elements
          if (isPrime(ptr.data))
          {
            s += factorial(ptr.data);
            ptr = ptr.next;
          } else {
            ptr = ptr.next;
          }
        }
        return s;
      }

      // Driver Code
      var head1 = null;

      head1 = push(head1, 4);
      head1 = push(head1, 6);
      head1 = push(head1, 2);
      head1 = push(head1, 12);
      head1 = push(head1, 3);

      var ans = sumFactorial(head1);

      document.write(ans);

      // This code is contributed by rdtank.
    </script>
```

**Output:** 

```py
8
```