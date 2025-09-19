## 📋 Problem
**LeetCode #122**: You can buy and sell stock multiple times (but can't hold multiple stocks at once). Find the maximum profit.

**Example**: `[7,1,5,3,6,4]` → Answer: `7` (buy at 1, sell at 5, buy at 3, sell at 6: profit = 4+3 = 7)

---

## 🔍 Step 1: What kind of problem? (30 seconds)
**Keywords:** "maximum profit", "multiple times"
**Type:** OPTIMIZATION problem (but with multiple transactions allowed)

---

## ⏱️ Step 2: What are the limits? (15 seconds)
- Array can be large → Need fast solution O(n)
- Multiple transactions allowed → Different from Stock I
- Can't hold multiple stocks → Must sell before buying again
- No limit on number of transactions → Greedy approach possible

---

## 🎯 Step 3: Which pattern? (10 seconds)
**Pattern:** GREEDY - Capture every profitable opportunity
**Key Insight:** If tomorrow's price > today's price, buy today and sell tomorrow!
**Why:** With unlimited transactions, we can capture every upward movement

---

## ✅ Step 4: Does this work? (15 seconds)
- ✅ Finds maximum profit? YES - captures all gains
- ✅ Fast enough O(n)? YES - single pass
- ✅ Handles constraints? YES - greedy is optimal here
- ✅ Easy to code? YES - very simple logic

---

## 💻 Step 5: How to code it? (10 seconds)## 🏃‍♂️ Quick Example
```
Prices: [7, 1, 5, 3, 6, 4]

Day 0→1: 7→1 (down) → Skip (no profit)
Day 1→2: 1→5 (up)   → Take profit = 4
Day 2→3: 5→3 (down) → Skip (no profit)  
Day 3→4: 3→6 (up)   → Take profit = 3
Day 4→5: 6→4 (down) → Skip (no profit)

Total profit: 4 + 3 = 7 ✨
```

---

## 🎯 Key Difference from Stock I

| **Stock I** | **Stock II** |
|-------------|--------------|
| One transaction only | Unlimited transactions |
| Track min price + max profit | Capture every upward move |
| `O(n)` time, `O(1)` space | `O(n)` time, `O(1)` space |

---

## 🧠 Why Greedy Works Here

**The Magic Insight:** 
- If we can do unlimited transactions, we should capture EVERY profitable opportunity
- Every time price goes up tomorrow, buy today and sell tomorrow
- This is equivalent to buying at every local minimum and selling at every local maximum

**Mathematical Proof:**
- Any complex strategy can be broken down into these simple day-to-day gains
- Missing any upward movement = missed profit
- Therefore, greedy = optimal!

---

## 🚀 Why The 5-Step Process Works Again

**Total time:** 80 seconds from problem to solution!

1. **Keywords** → OPTIMIZATION with multiple transactions
2. **Constraints** → Unlimited transactions changes the game
3. **Pattern** → GREEDY (capture every gain)
4. **Validate** → Greedy is provably optimal here
5. **Code** → Super simple: add up all positive differences

```python
# LeetCode #122: Best Time to Buy and Sell Stock II
# Pattern: Greedy - Capture Every Gain

def maxProfit(prices):
    """
    Find max profit with unlimited transactions.
    
    Key Idea: Buy before every price increase, sell before every decrease
    """
    if len(prices) < 2:
        return 0
    
    total_profit = 0
    
    for i in range(1, len(prices)):
        # If price goes up, capture the profit
        if prices[i] > prices[i-1]:
            total_profit += prices[i] - prices[i-1]
    
    return total_profit

# Even simpler one-liner version:
def maxProfit_oneliner(prices):
    return sum(max(0, prices[i] - prices[i-1]) for i in range(1, len(prices)))

# Test it
prices = [7, 1, 5, 3, 6, 4]
print(f"Prices: {prices}")
print(f"Max Profit: {maxProfit(prices)}")  # Output: 7

# How it works step by step:
# Day 0→1: 7→1 (down) → profit = 0
# Day 1→2: 1→5 (up)   → profit = 4  (buy at 1, sell at 5)
# Day 2→3: 5→3 (down) → profit = 0  
# Day 3→4: 3→6 (up)   → profit = 3  (buy at 3, sell at 6)
# Day 4→5: 6→4 (down) → profit = 0
# Total: 4 + 3 = 7

# Another example
prices2 = [1, 2, 3, 4, 5]
print(f"Prices: {prices2}")
print(f"Max Profit: {maxProfit(prices2)}")  # Output: 4 (buy at 1, sell at 5)

# Visualization of the greedy approach:
def visualize(prices):
    print(f"Prices: {prices}")
    total = 0
    transactions = []
    
    for i in range(1, len(prices)):
        if prices[i] > prices[i-1]:
            profit = prices[i] - prices[i-1]
            total += profit
            transactions.append(f"Buy at {prices[i-1]}, sell at {prices[i]} → +{profit}")
    
    for transaction in transactions:
        print(f"  {transaction}")
    print(f"Total Profit: {total}")
    return total

print("\nVisualization:")
visualize([7, 1, 5, 3, 6, 4])
```
The systematic approach immediately identified that unlimited transactions makes this a completely different problem requiring a greedy solution instead of the tracking approach from Stock I!
