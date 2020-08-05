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
