---
layout: post
title:  "Activity: Divide and Conquer Practice"
categories: Activity DataStructures Sorting TreeSort HeapSort
---

## Learning Goals

You will work towards being able to...

1. Design and analyze divide and conquer algorithms


## Problems

1. (Erickson 1-13) An *inversion* is a pair of indices $i < j$ in an array $A$ such that $A[i] > A[j]$ --- two indices that are not in order! If every pair is out of order, there will be $\frac{1}{2}n(n-1)$ inversions in an array $A[1\dots n]$ (this is an array in reverse order!). Modify MergeSort to compute the number of inversions in an array $A[1\dots n]$ in $O(n \log n) $ time.
    - I do mean modify MergeSort --- you will compute this while sorting the array!
    - Think through the Merge step in particular: You recursive calls give you inversions in the left half and right half, but what inversions aren't you counting?
    - How can you get those inversions with two sorted subarrays in a time efficient enough to give us an $O(n\log n)$ time complexity?

2. (Erickson 1-14) Suppose you are given two sets of points, $\{(p_1, 0), \dots (p_n, 0)\}$ and \{(q_1, 1), \dots, (q_n, 1)\}$ on two parallel lines. Suppose you construct line segments connecting $p_1$ to $q_1$, $p_2$ to $q_2$, and so on. Write an $O(n\log n)$ algorithm that counts the number of crossings.
    - What is the relationship between an inversion as defined in the previous problem and the crossings in this problem?
    - How can you design an algorithm based on this similarity? 

3. Additional Recommended Practice Problems : Erickson Ch 1 Probs 18 (Same vibe as HW3 Prob 1), 29, 32, 38 
