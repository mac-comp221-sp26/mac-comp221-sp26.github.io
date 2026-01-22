---
layout: post
title:  "Activity: Sorting"
categories: Activity Sorting
---

## Learning Goals

You will work towards being able to...

1. Prove the correctness of an iterative algorithm using a loop invariant

### Warm-Up

1. (Skiena 2.39) Suppose you have an unsorted array of $n$ unique integers, each between $1$ and $n+1$. Naturally, there is a single integer between $1$ and $n+1$ missing. Find an algorithm that runs in $O(n)$ time and *constant space* complexity that finds that missing number. **HINT**: Note that the textbook lists this problem under the *Summation* subheading.  

### Activity Instructions

1. Look at the set of numbered index cards in front of you. They should start in the order [4 -12 6 3 1]. Have a volunteer at your table slowly and methodically demonstrate how they'd rearrange the cards so that they are in increasing order using a sequence of comparisons between the values on cards and swaps. If you're the volunteer, do this in a way that seems natural to you (and perhaps not in an unintuitive way that might be slightly more efficient for a computer!). 

2. *Formalize* the mechanics of your table's chosen sorting technique. Describe it as a combination of a few *basic* operations: comparisons, and swapping the positions of two numbers. Write out pseudocode to describe your sorting operation. 

3. Starting from the array listed in step 1, count the number of basic operations it takes to sort the array using your sorting algorithm. 

4. Now, consider how far from a best or worst case scenario the array you were given was. Try and see if you can can determine the *worst-case* input (of length 5!) for your sorting algorithm. If you think you've found the worst possible case, share your reasoning and try and convince your table-mates that no input would take any longer. How many time steps does your algorithm take in the worst case? *Hint*: Since all sorting cares about the relative ordering of elements, you only need to consider different initial shuffles of the 5 elements.

5. If you have spare time, try: 
    - Do the above for a different intuitive sorting algorithm from someone else at the table. Are the worst-case arrays different for the two? 
    - Can you come up with a way to construct a worst-case array for your algorithm for any n? See if you can generalize a worst-case growth function for the time complexity of this algorithm. 
    - We've assumed that the only things you can do are compare and swap elements in the array. Would your algorithm be faster with access to a different data structure or basic operation?  


6. **For credit**: Submit the pseudocode of your algorithm to Moodle. If you found a worst-case input for your algorithm, provide that as well!
