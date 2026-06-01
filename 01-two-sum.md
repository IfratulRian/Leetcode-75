# 1. Two Sum

> [LeetCode #1 — Two Sum](https://leetcode.com/problems/two-sum/) · Easy

Given an array `nums` and an integer `target`, return indices of the two numbers that add up to `target`. Each input has exactly one solution, and you may not use the same element twice.

```
Input:  nums = [2, 7, 11, 15], target = 9
Output: [0, 1]          # nums[0] + nums[1] == 9
```

---

## Intuition

For every number `x`, the partner we need is `target - x`. If we've already seen that partner earlier in the array, we have our answer. So we walk the array once and remember every number we've seen along with its index in a hash map.

```
nums   = [2, 7, 11, 15],  target = 9
        ↑
i=0: x=2,  need 7  → not seen, store {2:0}
i=1: x=7,  need 2  → seen at index 0 → return [0, 1]
```

---

## Optimal Solution — Hash Map (one pass)

**Time:** `O(n)` · **Space:** `O(n)`

```python
from typing import List

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        seen: dict[int, int] = {}          # value -> index
        for i, x in enumerate(nums):
            complement = target - x
            if complement in seen:
                return [seen[complement], i]
            seen[x] = i
        return []                          # unreachable per constraints
```

### Step-by-step

1. Create an empty dict `seen` mapping value → index.
2. Iterate over `nums` with both index and value.
3. For each `x`, compute `complement = target - x`.
4. If `complement` is already in `seen`, we've found the pair — return `[seen[complement], i]`.
5. Otherwise, store the current value: `seen[x] = i` and continue.

### Why one pass works

We only need the *earlier* index when we find a match. Storing `x` **after** the lookup ensures we never pair a number with itself at the same index.

---

## Complexity

| Approach | Time | Space | Notes |
|---|---|---|---|
| Brute force (nested loops) | `O(n²)` | `O(1)` | Try every pair |
| Sort + two pointers | `O(n log n)` | `O(n)` | Loses original indices — needs index tracking |
| **Hash map (one pass)** | **`O(n)`** | **`O(n)`** | ✅ Optimal for this problem |

Hash lookup is `O(1)` average; we touch each element at most once.

---

## Edge cases

- **Negatives / zero:** works — hashing handles any int.
- **Duplicates** (e.g. `nums=[3,3]`, `target=6`): when we reach the second `3`, `complement=3` is already in `seen` from the first index → returns `[0, 1]`.
- **No solution:** problem guarantees one exists, so the trailing `return []` is just a safety net.
