# 反转链表

## 1 迭代法

> 注：思路简单，代码难，需要记忆！

### 思路

1. 遍历链表。
2. 每次先暂存下一节点，然后将下一节点指向前一节点，然后把当前节点赋值给前一节点，最后再把暂存的下一节点复制给当前节点。
3. 直到当前节点为空时，返回上一节点。

### 分析

- 时间复杂度：O(n)
- 空间复杂度：O(1)

### 代码

```python
# 啰嗦的直观版本
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        curr = head
        prev = None
        while curr:
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp
        return prev

# 精简版本（记这个）
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        curr, prev = head, None
        while curr:
            curr.next, prev, curr = prev, curr, curr.next
        return prev
```
