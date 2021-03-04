# 环形链表

## 1 快慢指针

### 思路

一快一慢，如果存在环，快指针一定会追上慢指针。

### 分析

- 时间复杂度：O(n)
- 空间复杂度：O(1)

### 代码

```python
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        if not head or not head.next:
            return False
        
        slow = head
        fast = head.next

        while slow != fast:
            if not fast or not fast.next:
                return False
            slow = slow.next
            fast = fast.next.next
        
        return True
```
