---
tags: [LeetCode, 算法, Python3]
aliases: []
---



## 1️⃣ 基本信息
- **题目路径**：[Two Sum](Two Sum)
- **题目难度**：简单 
- **标签/分类**：数组

---

## 2️⃣ 题目描述
- **输入**：
- **输出**：
- **样例**：
给定一个数组,和一个目标数.查询数组中是否存两个数的和是否等于目标数.
如果等于就返回两个数的下标,如果没有就返回空数组.

---

## 3️⃣ 解题思路
### 思路1（暴力/常规解法）
- 算法原理：罗列出所有两个 数的组合.然后查看是否有和等于目标值.如果等于返回下标,
- 时间复杂度： O(n^2)
- 空间复杂度：O(1)

### 思路2（优化/进阶）
- 算法原理：对数组进行排序,然后让最高和最低两个数的和.如果比目标值小,就将左下标右移,如果比目标值大,那么就将右下标左移.如果相等就返回下标.由于需要返回下标,所以需要拷贝出一个下标数组idx,然后对下标数组排序,但是比较和交换的依据是nums[i].最终得到
- 时间复杂度：
- 空间复杂度：

---

## 4️⃣ Python3 技巧点
- **语法技巧**：
  - 例：列表生成式 `[x*x for x in nums]`
  - 例：字典操作 `dict.get(key, default)`
  - 内置函数：`zip`, `enumerate`, `sorted`, `heapq`
- **数据结构**：
  - `deque` 双端队列
  - `set` 与 `dict` 的差异
- **常用方法**：
  - 切片 `nums[i:j]`
  - `lambda` + `sorted`/`heapq`
- **注意事项**：
  - 浅拷贝和深拷贝
  - 默认可变参数问题

---

## 5️⃣ 算法技巧点
- **算法类别**：回溯 / 动态规划 / 贪心 / 二分 / DFS / BFS / 双指针
- **常用模板**：
  - 回溯模板：
    ```python
    def backtrack(path, choices):
        if 满足条件:
            res.append(path)
            return
        for choice in choices:
            backtrack(path + [choice], choices - ...)
    ```
  - 动态规划模板：
    ```python
    dp = [0] * n
    for i in range(n):
        dp[i] = min/max/... dp[j] + ...
    ```

---

## 6️⃣ 代码实现
```python
class Solution:
    def function_name(self, params):
        # TODO: 实现代码
        pass
