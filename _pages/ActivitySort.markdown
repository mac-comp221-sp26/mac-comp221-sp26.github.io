---
layout: post
title:  "Activity: Sorting"
categories: Activity Sorting
---

## Learning Goals

You will work towards being able to...

1. Prove Big-$O, \Omega, \Theta$ from definition.
2. Formalize algorithmic ideas into pseudocode
3. Compute growth functions from time & space complexities under the RAM model 
4. Know common algorithms to solve cannonical problems (sorting)

### Warm-Up

1. Show that $f(n) = \log n \in O(n)$. 

2. Show that $g(n) = n + \log n \in O(n)$.

3. Now let's get a big more abstract: Consider non-negative functions $f, g$ such that $f(n) \in O(g(n))$. Show that $f(n) + g(n) \in O(g(n))$. *Hint*: Use the definition of Big-O to give you more information about the relationship between $f$ and $g$!

### Activity Instructions

1. Look at the set of cards in front of you. Have a volunteer at your table slowly and methodically demonstrate how they'd rearrange the cards so that they are in increasing order using a sequence of comparisons between the values on cards and swaps. If you're the volunteer, do this in a way that seems natural to you (and perhaps not in an unintuitive way that might be slightly more efficient for a computer!). 

2. *Formalize* the mechanics of your table's chosen sorting technique. Describe it as a combination of a few *basic* operations: comparisons, and swapping the positions of two numbers. Write out pseudocode to describe your sorting operation. 

3. Construct a random ordering of cards and count the number of basic operations it takes to sort the array using your sorting algorithm. 

4. Now, consider how far from a best or worst case scenario the array you were given was. Try and see if you can can determine the *worst-case* input (of length 5!) for your sorting algorithm. If you think you've found the worst possible case, share your reasoning and try and convince your table-mates that no input would take any longer. How many time steps does your algorithm take in the worst case? *Hint*: Since all sorting cares about the relative ordering of elements, you only need to consider different initial shuffles of the 5 elements.

5. Analyze the pseudocode for your algorithm and determine the growth function for your sort in terms of the number of comparisons and swaps. Determine it's time complexity in terms of Big-$\Theta$.

6. If you have time, prove your growth function is, in fact, within that Big-$\Theta$ time complexity class.

7. Submit an artifact (picture, screenshot, etc.) of you (1) pseudocode and (2) worst-case growth function and submit it on Moodle.

