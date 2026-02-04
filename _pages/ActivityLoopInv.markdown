---
layout: post
title:  "Activity: Sorting and Loop Invariants"
categories: Activity Sorting
---

## Learning Goals

You will work towards being able to...

1. Prove the correctness of an iterative algorithm using a loop invariant

### Warm-Up

### Activity Instructions

1. Consider the following BubbleSort algorithm. Read through the code, verify you understand the steps, and simulate the algorithm with the cards in front of you.

```plaintext
    BubbleSort(Array A[1...n]):
        for i <- 1 to n
            for j <- 2 to n:
                if A[j] < A[j-1]:
                    swap(A[j], A[j-1])
    
``` 

2. Begin to think about what each loop in the code does. Keep in mind our core questions: *What is the end goal of each loop?* and *How does each iteration make progress toward that goal?*. Make sure your group has a solid intuition for this before moving on.

3. Split the code into two functions (like Insert and InsertionSort) that isolate each loop. Write a problem definition for the problem each function solves.

4. Identify a loop invariant for the loop in each function. Sketch out a proof (i.e., don't worry about phrasing for now, just the ideas!) for each invariant. 

