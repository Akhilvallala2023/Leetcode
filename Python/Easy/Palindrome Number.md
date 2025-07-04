# Palindrome Number - LeetCode Problem

This repository contains a solution to the **Palindrome Number** problem from [LeetCode](https://leetcode.com/problems/palindrome-number/).

---

## 🧩 Problem Statement

Given an integer `x`, return `true` if `x` is a **palindrome**, and `false` otherwise.

A palindrome is a number that reads the same forward and backward.

---

## 🧪 Examples

### Example 1
Input: x = 121
Output: true
Explanation: 121 reads the same forward and backward.


### Example 2
Input: x = 10
Output: false
Explanation: From right to left, it becomes 01, which is not equal to 10.


---

## 🧾 Constraints

- `-2^31 <= x <= 2^31 - 1`

---

## ✅ Approach 1: Convert Integer to String (Simple)

### ✔ Time Complexity: O(n)  
### ✔ Space Complexity: O(n)

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        x_str = str(x)
        return x_str == x_str[::-1]
```

#Follow-up: Solve Without Converting to a String

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        # Negative numbers are not palindrome
        # Numbers ending in 0 are not palindrome unless the number is 0
        if x < 0 or (x % 10 == 0 and x != 0):
            return False

        reverted = 0
        while x > reverted:
            reverted = reverted * 10 + x % 10
            x //= 10

        # When length is even: x == reverted
        # When length is odd: x == reverted // 10
        return x == reverted or x == reverted // 10
```
