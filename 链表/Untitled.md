#  

# 反转链表

## Recursive！Recursive！and Recursive！

Reverse a singly linked list.

**Example:**

```c++
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?

## Mine (0 ms)

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        if ( head == null || head.next == null ){
            return head;
        }
        
        else {
            ListNode newHead = reverseList ( head.next );
            head.next.next = head;
            head.next = null;
        
            return newHead;
        }
    }
}
```

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gcw4emurn2j30u013yqc1.jpg" alt="Screen Shot 2020-03-16 at 10.06.56 PM" style="zoom: 50%;" />
$$
by :https://www.jianshu.com/p/f7534f8d7bf2
$$

> 递归真是博大精深啊！！！



## Standard Answer

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;

        while (curr != null) {
            ListNode nextTemp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextTemp;
        }
        return prev;        
    } 
}
```

> 哇\_(:з」∠)\_车轮战啊这是！！！但是好理解多了。