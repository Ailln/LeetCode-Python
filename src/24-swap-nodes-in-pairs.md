# 两两交换链表中的节点

## 1 递归法

### 思路

略

### 分析

- 时间复杂度：O(n)
- 空间复杂度：O(n)

### 代码

```python
class Solution:
    def swapPairs(self, head: ListNode) -> ListNode:
        if not head or not head.next:
            return head
        new_head = head.next
        head.next = self.swapPairs(new_head.next)
        new_head.next = head
        return new_head
```
