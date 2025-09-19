# Array Pattern Solving Guide - Complete

## 🎯 THE GOLDEN RULE
**"Every array problem has EXACTLY ONE optimal pattern. Follow these 5 steps to find it EVERY TIME."**

---

## 📝 STEP 1: EXTRACT KEYWORDS & CLASSIFY
**Time: 30 seconds | Goal: Identify problem category**

### 1.1 Circle These Keywords in the Problem:

#### STRUCTURE KEYWORDS:
- [ ] sorted, ascending, descending, rotated
- [ ] duplicate, unique, distinct
- [ ] contiguous, consecutive, adjacent
- [ ] range [1,n], range [0,n-1]

#### ACTION KEYWORDS:
- [ ] find, search, locate, identify
- [ ] count, frequency, occurrence
- [ ] sum, product, difference, target
- [ ] maximum, minimum, largest, smallest
- [ ] merge, combine, intersection
- [ ] remove, delete, replace, modify

#### RELATIONSHIP KEYWORDS:
- [ ] pair, triplet, two numbers, three numbers
- [ ] subarray, substring, subsequence
- [ ] next greater, next smaller, previous
- [ ] increasing, decreasing, monotonic
- [ ] overlap, interval, meeting
- [ ] permutation, combination, subset

### 1.2 Classify into ONE Primary Category:

- **SEARCH**: find, locate, search, exists
- **PAIR/TARGET**: pair, two sum, target, complement  
- **SUBARRAY**: contiguous, subarray, window, range
- **FREQUENCY**: count, duplicate, frequency, occurrence
- **STRUCTURE**: next greater, stack, monotonic
- **INTERVAL**: merge, overlap, meeting, schedule
- **GENERATION**: permutation, combination, subset
- **OPTIMIZATION**: maximum, minimum, best, optimal

**Example**: "Find two numbers in array that add up to target"
- Keywords: `find`, `two numbers`, `target`
- Category: **PAIR/TARGET**

---

## 🔍 STEP 2: CONSTRAINT ANALYSIS
**Time: 15 seconds | Goal: Eliminate impossible patterns**

### 2.1 Check Array Size Constraint:

| Array Size | Acceptable Complexity | Available Patterns |
|------------|---------------------|-------------------|
| n ≤ 20 | O(2ⁿ) or O(n!) | Backtracking possible |
| n ≤ 100 | O(n³) | Triple nested loops OK |
| n ≤ 1,000 | O(n²) | Double nested loops OK |
| n ≤ 10,000 | O(n log n) or better | Must sort or use heap |
| n ≤ 100,000 | O(n log n) or better | Hash map, sorting |
| n ≤ 1,000,000 | O(n) or O(n log n) | Hash map, single pass |
| n > 1,000,000 | O(log n) or O(n) | Binary search, hash map |

### 2.2 Check Special Properties:
- [ ] Array is sorted → Binary Search, Two Pointers possible
- [ ] Array has duplicates → Need special handling
- [ ] Need original indices → Cannot sort (use Hash Map)
- [ ] Can modify input → In-place algorithms possible
- [ ] Values in range [1,n] → Cyclic Sort possible

**Example**: Array size n ≤ 10⁵, need original indices
- Eliminated: O(n²) solutions, sorting-based approaches
- Possible: Hash Map O(n), Binary Search if sorted

---

## ⚡ STEP 3: INSTANT PATTERN DECISION
**Time: 10 seconds | Goal: Pick the ONE correct pattern**

### Use This Decision Matrix:

| Category + Constraints | Pattern | Confidence |
|----------------------|---------|-----------|
| SEARCH + sorted array | Binary Search | 100% |
| PAIR/TARGET + need indices | Hash Map | 100% |
| PAIR/TARGET + can sort | Two Pointers | 100% |
| SUBARRAY + fixed size | Fixed Sliding Window | 100% |
| SUBARRAY + variable size | Variable Sliding Window | 100% |
| SUBARRAY + sum equals K | Prefix Sum + Hash Map | 100% |
| FREQUENCY + counting | Hash Map | 100% |
| FREQUENCY + range [1,n] | Cyclic Sort | 100% |
| STRUCTURE + next greater | Monotonic Stack | 100% |
| INTERVAL + merge/overlap | Sort + Merge | 100% |
| GENERATION + all possibilities | Backtracking | 100% |
| OPTIMIZATION + subproblems | Dynamic Programming | 90% |

