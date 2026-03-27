<img width="1904" height="975" alt="Screenshot 2026-03-27 200412" src="https://github.com/user-attachments/assets/29e23cb9-e003-4c8b-ab75-b5995cca7fc2" />
# Check If N and Its Double Exist

## Problem
Given an array `arr` of integers, check if there exist two indices `i` and `j` such that:

- `i != j`
- `0 <= i, j < arr.length`
- `arr[i] == 2 * arr[j]`

---

## Efficient Approach (Hash Set) — O(n)

### Idea
For each number `x`, check:
- if `2*x` already exists
- if `x` is even and `x/2` already exists

If yes → return `true`.

---

