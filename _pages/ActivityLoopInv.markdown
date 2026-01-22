---
layout: post
title:  "Activity: Sorting"
categories: Activity Sorting
---

## Learning Goals

You will work towards being able to...

1. Prove the correctness of an iterative algorithm using a loop invariant

### Warm-Up

1. (Skiena 2.39) Suppose you have an unsorted array of $n$ unique integers, each between $1$ and $n+1$. Naturally, there is a single integer between $1$ and $n+1$ missing. Find an algorithm that runs in $O(n)$ time and *constant space* complexity that finds that missing number.

### Activity Instructions

1. Look at the set of numbered cards in front of you. Have a volunteer at your table slowly and methodically demonstrate how they'd rearrange the cards so that they are in increasing order using a sequence of comparisons between the values on cards and swaps. If you're the volunteer, do this in a way that seems natural to you (and perhaps not in an unintuitive way that might be slightly more efficient for a computer!). Try to do something that *isn't* an insertion sort, but is described iteratively!

2. *Formalize* the mechanics of your table's chosen sorting technique. Describe it as a combination of a few *basic* operations: comparisons, and swapping the positions of two numbers. Write out pseudocode to describe your sorting method with these operations. 

3. Make sure you understand the way in which the algorithm works --- how does it make progress toward a fully sorted array? Be sure you are confident about this before moving on --- work through examples and see if you can identify what progress looks like!

4. Strategize about how you might prove the algorithm you've designed correct --- can you our small pieces (like INSERT in insertion sort) that you can prove correct that build toward total correctness? Do your best to sketch out the proof structure for each segment - state a loop invariant, show it's true before the first iteration (base case) and that if it's true after one iteration, it'll be true after the next (inductive step), and then show it's truth after the last iteration implies correctness of the algorithm.