### 3.1 Apply the Matrix:
1. Find your category from Step 1
2. Match with constraints from Step 2  
3. Get your pattern with confidence level

**Example**: PAIR/TARGET + need indices = **Hash Map (100%)**

---

## 🧠 STEP 4: PATTERN VALIDATION
**Time: 15 seconds | Goal: Confirm the pattern is correct**

### 4.1 Quick Validation Checklist:
- ✅ Does this pattern solve the core problem?
- ✅ Does it meet the time complexity requirement?
- ✅ Does it handle the given constraints?
- ✅ Can I implement this pattern confidently?
- ✅ Does it handle edge cases naturally?

### 4.2 Red Flags to Watch For:
- ❌ Pattern needs O(n²) but n > 1000
- ❌ Pattern requires sorting but need original indices
- ❌ Pattern assumes sorted array but array isn't sorted
- ❌ Pattern needs extra space but space is constrained
- ❌ Pattern is too complex for the problem size

### 4.3 If Validation Fails:
- Go back to Step 3 and pick the second-best pattern
- Reconsider the problem category in Step 1
- Check if you missed any constraints in Step 2

**Example**: Hash Map for Two Sum
- ✅ Solves finding pairs with target sum
- ✅ O(n) time meets constraint n ≤ 10⁵
- ✅ Preserves original indices
- ✅ I can implement Hash Map
- ✅ Handles duplicates and edge cases

---

## 💡 STEP 5: IMPLEMENTATION APPROACH
**Time: 10 seconds | Goal: Plan the implementation**

### 5.1 Choose Implementation Strategy:

#### HASH MAP:
- [ ] What to store as key? What as value?
- [ ] When to check for existence?
- [ ] How to handle duplicates?

#### TWO POINTERS:
- [ ] Start positions? (both ends vs same start)
- [ ] Movement condition? (sum comparison)  
- [ ] Termination condition?

#### SLIDING WINDOW:
- [ ] Expansion condition?
- [ ] Contraction condition?
- [ ] When to update result?

#### BINARY SEARCH:
- [ ] Search space? (indices vs values)
- [ ] Target condition?
- [ ] Left/right boundary updates?

#### STACK:
- [ ] What to push? (values vs indices)
- [ ] When to pop? (condition check)
- [ ] Monotonic increasing or decreasing?

### 5.2 Plan the Code Structure:
1. Initialize data structures
2. Main algorithm loop
3. Handle result extraction
4. Return in required format

**Example**: Hash Map for Two Sum
- Key: array value, Value: index
- Check existence: if (target - current) in map
- Handle duplicates: store after checking
- Structure: map = {}, loop through array, return indices

---

## 🚀 COMPLETE WALKTHROUGH EXAMPLE

**Problem**: "Given an array of integers and a target, return indices of two numbers that add up to target."

### Step 1: Extract & Classify (30s)
- Keywords: `integers`, `target`, `indices`, `two numbers`, `add up`
- Category: **PAIR/TARGET**

### Step 2: Constraint Analysis (15s)  
- n ≤ 10⁴ (assume), need indices → Cannot sort
- Need O(n) or O(n log n) solution

### Step 3: Pattern Decision (10s)
- PAIR/TARGET + need indices = **Hash Map (100%)**

### Step 4: Validation (15s)
- ✅ Hash Map finds pairs in O(n)
- ✅ O(n) time, O(n) space acceptable  
- ✅ Preserves indices
- ✅ Can implement easily
- ✅ Handles edge cases

### Step 5: Implementation Plan (10s)
- Map: value → index
- For each element: check if (target - element) exists
- If exists: return [map[complement], current_index]
- If not: store current element

**Total Time: 80 seconds to identify pattern with 100% confidence**

---

## 🎯 PATTERN SHORTCUTS (MEMORIZE THESE)

### Instant Recognition Phrases:
```
"two numbers that sum to target"           → Hash Map
"maximum sum subarray"                     → Kadane's Algorithm  
"next greater element"                     → Monotonic Stack
"merge overlapping intervals"              → Sort + Merge
"longest substring without repeating"      → Sliding Window
"find duplicate in range [1,n]"          → Cyclic Sort
"search in sorted array"                  → Binary Search
"all permutations/combinations"           → Backtracking
"range sum queries"                       → Prefix Sum
```

