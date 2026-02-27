---
layout: post
title:  "Activity: Divide and Conquer Practice"
categories: Activity DataStructures Sorting TreeSort HeapSort
---

## Learning Goals

You will work towards being able to...

1. Design and analyze divide and conquer algorithms

2. Apply the Master Theorem to determine the runtime of Divide and Conquer Algorithms


## Warm-Up

1. Apply the master theorem to solve the following recurrences. Note the case we fall into and the resulting closed form.

    - $T(n) = 4T(\frac{n}{2}) + 2n^2$ 
    - $T(n) = 3T(\frac{n}{2}) + 7n$ 
    - $T(n) = T(\frac{n}{3}) + n^2$ 

2. Suppose you want to write a $O(n^2\log n)$ algorithm and have devised a scheme to split the input into 5 pieces, each a third of the input size. You have yet to write the algorithms to split the input and recombine the pieces, and want to know how efficient those algorithms must be. What time complexities can my algorithm obtain (in Big-$\Theta$) and how fast must the division/recombination steps be to achieve those complexities?

## Problems

1. (Erickson 1-13) An *inversion* is a pair of indices $i < j$ in an array $A$ such that $A[i] > A[j]$ --- two indices that are not in order! If every pair is out of order, there will be $\frac{1}{2}n(n-1)$ inversions in an array $A[1\dots n]$ (this is an array in reverse order!). Modify MergeSort to compute the number of inversions in an array $A[1\dots n]$ in $O(n \log n) $ time.
    - I do mean modify MergeSort --- you will compute this while sorting the array!
    - Think through the Merge step in particular: You recursive calls give you inversions in the left half and right half, but what inversions aren't you counting?
    - How can you get those inversions with two sorted subarrays in a time efficient enough to give us an $O(n\log n)$ time complexity?

2. (Erickson 1-14) Suppose you are given two sets of points, $\{(p_1, 0), \dots (p_n, 0)\}$ and $\{(q_1, 1), \dots, (q_n, 1)\}$ on two parallel lines. Suppose you construct line segments connecting $p_1$ to $q_1$, $p_2$ to $q_2$, and so on. Write an $O(n\log n)$ algorithm that counts the number of crossings.
    - What is the relationship between an inversion as defined in the previous problem and the crossings in this problem?
    - How can you design an algorithm based on this similarity? 

3. Bonus: Additional Recommended Practice Problems! Erickson Ch 1 Probs... 
    - 18, Same vibe as HW3 Prob 1 (sorting as a decision tree!)
    - 26, you may have seen this problem in Discrete! Recall "Trominos"!
        > <details>
        >    <summary> Reveal/hide hint</summary>
        >    Recall the proof of correctness and look for the place that you use your inductive hypothesis (i.e., 4 grids a quarter of the size). Those are your recursive calls, and the rest is the Divide/Recombine step.
        .</details>
        {: .block-tip }
    - 29, Another 2D divide and conquer analysis example, but with exact counts!
    - 32, A classic interview question (also leetcode [problem 162](https://leetcode.com/problems/find-peak-element/description/)) 
        > <details>
        >    <summary>Reveal/hide hint</summary>
        >    This is a sort-of a discrete version of our root finding algorithm, but to understand why involves some more calculus (we want to do root-finding on the derivative of the data). If that's not familiar, consider this: If a sequence is increasing at one point and decreasing later, what has to happen at some point between? What if we're decreasing around one index and increasing at another?
        .</details>
        {: .block-tip }
    - 38, A example of how Divide and Conquer techniques can apply to data structures like Trees!
        > <details>
        >    <summary> Reveal/hide hint </summary>
        >    Taking an arbitrary node and computing the number of nodes to the left, $l$, to the right $r$, and in the parent $p$. If this node *isn't* central, then one of $l$, $r$, or $p$ is $\geq \frac{n}{2}$. Which one has this property tells you where a central node **cannot** be. Use this to rule out options ala Binary Search.
        .</details>
        {: .block-tip }
    - 40, An algorithm from a prior semester's final report!
