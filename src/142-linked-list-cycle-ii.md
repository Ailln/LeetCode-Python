# 环形链表 II

## 1 快慢指针

### 思路

快指针走了 f = 2nb，慢指针走了 s = nb，慢指针还需要走 a 步就可以到达起点。

### 分析

- 时间复杂度：O(n)
- 空间复杂度：O(1)

### 代码

```python
class Solution:
    def detectCycle(self, head: ListNode) -> ListNode:
        slow, fast = head, head

        while True:
            if not fast or not fast.next: 
                return None

            slow = slow.next
            fast = fast.next.next

            if slow == fast:
                break

        fast = head
        while slow != fast:
            fast = fast.next
            slow = slow.next

        return slow
```
