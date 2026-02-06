---
layout: post
title:  "Activity: Sorting and Loop Invariants"
categories: Activity Sorting
---

## Learning Goals

You will work towards being able to...

1. Prove the correctness of an iterative algorithm using a loop invariant

### Warm-Up
For each of the following iterative functions, write a loop invariant that you can use to prove it correct. If you have extra time, sketch out a proof.

1. We define the factorial of $n \in \mathbb{N}$ (i.e., $n!$) as $n! = \prod_{i=1}^n i$. Consider:

```
    Factorial(n ∈ ℕ):
        p ← 1
        for i ← 1 to n:
            p ← p * i
        return p
```

2. We define the *Fibonacci sequence* $f_0, f_1, \dots $ as follows: $f_0 = 0$, $f_1 = 1$, and for $n \geq 2$, $f_n = f_{n-1} + f_{n-2}$. A solution to the Fibonacci Number problem takes in $n \in \mathbb{N}$ and must return $f_n$ as defined. Consider the following:

``` 
    Fibonacci(n ∈ ℕ):
        f_prev ← 0
        f ← 1
        for i ← 2 to n:
            f ← f + f_prev
            f_prev ← f - f_prev
        return f
```

### Activity Instructions

1. Consider the following BubbleSort algorithm. Read through the code, verify you understand the steps, and simulate the algorithm with the cards in front of you.

```
    BubbleSort(Array A[1...n]):
        for i ← 1 to n
            for j ← 1 to n-i:
                if A[j+1] < A[j]:
                    swap(A[j], A[j+1])
        return A
    
``` 

2. As your simulate the code, begin to think about what each loop in the code does. Then, as you perform each loop, keep in mind our core questions: *How does each iteration make progress toward our ultimate goal?*. Make sure your group has a solid ointuition for this before moving on.
    - It may be helpful to grab a marker and keep track of the state of the array after each iteration. Look for patterns that you might be able to describe as invariants!

3. Split the code into two functions (like Insert and InsertionSort) that isolate each loop. Call the new function that represents the inner loop Bubble, to fit the theme. Write a problem definition for the problem each function solves using your idea of what each loop is supposed to do.
    - This should be simple for the outer loop, since the algorithm needs to sort! The inner loop will be more interesting.

4. Identify a loop invariant for the loop in each function. Sketch out a proof (i.e., don't worry about phrasing for now, just the ideas!) for each invariant, starting with the Bubble function and using that result to prove the outer Loop Invariant.
    - Don't be worried if you feel like you don't have enough to show your loop invariant holds! Think about what additional information might be missing and how you might strengthen your loop invariant to give you a stronger inductive hypothesis!

