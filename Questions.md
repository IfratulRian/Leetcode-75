# Blind 75

## 1. Array (10)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 1 | [1. Two Sum (OK) ](https://leetcode.com/problems/two-sum/) | Hash map complement | `seen[target - x]` lookup |
| 2 | [121. Best Time to Buy and Sell Stock (OK) ](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) | Single pass | Track running min, profit = price − min |
| 3 | [217. Contains Duplicate (OK) ](https://leetcode.com/problems/contains-duplicate/) | Hash set | Insert; if exists → true |
| 4 | [238. Product of Array Except Self (OK) ](https://leetcode.com/problems/product-of-array-except-self/) | Prefix × suffix | Two passes: left-products, right-products |
| 5 | [53. Maximum Subarray (OK) ](https://leetcode.com/problems/maximum-subarray/) | Kadane's | curr = max(x, curr+x); best = max(best, curr) |
| 6 | [152. Maximum Product Subarray (OK) ](https://leetcode.com/problems/maximum-product-subarray/) | Track min & max | Negative flips min ↔ max |
| 7 | [153. Find Minimum in Rotated Sorted Array (OK) ](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) | Binary search | Compare mid vs right to pick half |
| 8 | [33. Search in Rotated Sorted Array (OK) ](https://leetcode.com/problems/search-in-rotated-sorted-array/) | BS with rotation | One half is always sorted |
| 9 | [15. 3Sum](https://leetcode.com/problems/3sum/) | Sort + two pointers | Fix `i`, shrink window for pair sum |
| 10 | [11. Container With Most Water (OK) ](https://leetcode.com/problems/container-with-most-water/) | Two pointers | Move shorter wall inward |

## 2. Binary (5)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 11 | [371. Sum of Two Integers (OK) ](https://leetcode.com/problems/sum-of-two-integers/) | Bit XOR + carry | `a^b` = sum w/o carry, `(a&b)<<1` = carry |
| 12 | [191. Number of 1 Bits (OK) ](https://leetcode.com/problems/number-of-1-bits/) | `n & (n-1)` trick | Each step clears lowest set bit |
| 13 | [338. Counting Bits (OK) ](https://leetcode.com/problems/counting-bits/) | DP on bits | `dp[i] = dp[i>>1] + (i&1)` |
| 14 | [268. Missing Number (OK) ](https://leetcode.com/problems/missing-number/) | XOR or sum | XOR all indices and values |
| 15 | [190. Reverse Bits (OK) ](https://leetcode.com/problems/reverse-bits/) | Bit shift loop | Pull LSB → push to result MSB |

## 3. Dynamic Programming (11)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 16 | [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) | Fibonacci DP | `dp[i] = dp[i-1] + dp[i-2]` |
| 17 | [322. Coin Change](https://leetcode.com/problems/coin-change/) | Unbounded knapsack | `dp[a] = min(dp[a-c] + 1)` |
| 18 | [300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/) | DP O(n²) / patience sort | Tails array + binary search |
| 19 | [1143. Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/) | 2D DP grid | Match → diag+1, else max(↑, ←) |
| 20 | [139. Word Break](https://leetcode.com/problems/word-break/) | DP over prefixes | `dp[i]` true if any `dp[j]` & `s[j:i]` in dict |
| 21 | [39. Combination Sum](https://leetcode.com/problems/combination-sum/) | Backtracking | DFS, reuse `i` (unbounded), prune by remaining |
| 22 | [198. House Robber](https://leetcode.com/problems/house-robber/) | DP pick / skip | `dp[i] = max(dp[i-1], dp[i-2] + x)` |
| 23 | [213. House Robber II](https://leetcode.com/problems/house-robber-ii/) | Circular DP | Run #198 on `[0..n-2]` and `[1..n-1]` |
| 24 | [91. Decode Ways](https://leetcode.com/problems/decode-ways/) | DP on string | Check 1-digit & 2-digit validity |
| 25 | [62. Unique Paths](https://leetcode.com/problems/unique-paths/) | Grid DP | `dp[i][j] = dp[i-1][j] + dp[i][j-1]` |
| 26 | [55. Jump Game](https://leetcode.com/problems/jump-game/) | Greedy reach | Track furthest reachable index |

## 4. Graph (8)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 27 | [133. Clone Graph](https://leetcode.com/problems/clone-graph/) | DFS/BFS + map | `old → new` node map |
| 28 | [207. Course Schedule](https://leetcode.com/problems/course-schedule/) | Topo sort / cycle detect | Kahn's BFS or DFS w/ colors |
| 29 | [417. Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/) | Multi-source BFS/DFS | Reverse flow from each ocean |
| 30 | [200. Number of Islands](https://leetcode.com/problems/number-of-islands/) | DFS/BFS flood fill | Mark visited; count starts |
| 31 | [128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) | Hash set | Count only from sequence "starts" |
| 32 | [269. Alien Dictionary](https://leetcode.com/problems/alien-dictionary/) 🔒 | Topo sort | Build edges from adjacent word diffs |
| 33 | [261. Graph Valid Tree](https://leetcode.com/problems/graph-valid-tree/) 🔒 | Union-Find / DFS | Connected & `edges == n-1` |
| 34 | [323. Number of Connected Components in an Undirected Graph](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/) 🔒 | Union-Find | Count distinct roots |

## 5. Interval (5)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 35 | [57. Insert Interval](https://leetcode.com/problems/insert-interval/) | Linear scan | Before / overlap merge / after |
| 36 | [56. Merge Intervals](https://leetcode.com/problems/merge-intervals/) | Sort by start | Extend last end if overlap |
| 37 | [435. Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/) | Greedy by end | Keep earliest-ending; remove conflicts |
| 38 | [252. Meeting Rooms](https://leetcode.com/problems/meeting-rooms/) 🔒 | Sort + check | Any `start[i] < end[i-1]` → false |
| 39 | [253. Meeting Rooms II](https://leetcode.com/problems/meeting-rooms-ii/) 🔒 | Min-heap of ends | Reuse room if earliest end ≤ start |

## 6. Linked List (6)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 40 | [206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/) | 3-pointer flip | prev ← curr → next |
| 41 | [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/) | Floyd tortoise & hare | Slow/fast meet inside loop |
| 42 | [21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/) | Dummy + tail | Splice smaller head each step |
| 43 | [23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/) | Min-heap / divide & conquer | Heap of k current heads |
| 44 | [19. Remove Nth Node From End](https://leetcode.com/problems/remove-nth-node-from-end-of-list/) | Two pointers gap | Fast leads by `n`, then advance both |
| 45 | [143. Reorder List](https://leetcode.com/problems/reorder-list/) | Mid + reverse + merge | Split half, reverse 2nd, weave |

## 7. Matrix (4)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 46 | [73. Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/) | First row/col as flags | Encode zero rows/cols in-place |
| 47 | [54. Spiral Matrix](https://leetcode.com/problems/spiral-matrix/) | 4 boundaries | Shrink top/bottom/left/right |
| 48 | [48. Rotate Image](https://leetcode.com/problems/rotate-image/) | Transpose + reverse | Swap across diagonal, reverse rows |
| 49 | [79. Word Search](https://leetcode.com/problems/word-search/) | DFS + backtrack | Mark visited, restore on return |

## 8. String (10)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 50 | [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/) | Sliding window | Move left past duplicate index |
| 51 | [424. Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/) | Window + maxFreq | `len - maxFreq ≤ k` |
| 52 | [76. Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/) | Variable window + counts | Expand right, shrink left when valid |
| 53 | [242. Valid Anagram](https://leetcode.com/problems/valid-anagram/) | Count compare | 26-length array |
| 54 | [49. Group Anagrams](https://leetcode.com/problems/group-anagrams/) | Sorted-key hash | Group by sorted string / count tuple |
| 55 | [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) | Stack | Push opens, match on close |
| 56 | [125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) | Two pointers | Skip non-alnum, compare lower |
| 57 | [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/) | Expand around center | 2n−1 centers (odd & even) |
| 58 | [647. Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/) | Expand around center | Count expansions |
| 59 | [271. Encode and Decode Strings](https://leetcode.com/problems/encode-and-decode-strings/) 🔒 | Length-prefix framing | `"len#payload"` |

## 9. Tree (14)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| 60 | [104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/) | DFS recursion | `1 + max(L, R)` |
| 61 | [100. Same Tree](https://leetcode.com/problems/same-tree/) | Parallel DFS | Compare nodes & recurse |
| 62 | [226. Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/) | DFS swap | Swap L/R, recurse |
| 63 | [124. Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/) | Post-order DFS | gain = node + max(L, R, 0); update global |
| 64 | [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/) | BFS by level | Queue size = level width |
| 65 | [297. Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/) | Pre-order + null markers | Queue of tokens |
| 66 | [572. Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/) | DFS + sameTree | At each node, try match |
| 67 | [105. Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) | Recursion + index map | First preorder = root; split inorder |
| 68 | [98. Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/) | DFS with bounds | Pass `(low, high)` down |
| 69 | [230. Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/) | Inorder traversal | Stop at k-th visit |
| 70 | [235. Lowest Common Ancestor of a BST](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) | Walk by value | Split point = LCA |
| 71 | [208. Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/) | Trie nodes | 26 children + `isEnd` |
| 72 | [211. Design Add and Search Words Data Structure](https://leetcode.com/problems/design-add-and-search-words-data-structure/) | Trie + DFS for `.` | Wildcard branches all children |
| 73 | [212. Word Search II](https://leetcode.com/problems/word-search-ii/) | Trie + grid DFS | Prune trie branches as found |

## 10. Heap (3)

| # | Problem | Pattern | Visual |
|---|---------|---------|--------|
| – | [23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/) | Min-heap of heads | (cross-listed with Linked List #43) |
| 74 | [347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) | Bucket sort / heap | Buckets indexed by frequency |
| 75 | [295. Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) | Two heaps | Max-heap (low) + min-heap (high) |

