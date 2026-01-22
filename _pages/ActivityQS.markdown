---
layout: post
title:  "Activity: Quicksort and Partitioning"
categories: Activity Sorting Quicksort Partitioning
---

## Learning Goals

You will work towards being able to...

1. Understanding the behavior of common algorithms (quicksort)

2. Implement common algorithms (quicksort)

## Warm-Up

1. As a group, walk through a few examples of the partitioning algorithm you saw in the reading. Construct a few random arrays and step through the code line-by-line to understand how the array is structured and maintained throughout. With an array of fixed size $n$ and fixed elements, which permutation of the array is best? Which is worst?

## Instructions
Work with your groups on the following problems:

1. Based on our sketch of the proof of correctness for quicksort in lecture, define correctness for the partition algorithm and construct a proof of correctness for the partition algorithm. Feel free to sketch things out (Find the right loop invariant, etc.) while you're with your group and fill out details on your own.

2. Bonus: This partitioning algorithm isn't the only (or most efficient, or even first) partitioning algorithm for quicksort. However, this version (called the *Lomuto* scheme) is generally regarded as a simpler, easier to implement version that doesn't sacrifice asymptotic time complexity. The other common scheme, the *Hoare* scheme, is faster, but more complex. It's also clever in a very *intro algorithms* sort of way, so it may be worth seeing the trick!

```plaintext
partition(A, low, high):
    pivot <- A[low]
    i <- low
    j <- high
    While True
        while A[i] < pivot:
            i <- i + 1

        while A[j] > pivot:
            j <- j - 1
        
        if j <= i:
            Return j
        Swap(A[i], A[j])
        
        i <- i + 1
        j <- j - 1
```
Here the idea is to move two indices from the edges toward the center until we find an element on the left that should be on the right and an element on the right that should be on the left. If that happens, we swap them! When the two indices cross, we swap them. Work through a few array with this partition algorithm until you can convince yourself it partitions in a way that can be used to implement quicksort. Note that the pivot isn't even ending up at the returned index!

As a bonus, you can probably find a bug in my pseudocode above. This version is notoriously tricky! Here's a quote from Jon Bentley's *Programming Pearls*:
>“Most discussions of Quicksort use a partitioning scheme based on two approaching indices... (i.e. Hoare's). Although the basic idea of that scheme is straightforward, I have always found the details tricky - I once spent the better part of two days chasing down a bug hiding in a short partitioning loop. A reader of a preliminary draft complained that the standard two-index method is in fact simpler than Lomuto's and sketched some code to make his point; I stopped looking after I found two bugs.”

#### Submission
Submit an artifact of your work from 1 and 2.


