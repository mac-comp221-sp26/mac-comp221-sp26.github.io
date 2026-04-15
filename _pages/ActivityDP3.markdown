---
layout: post
title: "Activity: Dynamic Programming Practice 3"
categories: Activity dynamic programming dp 
---

## Learning Goals

You will work towards being able to...

1. Design dynamic programming solutions to algorithmic problems

## Activity
For each of the following questions, design a recurrence relation, and then provide pseudocode for a dynamic programming algorithm to solve it. Consider the time and space complexity of your solutions. **It may be helpful to play around with the problem specification to build intution (i.e., work through an example!) before jumping to designing an algorithm**.

Do them in any order!

### **More than one way to tell the truth**
Suppose you're given a (valid) boolean expression consisting of T (true) and F (false) combined with standard boolean operators AND (&), OR (|) and XOR (^). What we're missing is parenthesis to disambiguate operator order (you see `T&F|T` rather than `((T&F)|T)` or `(T&(F|T))`). Of course, operator order is ambiguous. Your goal is to count the number of ways in which you can parenthesize (i.e., disambiguate operator order) the expression such that each parenthesized expression evaluates to T.

For example, `T^F|T` can be parenthesized 2 ways: `(T|F)^T` evaluates to F but `T|(F^F)` evaluates to T, so we count 1 (there are only 2 ways to parenthesize!). 
> <details>
>    <summary> Reveal/hide hint</summary>
> Think of this like parsing: For every operator (&/^/|), we can make the expression evaluate to true IF everything on the left and everything on the right evaluates to things that make the operator true. Think it through to determine if there **is** a way to make it evaluate to true, and then modify it to count!
> </details>
{: .block-tip }

### **Cut the cord**
Suppose you have $n$ feet of an extraordinarily valuable rope, where a rope of length $i$ is worth $c[i]$ dollars. Note that it is **not** priced by the foot: prices can be any value for any length, with the one exception that a rope of length 0 is worth $0. Determine the most money you can make by splitting your rope. 

For example, if $c = [1, 3, 4, 4]$ and $n = 4$, you should split the rope into 2 pieces of length 2 and make 6 dollars. If one didn't split it, it's worth 4 dollars, and if one split it into pieces of lengths (1 and 3) or (2 and 1 and 1) it's worth 5. Similarly, if $c = [2, 3, 5, 7]$, one should split the rope into 4 pieces of size 1 and make 8 dollars. 
> <details>
>    <summary> Reveal/hide hint</summary>
> Again, like parsing! You have to consider each possible split point, which reducts the rope into two ropes of smaller size (sub-problem!). Find the split that gets you the most money.
> </details>
{: .block-tip }


### **Top-Deque**
You an a friend are playing a game using a board represented by an deque of integers $D$. The players have perfect information, and know all of the elements of the deque and their order. Players take turns choosing whether to take an integer from the front or back of the deque and adding the dequeued value to their score. Determine the largest score you (the first player) can achieve with optimal play from both sides.

For example, if the deque contains [8 20 1 7], optimal play would be to choose 7, have your opponent choose 8, then take 20, then your opponent gets 1, earning you a score of 27. Note that greedy play (selecting 8 over 7 in the first move) is *suboptimal* here, as it allows the opponent to access the valuable 20! 
> <details>
>    <summary> Reveal/hide hint</summary>
> Consider that both players must play optimally, but the game is symmetric. Build a recurrance that tracks *both* player's scores! 
> </details>
{: .block-tip }


### **Inter-leavened b***re***ad**
Given three string $s_1, s_2, s$, determine whether $s$ is simply the two strings $s_1$ and $s_2$ *interleaved*. 

This is easier to explain via example: **p***a***re***n* is *an* and **pre** interleaved: All of the letters of both $s_1, s_2$ appear in $s$, in-order, but with the letters of the other word mixed in-between. This gets tricky though --- for the strings "arid" and "anger" you should be able to match both "arangerid" and "angarierd" -- note the initial a must belong to a differing $s_1, s_2$ in each $s$!
    > <details>
    >    <summary> Reveal/hide hint</summary>
    > This is like edit distance! What "decision" should you make for each letter in $s$?
    > </details>
    {: .block-tip }


#### Submission
Submit an artifact of your work on Moodle. 

---
