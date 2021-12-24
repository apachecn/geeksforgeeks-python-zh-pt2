# 链表中所有回文数字的总和

> 原文:[https://www . geeksforgeeks . org/all-sum-回文-numbers-present-in-a-link-list/](https://www.geeksforgeeks.org/sum-of-all-palindrome-numbers-present-in-a-linked-list/)

给定一个具有整数节点值的链表，任务是找到所有 [**回文数字**](https://www.geeksforgeeks.org/check-if-a-number-is-palindrome/) 的和，这些数字以节点值的形式出现。
**例:**

> **输入:**13->212->22->44->4->3
> **输出:** 285
> **解释:**回文数{22，212，44，4，3}之和为 285
> **输入:** 19 - > 22 - > 141

**方法:**为了解决这个问题，我们使用类似的方法来计算数组中所有回文的[和](https://www.geeksforgeeks.org/sum-of-all-palindrome-numbers-present-in-an-array/)。遍历链表的所有节点，检查当前节点值是否是回文。如果是这样，将值相加并存储总和。所有这些值的最终总和给出了期望的答案。
以下是上述方法的实施:

## C++

```py
// C++ program to calculate
// the sum of all palindromic
// numbers in a linked list

#include <bits/stdc++.h>
using namespace std;

// Node of the singly
// linked list
struct Node {
    int data;
    Node* next;
};

// Function to insert a node at
// the beginning of the singly
// Linked List
void push(Node** head_ref, int new_data)
{
    // allocate node
    Node* new_node = (Node*)malloc(
        sizeof(struct Node));

    // Insert the data
    new_node->data = new_data;

    // Point the new Node
    // to the current head
    new_node->next = (*head_ref);

    // Make the new Node as
    // the new head
    (*head_ref) = new_node;
}

// Function to check
// if a number n is
// palindrome or not
bool isPalin(int n)
{
    int d = 0, s = 0;
    int temp = n;
    while (n > 0) {
        d = n % 10;
        s = s * 10 + d;
        n = n / 10;
    }

    // If n is equal to
    // the its reverse
    // it is a palindrome
    return temp == s;
}

// Function to calculate
// the sum of all nodes
// which are palindrome
int sumOfpal(Node* head_1)
{
    int s = 0;
    Node* ptr = head_1;
    while (ptr != NULL) {

        // If the value of the
        // current node is
        // a palindrome
        if (isPalin(ptr->data)) {

            // Add the value
            // to the sum
            s += ptr->data;
        }
        ptr = ptr->next;
    }
    return s;
}

// Driver Code
int main()
{
    // Create the head
    // of the linked list
    Node* head1 = NULL;

    // Insert nodes into
    // the linked list
    push(&head1, 13);
    push(&head1, 212);
    push(&head1, 22);
    push(&head1, 44);
    push(&head1, 4);
    push(&head1, 3);

    // Print the sum of all
    // palindromes
    cout << sumOfpal(head1)
         << endl;
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java program to calculate
// the sum of all palindromes
// in a linked list

import java.util.*;

class GFG {

    // Node of the singly
    // linked list
    static class Node {
        int data;
        Node next;
    };

    // Function to insert a node
    // at the beginning of the
    // singly Linked List
    static Node push(Node head_ref,
                     int new_data)
    {
        // Allocate node
        Node new_node = new Node();

        // Insert the data
        new_node.data = new_data;

        // Point the current Node
        // to the current head
        new_node.next = (head_ref);

        // Make the current node
        // as the new head
        (head_ref) = new_node;

        return head_ref;
    }

    // Function to check if
    // a number is palindrome
    static boolean isPalin(int n)
    {
        int d = 0, s = 0;
        int temp = n;
        while (n > 0) {
            d = n % 10;
            s = s * 10 + d;
            n = n / 10;
        }
        // If n is equal to its
        // reverse, it is a
        // palindrome
        return temp == s;
    }

    // Function to calculate sum
    // of all nodes with value
    // which is a palindrome
    static int sumOfpal(Node head_1)
    {
        int s = 0;
        Node ptr = head_1;
        while (ptr != null) {
            // If the value of the
            // current node
            // is a palindrome
            if (isPalin(ptr.data)) {

                // Add that value to
                // the sum
                s += ptr.data;
            }
            ptr = ptr.next;
        }

        // Return the sum
        return s;
    }

    // Driver Code
    public static void main(String args[])
    {
        // Create the head
        Node head1 = null;

        // Insert nodes to the
        // Linked List
        head1 = push(head1, 13);
        head1 = push(head1, 212);
        head1 = push(head1, 22);
        head1 = push(head1, 44);
        head1 = push(head1, 4);
        head1 = push(head1, 3);

        System.out.println(
            sumOfpal(head1));
    }
}
```

## 蟒蛇 3

```py
# Python3 program to
# calculate the sum of all
# palindromes present in
# a Linked List

class Node: 

    def __init__(self, data): 
        self.data = data 
        self.next = next

# Function to insert a
# node at the beginning 
# of the singly Linked List 
def push( head_ref, new_data) :

    # Allocate node 
    new_node = Node(0) 

    # Insert data 
    new_node.data = new_data 

    # Pont to the head
    new_node.next = (head_ref) 

    # Make the new Node
    # the new head
    (head_ref) = new_node

    return head_ref

# Function to check if
# a number is palindrome
def isPalin(n) :

    d = 0; s = 0;
    temp = n;
    while (n > 0) :

        d = n % 10;
        s = s * 10 + d;
        n = n // 10;

    # If n is equal to its reverse,
    # it is a palindrome
    return s == temp;

# Function to calculate sum of
# all elements in a Linked List
# which are palindrome
def sumOfpal(head_ref1) :

    s = 0;
    ptr1 = head_ref1

    while (ptr1 != None) :
        # If the value of the
        # current node
        # is a palindrome
        if (isPalin(ptr1.data)) :

            # Add that value
            s = s + ptr1.data

        # Move to the next node
        ptr1 = ptr1.next

    # Return the final sum
    return s;

# Driver code 

# Create the Head
head1 = None

# Insert nodes 
head1 = push(head1, 13) 
head1 = push(head1, 212) 
head1 = push(head1, 22) 
head1 = push(head1, 44) 
head1 = push(head1, 4)
head1 = push(head1, 3)

print(sumOfpal(head1))
```

## C#

```py
// C# program to calculate
// the sum of all palindromes
// in a linked list
using System;

class GFG {

// Node of the singly
// linked list
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

    // Insert the data
    new_node.data = new_data;

    // Point the current Node
    // to the current head
    new_node.next = (head_ref);

    // Make the current node
    // as the new head
    (head_ref) = new_node;

    return head_ref;
}

// Function to check if
// a number is palindrome
static bool isPalin(int n)
{
    int d = 0, s = 0;
    int temp = n;

    while (n > 0)
    {
        d = n % 10;
        s = s * 10 + d;
        n = n / 10;
    }

    // If n is equal to its
    // reverse, it is a
    // palindrome
    return temp == s;
}

// Function to calculate sum
// of all nodes with value
// which is a palindrome
static int sumOfpal(Node head_1)
{
    int s = 0;
    Node ptr = head_1;

    while (ptr != null)
    {

        // If the value of the
        // current node
        // is a palindrome
        if (isPalin(ptr.data))
        {

            // Add that value to
            // the sum
            s += ptr.data;
        }
        ptr = ptr.next;
    }

    // Return the sum
    return s;
}

// Driver Code
public static void Main(String []args)
{

    // Create the head
    Node head1 = null;

    // Insert nodes to the
    // Linked List
    head1 = push(head1, 13);
    head1 = push(head1, 212);
    head1 = push(head1, 22);
    head1 = push(head1, 44);
    head1 = push(head1, 4);
    head1 = push(head1, 3);

    Console.WriteLine(sumOfpal(head1));
}
}

// This code is contributed by sapnasingh4991
```

## java 描述语言

```py
<script>
      // JavaScript program to calculate
      // the sum of all palindromes
      // in a linked list
      // Node of the singly
      // linked list
      class Node {
        constructor() {
          this.data = 0;
          this.next = null;
        }
      }

      // Function to insert a node
      // at the beginning of the
      // singly Linked List
      function push(head_ref, new_data) {
        // Allocate node
        var new_node = new Node();

        // Insert the data
        new_node.data = new_data;

        // Point the current Node
        // to the current head
        new_node.next = head_ref;

        // Make the current node
        // as the new head
        head_ref = new_node;

        return head_ref;
      }

      // Function to check if
      // a number is palindrome
      function isPalin(n) {
        var d = 0,
          s = 0;
        var temp = n;

        while (n > 0) {
          d = n % 10;
          s = s * 10 + d;
          n = parseInt(n / 10);
        }

        // If n is equal to its
        // reverse, it is a
        // palindrome
        return temp == s;
      }

      // Function to calculate sum
      // of all nodes with value
      // which is a palindrome
      function sumOfpal(head_1) {
        var s = 0;
        var ptr = head_1;

        while (ptr != null) {
          // If the value of the
          // current node
          // is a palindrome
          if (isPalin(ptr.data)) {
            // Add that value to
            // the sum
            s += ptr.data;
          }
          ptr = ptr.next;
        }

        // Return the sum
        return s;
      }

      // Driver Code
      // Create the head
      var head1 = null;

      // Insert nodes to the
      // Linked List
      head1 = push(head1, 13);
      head1 = push(head1, 212);
      head1 = push(head1, 22);
      head1 = push(head1, 44);
      head1 = push(head1, 4);
      head1 = push(head1, 3);

      document.write(sumOfpal(head1));

      // This code is contributed by rdtank.
    </script>
```

**Output:** 

```py
285
```