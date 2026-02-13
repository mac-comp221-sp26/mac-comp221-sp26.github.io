---
layout: post
title:  "Activity: Heap- & TreeSort"
categories: Activity DataStructures Sorting TreeSort HeapSort
---

## Learning Goals

You will work towards being able to...

1. Build and reason about algorithms that use data structure-based design principles

2. Understanding the core idea of, write pseudocode for, and analyze the runtime and correctness of common algorithms (HeapSort and TreeSort)

3. Understand sorting as a pre-processing step for solving common algorithmic problems. 

### Part 1: HeapSort

1. Consider the following pseudocode for SelectionSort. Make sure you understand how it works (HW2 should help!). 

```
SelectionSort(Array A[1...n]):
    for i ← 1 to n-1:
        idx ← (i-1) + Select(A[i...n]) // Gets the index of the smallest element in the subarray
        Swap(A[idx], A[i])
    return A
``` 

2. Note that the implementation of Select you saw in the homework operates by performing a linear scan of the subarray, as follows:

```
Select(Array A[1...m]):
    min_idx ← 1
    for i ← 2 to m:
        if A[i] < A[min_idx]:
            min_idx ← i
    return min_idx
```

Make sure you understand what this code is doing!

3. The goal of **Data Structure-based Design** is to identify code that navigates data (i.e., a collection) inefficiently and modifying the code to replace these inefficiencies with code that uses a better data structure that is faster and still correct. 
    1. What is the Big-O worst-case time complexity of select?
    2. We define correctness for select as returning the index of the smallest element in the subarray passed as an argument. Recall from data structures that we spent some time designing a data structure that made repeatedly finding the smallest element in a collection fast and efficient! 
    3. Spend a moment reminding yourself and your partner of this data structure (a priority queue, implemented via a min-heap!). What are the time complexities of the `add` and `removeMin` operations in a min-heap/pqueue?
    4. Rewrite `SelectionSort` so that it utilizes a priority queue rather than the `Select` function.
    5. Analyze the time complexity of the resulting `HeapSort` function.  You may use the fact that $\sum_{i=1}^{n} \log i \in \Theta(n\log n)$ (a consequence of Stirling's approximation, if you're interested). 

4. **Bonus:** Just as you prove the correctness of `SelectionSort` using an intermediate results/lemma about `Select` being correct, we prove the correctness of heapsort using established results about the correctness of our heap operations! For example, we can modify our proof of correctness for `SelectionSort` to be one for `HeapSort` by using a few facts about heaps we can prove. Namely, we can state results like

> (Lemma 1) For a min-heap $h$, `removeMin()` updates $h$ to $h'$ returns an element $e$ such that $e \leq f$ for all $f \in h'$, $e \notin h'$, and for all $f \in h$ where $e \neq f$, $f \in h$.  

which simply rephrases that removeMin returns the smallest element of the heap and removes it (and only it) from the heap. **(a.)** Think about how you might adapt your proof of correctness from HW2 to prove `HeapSort` correct. **(b.)** Now consider the *implementation* side of the proof. Consider how we might write a proof for the above lemma using our implementation of a heap from 128!

#### Part 2: TreeSort
1. Write out pseudocode for TreeSort, which works by inserting each element of our array into a Binary Search Tree and filling in a new array by reading out the search tree's in-order traversal. This should notably be more specified than the problem in HW0!

2. Work backwards from TreeSort and compare it's behavior the the $O(n^2)$ sorts we've seen before. Discuss with your partner how TreeSort can be analyzed as a Data Structure-based optimization of a sort we've seen before.

3. Recall what we've seen from discussing Self-Balancing BSTs and provide a Big-O time complexity for `Insert` into a SBBST. We will have to wait briefly for a formal analysis of an in-order traversal, but you may assume what we said in Data Structures --- that it is $O(n)$. What is the time complexity of `TreeSort`?

4. **Bonus:** Lets begin analyzing TreeSort's correctness. You'll find (similar to HeapSort) that the correctness of this algorithm relies on a property of a binary search tree: That it's in-order traversal is sorted! Use the following definitions:

A sequence $a_1, \dots a_n$ is *sorted* iff $a_1 \leq a_2 \leq \dots \leq a_n$. A sequence $a_1, \dots, a_n$ is an *in-order traversal* of a binary tree $T$ iff each $a_i$, $1 \leq i \leq n$ uniquely maps to the value of a node in $T$  and for any $a_i$ and it's corresponding node $N$, the value of each node in the left subtree of $N$, $a_j$  has index $j < i$ and every element in it's right subtree of $N$, $a_k$, has index $k > i$. A *binary search tree* is a tree $T$ such that for every node $N$ with value $m$ in the tree, every value $l$ in the left subtree of $N$ has $l \leq m$ and for every value $r$ in the right subtree of $N$ has $r \geq m$.

#### Submission
Submit an artifact of your work from the HeapSort portion of this assignment, as well as your TreeSort pseudocode if you've gotten there!
