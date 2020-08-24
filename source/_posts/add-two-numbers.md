---
title: add-two-numbers
date: 2020-08-24 22:00:42
tags: leetcode
---
## 问题
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

## 解决

````java

class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

        int temp = 0;

        ListNode end = null;
        ListNode head = null;

        while (l1 != null || l2 != null) {
            final int v1 = l1 == null ? 0 : l1.val;
            final int v2 = l2 == null ? 0 : l2.val;
            if(l1 != null){
                l1 = l1.next;
            }
            if(l2 != null){
                l2 = l2.next;
            }
            final ListNode listNode = new ListNode((v1 + v2 + temp) % 10);
            temp = (v1 + v2 + temp) / 10;

            if(head == null){
                head = listNode;
            }else {
                end.next = listNode;
            }
            end = listNode;
        }

        if(temp != 0){
            end.next = new ListNode(temp);
        }
        return head;
        
    }
}
````