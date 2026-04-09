---
layout: post
title: "Activity: Dynamic Programming Practice 2"
categories: Activity dynamic programming dp 
---

## Learning Goals

You will work towards being able to...

1. Design dynamic programming solutions to algorithmic problems

## Activity
For each of the following questions, design a recurrence relation, and then provide pseudocode for a dynamic programming algorithm to solve it. The first problem will scaffold this process explicitly, but you should consider following that strategy for the others as well! Consider the time and space complexity of your solutions. **It may be helpful to play around with the problem specification to build intution (i.e., work through an example!) before jumping to designing an algorithm**.

1. (Leetcode 121) Suppose you have an array $p[1\dots n]$ which stores the price of a stock at time $i$ as $P[i]$. Suppose you are interested in finding the best single transaction one can make  --- that is, finding $t_1, t_2$ where buying a stock at time $t_1$ and selling at time $t_2$ creates the maximum profit (or 0, if no profit can be made). Formally, you take $P$ as input and must determine $\max_{i < j} (P[j] - P[i])$.

    0. Make sure you understand the problem --- solve it by hand on a few examples.
    1. Determine a recurrence relation for the problem. Consider framing the problem in terms of computing *two* functions $min(P[1\dots n])$ --- the cheapest price within the array --- and $p(P[1\dots n])$ that computes the max profit from a single trade. If we have answers for $min(P[1\dots n-1])$ and $p(P[1\dots n-1])$, there are two options to consider --- either the new value is not involved in the best trade (and you fall back on your answer for $P[1\dots n-1]$) or $P[n]$ is the day you sell the stock in the optimal answer (what's the maximum profit one can make in this kind of trade?). Form this idea into a recurrence for $p$, and then build a recurrence for $min$.
    2. Consider what data structure one needs to store answers for all the subproblems that emerge in solving the recurrence.
    3. Consider the dependencies between subproblems, and determine a way to iterate through the data structure such that filling in the cell by applying the recurrence can be done by referencing other cells that are already filled in.
    4. Convert this idea into pseudocode.
    5. Optimize this, if possible. It can be done in $O(n)$ time and $O(1)$ space, though a naive DP approach will get you to $O(n)$ space. 

2. A variant of problem 1 is the maximum subarray problem --- find a contiguous subarray of an array $A$ such that the sum of the array is maximized (i.e., find $\max{i,j} \sum_{k=i}^j A[k]$). Similarly, this will involve keeping track of something other than the answer to other subproblems: when you extent the array by one, you either don't affect the maximum subarray, or the maximum subarray that ends at the right edge of the array extends by one. Work through building a recurrence for the max subarray problem and for this other *constrained* max subarray. It may be helpful to work through this recurrence idea with a concrete example before doing the other steps. 

3. You design a fun little program to implement a [Substitution Cipher](https://en.wikipedia.org/wiki/Substitution_cipher), where you replace every letter with a number: A goes to 1, B goes to 2, and so on until Z goes to 26. You then convert the numbers to strings and concatenate them, but then you run into a problem: the code is ambiguous! The encoded string "217" can be decoded as BAG (2-1-7) or UG (21-7) or BQ (2-17). Write an algorithm to determine the number of competing interpretations for a given string. 
    1. Again, build a recurrence relation for this problem. Ask yourself: How does adding an additional character affect the number of interpretations? Be careful --- there are only 26 letters! a new 7 can only be interpreted as a 7, but a 6 could be a 16 or 27 if the prior digit is a 1 or 2!
    2. Do the rest --- build a table, find an iteration order, and write and optimize pseudocode. This can be done (also) in $O(n)$ time and $O(1)$ space, but $O(n)$ space should fall out of a naive DP solution.  

#### Submission
Submit an artifact of your work on Moodle. This need not be answers to all of the problems, but try and spend a solid hour (as a replacement of class time) attempting these problems. Save questions and concerns for Monday!

---
