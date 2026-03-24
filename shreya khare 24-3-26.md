# Best Time to Buy and Sell Stock (Java Solution)

## 📌 Problem Statement
You are given an array `prices` where `prices[i]` is the price of a given stock on the `i-th` day.

You want to maximize your profit by choosing:
- One day to **buy** a stock  
- A different day in the future to **sell** that stock  

Return the **maximum profit** you can achieve. If no profit is possible, return `0`.

---

## 💡 Approach
This solution uses an **optimized single-pass approach**:
<img width="1908" height="971" alt="Screenshot 2026-03-24 183341" src="https://github.com/user-attachments/assets/5d508d21-bc9a-4710-aa03-a4c444d17c62" />

- Track the **minimum price** seen so far.
- For each day:
  - Calculate the potential profit.
  - Update the maximum profit if it's higher.
- This ensures we always buy at the lowest price before selling.

---

## 🧑‍💻 Code Implementation

```java
class Solution {
    public int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;
        
        for(int i = 0; i < prices.length; i++){
            if(prices[i] < minPrice){
                minPrice = prices[i];
            }
            
            int profit = prices[i] - minPrice;
            
            if(profit > maxProfit){
                maxProfit = profit;
            }
        }
        
        return maxProfit;
    }
}
