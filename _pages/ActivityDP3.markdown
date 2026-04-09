---
layout: post
title: "Activity: Dynamic Programming Practice 2"
categories: Activity dynamic programming dp 
---

## Learning Goals

You will work towards being able to...

1. Design dynamic programming solutions to algorithmic problems

## Activity
For each of the following questions, design a recurrence relation, and then provide pseudocode for a dynamic programming algorithm to solve it. Consider the time and space complexity of your solutions. **It may be helpful to play around with the problem specification to build intution (i.e., work through an example!) before jumping to designing an algorithm**.

1. (Skiena 10-6) Modify the edit distance algorithm we've discussed to allow for *transposition errors*, where at the cost of one operation, you can swap two adjacent characters. Convince yourself that your recurrence works, and run your pseudocode on the "steve"/"setve" pair Skiena gives you. 

2. (Skiena 10-7) Suppose you have 3 strings, $x, y, z$, where $\lvert z \rvert = \lvert x \rvert + \lvert y \rvert$. $z$ is a shuffle of $x$ and $y$ if it interleaves characters from $x$ and $y$ preserving their order. That is, you take $x$ and insert all characters of $y$ into the string such that the order of characters in $y$ are preserved. See Skiena 10-7a for examples --- confirm that they make sense! Then write a dynamic programming algorithm (based on the structure of edit distance!) that determines whether $z$ is a shuffle of $x$ and $y$. 

#### Submission
Submit an artifact of your work on Moodle. 

---
