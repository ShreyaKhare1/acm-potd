<img width="1906" height="976" alt="Screenshot 2026-03-23 182418" src="https://github.com/user-attachments/assets/a7fa7751-f5fe-442f-90a2-3536fb9c114b" />
# Two Sum Problem (Java Solution)

## 📌 Problem Statement
Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.

- Each input has exactly one solution.
- You may not use the same element twice.
- Return the answer in any order.

---

## 💡 Approach
This solution uses a **brute-force approach**:

- Loop through each element in the array.
- For every element, check all the elements after it.
- If the sum equals the target, store the indices.

---

## 🧑‍💻 Code Implementation

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int arr[] = new int[2];
        for(int i = 0; i < nums.length; i++){
            for(int j = i + 1; j < nums.length; j++){
                if(nums[i] + nums[j] == target){
                    arr[0] = i;
                    arr[1] = j;
                }
            }
        }
        return arr;
    }
}
