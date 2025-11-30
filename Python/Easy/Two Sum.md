 [LeetCode](https://leetcode.com/problems/two-sum/).

# 🧠 Two Sum — Optimized Hash Map Solution (O(n) Time)

**LeetCode Problem #1 — Two Sum**
This repository explains the optimized **O(n)** solution using a **Hash Map**, along with diagrams, reasoning, and complexity analysis.

---

## 📘 Problem Statement

Given an array of integers `nums` and an integer `target`, return the **indices of the two numbers** such that:

```
nums[i] + nums[j] == target
```

You may assume:

* Exactly **one** valid answer exists
* Same element cannot be used twice
* Return the answer in **any order**

---

# 🚀 Optimized Solution (Recommended)

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        seen = {}  # value → index

        for i, num in enumerate(nums):
            diff = target - num

            if diff in seen:
                return [seen[diff], i]

            seen[num] = i
```

---

# 🧩 How the Hash Map Method Works

The idea is:

1. For each number, compute the difference:

   ```
   diff = target - nums[i]
   ```
2. If `diff` already exists in the hash map → we found the answer
3. Otherwise, store the current number in the map for future lookup

Result:
We solve the problem in **one pass**, using a hash map for constant-time lookups.

---

# 🖼️ Visual Explanation

### 📌 High-Level Visualization

### 📌 Step-By-Step Example

Input:

```
nums = [2, 7, 11, 15]
target = 9
```

1. **i = 0**, num = 2

   * diff = 7
   * HashMap = {}
   * Not found → store `{2: 0}`

2. **i = 1**, num = 7

   * diff = 2
   * HashMap = {2: 0}
   * Found! → return `[0, 1]`

---

# ⚡ Why Hash Map (O(n)) Is Better Than Brute Force (O(n²))

## ❌ Brute Force Approach

```
for i in range(n):
    for j in range(i+1, n):
```

* Checks all possible pairs
* Takes **quadratic time**
* Extremely slow for large arrays

## ✅ Hash Map Approach (Optimized)

* Only **one loop**
* Constant-time hash map lookup (`O(1)`)
* Total operations = **O(n)**
* Handles millions of elements easily

---

# 📊 Time & Space Complexity

| Approach               | Time  | Space |
| ---------------------- | ----- | ----- |
| **Brute Force**        | O(n²) | O(1)  |
| **Optimized Hash Map** | O(n)  | O(n)  |

We trade a bit of memory for massive speed improvement — a common and worthwhile optimization.

---

# 📂 Files in This Repository

```
📁 two-sum-optimized/
│── README.md                # This documentation
│── solution.py              # The optimized code
│── brute_force.py           # O(n²) version for comparison
│── example_diagrams/        # (Optional) store local diagrams
```

---

# 🧠 Summary

* The **hash map** approach is the fastest and most scalable method
* Uses a **space–time tradeoff** to reduce time from **O(n²) → O(n)**
* Required knowledge for coding interviews

---



If you'd like, I can also turn this into a **complete GitHub repo structure** including a folder of example tests.

