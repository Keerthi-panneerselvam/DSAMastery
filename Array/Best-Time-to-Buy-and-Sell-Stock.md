# Simple Stock Problem Walkthrough

## 📋 Problem
**LeetCode #121**: Given stock prices for each day, find the maximum profit from buying once and selling once.

**Example**: `[7, 1, 5, 3, 6, 4]` → Answer: `5` (buy at 1, sell at 6)

---

## 🔍 Step 1: What kind of problem? (30 seconds)
**Keywords:** "maximum profit" 
**Type:** OPTIMIZATION problem

---

## ⏱️ Step 2: What are the limits? (15 seconds)
- Array can be large → Need fast solution O(n)
- Must buy BEFORE selling → Order matters
- Only one transaction → Simple case

---

## 🎯 Step 3: Which pattern? (10 seconds)
**Pattern:** Track minimum price + maximum profit
**Why:** We need the cheapest buy price and best profit

---

## ✅ Step 4: Does this work? (15 seconds)
- ✅ Finds maximum profit? YES
- ✅ Fast enough O(n)? YES  
- ✅ Handles buy-before-sell? YES
- ✅ Easy to code? YES

---

## 💻 Step 5: How to code it? (10 seconds)

```python
def maxProfit(prices):
    min_price = prices[0]    # Cheapest so far
    max_profit = 0           # Best profit so far
    
    for price in prices[1:]:
        profit = price - min_price       # Profit today
        max_profit = max(max_profit, profit)  # Update best
        min_price = min(min_price, price)     # Update cheapest
    
    return max_profit
```

---

## 🏃‍♂️ Quick Example
```
Prices: [7, 1, 5, 3, 6, 4]

Day 0: price=7 → min_price=7, max_profit=0
Day 1: price=1 → min_price=1, max_profit=0  
Day 2: price=5 → profit=4 → max_profit=4
Day 3: price=3 → profit=2 → max_profit=4
Day 4: price=6 → profit=5 → max_profit=5  ✨
Day 5: price=4 → profit=3 → max_profit=5

Answer: 5
```

---

## 🎯 Key Idea
**Always track:**
1. **Cheapest price seen so far** (best time to buy)
2. **Highest profit seen so far** (best result)

**Time:** O(n) - one pass  
**Space:** O(1) - two variables

---

## 🚀 Why The 5-Step Process Works
**Total time:** 80 seconds from problem to solution!

1. **Keywords** → Identified OPTIMIZATION
2. **Constraints** → Need O(n) solution  
3. **Pattern** → Single pass tracking
4. **Validate** → Confirmed it works
5. **Code** → Simple 6-line solution

The systematic approach eliminated guesswork and led straight to the optimal solution!
