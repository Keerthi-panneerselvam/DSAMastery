## Patterns to solve Array Problems

Here are the key patterns for solving array problems, along with important techniques and related problems:

## 1. Two Pointers Pattern
**When to use:** When you need to find pairs, triplets, or work with sorted arrays
**Technique:** Use two pointers moving towards each other or in the same direction

**Problems:**
- Two Sum (sorted array)
- Three Sum
- Container With Most Water
- Remove Duplicates from Sorted Array
- Trapping Rain Water

## 2. Sliding Window Pattern
**When to use:** For subarray/substring problems with contiguous elements
**Technique:** Maintain a window and expand/contract based on conditions

**Problems:**
- Maximum Sum Subarray of Size K
- Longest Substring Without Repeating Characters
- Minimum Window Substring
- Sliding Window Maximum
- Longest Subarray with Sum K

## 3. Fast and Slow Pointers (Floyd's Algorithm)
**When to use:** For cycle detection or finding middle elements
**Technique:** Two pointers moving at different speeds

**Problems:**
- Linked List Cycle Detection
- Find Middle of Array
- Happy Number
- Find Duplicate Number

## 4. Prefix Sum Pattern
**When to use:** For range sum queries or subarray sum problems
**Technique:** Precompute cumulative sums

**Problems:**
- Range Sum Query
- Subarray Sum Equals K
- Maximum Subarray Sum
- Product of Array Except Self
- Running Sum of 1D Array

## 5. Hash Map/Set Pattern
**When to use:** For frequency counting, lookups, or finding complements
**Technique:** Store elements/frequencies for O(1) access

**Problems:**
- Two Sum
- Group Anagrams
- Top K Frequent Elements
- First Non-Repeating Character
- Intersection of Two Arrays

## 6. Sorting-Based Pattern
**When to use:** When order matters or for optimization
**Technique:** Sort first, then apply other techniques

**Problems:**
- Merge Intervals
- Three Sum
- Meeting Rooms
- Largest Number
- Sort Colors

## 7. Binary Search Pattern
**When to use:** On sorted arrays or when searching for optimal values
**Technique:** Divide search space in half repeatedly

**Problems:**
- Search in Rotated Sorted Array
- Find Peak Element
- Search 2D Matrix
- Find Minimum in Rotated Sorted Array
- Koko Eating Bananas

## 8. Stack-Based Pattern
**When to use:** For nearest greater/smaller elements or bracket problems
**Technique:** Use stack to maintain elements in specific order

**Problems:**
- Next Greater Element
- Valid Parentheses
- Daily Temperatures
- Largest Rectangle in Histogram
- Monotonic Stack Problems

## 9. Dynamic Programming on Arrays
**When to use:** For optimization problems with overlapping subproblems
**Technique:** Build solutions incrementally

**Problems:**
- Maximum Subarray (Kadane's Algorithm)
- House Robber
- Climbing Stairs
- Longest Increasing Subsequence
- Best Time to Buy and Sell Stock

## 10. Divide and Conquer
**When to use:** When problem can be broken into similar subproblems
**Technique:** Recursively solve smaller parts and combine

**Problems:**
- Merge Sort
- Quick Sort
- Maximum Subarray (alternative approach)
- Closest Pair of Points
- Count Inversions

## 11. Cyclic Sort Pattern
**When to use:** When array contains numbers in range 1 to n
**Technique:** Place each number at its correct index

**Problems:**
- Missing Number
- Find All Duplicates
- First Missing Positive
- Find All Numbers Disappeared in Array

## 12. Backtracking on Arrays
**When to use:** For generating combinations, permutations, or subsets
**Technique:** Explore all possibilities with pruning

**Problems:**
- Permutations
- Combinations
- Subsets
- Palindrome Partitioning
- N-Queens

## Key Tips for Array Problems:

**Time Complexity Goals:**
- O(n) is often achievable for single-pass problems
- O(n log n) when sorting is involved
- O(n²) for nested comparisons (try to optimize)

**Space Optimization:**
- Try to solve in-place when possible
- Use the array itself for marking (negative indexing, swapping)
- Consider if you can use input array as auxiliary space

**Common Edge Cases:**
- Empty arrays
- Single element arrays
- All elements same
- Already sorted/reverse sorted arrays
- Arrays with negative numbers or zeros

These patterns cover about 80% of array problems you'll encounter. The key is recognizing which pattern applies to your specific problem and adapting the technique accordingly.
