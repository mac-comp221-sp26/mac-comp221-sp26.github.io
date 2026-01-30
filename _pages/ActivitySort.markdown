---
layout: post
title:  "Activity: Big-O Practice & Sorting 1"
categories: Activity Sorting Big-O
---

## Learning Goals

You will work towards being able to...

1. Prove growth functions are Big-$O, \Omega, \Theta$ from definition.
2. Formalize algorithmic ideas into pseudocode
3. Compute growth functions from time & space complexities under the RAM model 
4. Know common algorithms to solve cannonical problems (sorting)

### Warm-Up
Using our formal definition of Big-$O$...

1. Show that $f(n) = \log n \in O(n)$. 

2. Show that $g(n) = n + \log n \in O(n)$. *Hint*: Can the previous problem help you?

3. Now let's get a big more abstract: Consider non-negative functions $f, g$ such that $f(n) \in O(g(n))$. Show that $f(n) + g(n) \in O(g(n))$. *Hint*: Use the definition of Big-O to give you more information about the relationship between $f$ and $g$!


### Activity Instructions
You will begin this activity with a set of 5 playing cards. Ignoring suit, your goal is to organize the cards using a standard ordering: $2 \leq \dots \leq 9 \leq 10 \leq J \leq Q \leq K \leq A$ (i.e., Ace high). The idea that underlies this activity is that **you already know how to write a sort cards**: If you have cards in front of you, you can confidently rearrange them into sorted order by implicitly comparing and swapping the positions of cards. What we will practice is *formalizing* the algorithm you use to do so by asking you to turn your intuitive sorting schemes into rigorous and well-defined algorithms based on the basic operations of comparison (is this card higher value than this other card?) and swapping (switch the position of this card with this other card). 

1. Look at the set of cards in front of you. Have a volunteer at your table slowly and methodically demonstrate how they'd rearrange the cards so that they are in increasing order using a sequence of comparisons between the values on cards and swaps. Try and document any local variables you need to update and keep track of as you go along. If you're the volunteer, do this in a way that seems natural to you (and perhaps not in an unintuitive way that might be slightly more efficient for a computer!).

2. *Formalize* the mechanics of your table's chosen sorting technique. Describe it as a combination of a few *basic* operations --- comparisons, and swapping the positions of two cards --- along with standard operations like declaring and updating variables. Write out pseudocode to describe your sorting operation, doing your best to follow the format of the examples you've seen. 

3. Shuffle the cards and count the number of basic operations (swaps and comparisons) it takes to sort the array using your sorting algorithm. 

4. Now, consider how far from a best or worst case scenario the array you were given was. Try and see if you can can determine the *worst-case* input (of length 5!) for your sorting algorithm. If you think you've found the worst possible case, share your reasoning and try and convince your table-mates that no input would take any longer. How many time steps does your algorithm take in the worst case? *Hint*: Since all sorting cares about the relative ordering of elements, you only need to consider different initial shuffles of the 5 elements.

5. Analyze the pseudocode for your algorithm and determine the growth function for your sort in terms of the number of comparisons and swaps. Determine it's time complexity in terms of Big-$\Theta$.

6. If you have time, prove your growth function is, in fact, within that Big-$\Theta$ time complexity class.

7. Submit an artifact (picture, screenshot, etc.) of (1) your sorting pseudocode and (2) the corresponding worst-case growth function and submit it on Moodle. 

