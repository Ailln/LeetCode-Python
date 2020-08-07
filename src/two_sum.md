# 两数之和

## 1 暴力法

### 思路

1. 遍历数字序列，每遍历出一个数字 n；
2. 接着遍历后面的数字序列，判断出后面的数字有没有等于 target - n 的数字；
3. 重复 1 和 2，如果有则返回下标。

### 分析

- 时间复杂度：O(n^2)
- 空间复杂度：O(1)

### 代码

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[j] == target - nums[i]:
                    return i, j
```

## 2 两遍哈希表

### 思路

1. 第一次遍历，将数字和索引存入哈希表。
2. 第二次遍历，判断 target - nums\[j\](当前数字) 是否在哈希表中，而且此数字的索引不能和哈希表的索引相同，举例假如 nums 中包含 5，target 是 10，10-5=5 依然在哈希表中，但实际上只有一个 5。
3. 返回下标。

### 分析

- 时间复杂度：O(n)
- 空间复杂度：O(n)

### 代码

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        harsh_map = {}
        for i in range(len(nums)):
            harsh_map[nums[i]] = i

        for j in range(len(nums)):
            n = target - nums[j]
            if n in harsh_map.keys() and harsh_map[n] != j:
                return j, harsh_map[n]
```
