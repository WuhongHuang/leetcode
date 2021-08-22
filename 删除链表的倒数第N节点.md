## 问题描述
给你一个链表，删除链表的倒数第 n 个结点，并且返回链表的头结点
---
## 解法一
暴力求解。第一步遍历链表得到链表节点个数。第二步，遍历链表到要删除节点前一节点时，跳出遍历，将删除节点的下一节点作为其前驱节点将要指向的节点。完成删除。
应该注意，避免头节点判断边界条件可使用人工设置哑节点方法，但应记得返回时应返回哑节点下一节点开始。
## 代码如下
```python
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        def getLength(head: ListNode) -> int:
            length = 0
            while head:
                length += 1
                head = head.next
            return length
        
        dummy = ListNode(0, head)
        length = getLength(head)
        cur = dummy
        for i in range(1, length - n + 1):
            cur = cur.next
        cur.next = cur.next.next
        return dummy.next
```