### Time Complexity Constraints:
```
O(log n):  Binary Search only
O(n):      Hash Map, Sliding Window, Two Pointers
O(n log n): Sorting + something
O(n²):     Nested loops (avoid if n > 1000)
O(2ⁿ):     Backtracking (only if n ≤ 20)
```

---

## 🔧 TROUBLESHOOTING GUIDE

### If You Can't Identify Pattern:
1. **Re-read problem slowly** - missed keywords?
2. **Check constraints again** - missed size limit?
3. **Try brute force first** - what's the O(n²) solution?
4. **Look for similar problems** - seen anything like this?
5. **Break down the problem** - can you split it into parts?

### If Multiple Patterns Seem Right:
1. **Pick the simplest** one you can implement
2. **Check time complexity** - which one is faster?
3. **Consider edge cases** - which handles them better?
4. **Think about follow-ups** - which is more extensible?

### If Pattern Seems Too Hard:
1. **Start with brute force** - get any working solution
2. **Optimize step by step** - can you eliminate redundancy?
3. **Use a simpler pattern** - even if not optimal
4. **Ask for hints** - in interviews, it's okay to ask

---

## 📊 SUCCESS METRICS

After using this process, you should achieve:
- **95%+ pattern identification accuracy**
- **Under 2 minutes to identify pattern**  
- **80%+ first implementation success rate**
- **Consistent performance across problem types**

**Practice Goal**: Use this exact 5-step process on 100 problems until it becomes automatic.

---

## 🏆 MASTER PATTERNS REFERENCE

### 1. Hash Map Pattern
**When**: Need fast lookups, finding complements, counting
**Time**: O(n), **Space**: O(n)
**Problems**: Two Sum, Group Anagrams, Top K Frequent

### 2. Two Pointers Pattern  
**When**: Sorted array, finding pairs, comparing ends
**Time**: O(n), **Space**: O(1)
**Problems**: Two Sum II, Three Sum, Container With Most Water

### 3. Sliding Window Pattern
**When**: Contiguous subarray/substring problems
**Time**: O(n), **Space**: O(1)
**Problems**: Max Sum Subarray K, Longest Substring Without Repeating

### 4. Binary Search Pattern
**When**: Sorted array, search space reduction
**Time**: O(log n), **Space**: O(1)
**Problems**: Search Insert Position, Find Peak Element

### 5. Stack Pattern
**When**: Next greater/smaller, bracket matching
**Time**: O(n), **Space**: O(n)
**Problems**: Next Greater Element, Valid Parentheses

### 6. Prefix Sum Pattern
**When**: Range queries, subarray sum problems
**Time**: O(n), **Space**: O(n)
**Problems**: Range Sum Query, Subarray Sum Equals K

### 7. Sorting Pattern
**When**: Order matters, grouping similar elements
**Time**: O(n log n), **Space**: O(1) to O(n)
**Problems**: Merge Intervals, Meeting Rooms

### 8. Dynamic Programming Pattern
**When**: Optimization with overlapping subproblems
**Time**: O(n) to O(n²), **Space**: O(n)
**Problems**: Maximum Subarray, House Robber, LIS

### 9. Backtracking Pattern
**When**: Generate all possibilities, permutations
**Time**: O(2ⁿ) to O(n!), **Space**: O(n)
**Problems**: Permutations, Combinations, Subsets

### 10. Cyclic Sort Pattern
**When**: Array with numbers in range [1,n]
**Time**: O(n), **Space**: O(1)
**Problems**: Missing Number, Find Duplicates

---

## 🎓 PRACTICE PROGRESSION

### Level 1: Foundation (20 problems)
- Two Sum, Contains Duplicate, Maximum Subarray
- Best Time to Buy/Sell Stock, Plus One, Move Zeroes

### Level 2: Core Patterns (30 problems)
- Three Sum, Longest Substring Without Repeating
- Next Greater Element, Merge Intervals, Search 2D Matrix

### Level 3: Advanced (50 problems)  
- Sliding Window Maximum, Trapping Rain Water
- LIS, Word Break, N-Queens, Regular Expression Matching

**Remember**: Pattern recognition is a skill. The more you practice this systematic approach, the faster and more accurate you'll become!
