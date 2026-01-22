---
layout: post
title:  "Activity: Data Structure Review"
categories: Activity DataStructures Review
---

## Learning Goals

You will work towards being able to...

1. Know the time complexities of common implementations of hashtables, priority queues, trees, and graphs

2. Reason about best- and worst-case inputs to these data structures

3. Use the vocabulary of non-linear data structures: hashing/hashcode, loading factor, parent, child, sister/sibling, ancestor/descendent, root, directed/undirected, dense/sparse, connected/connected component, cycle/cyclic/acyclic.

Over and above this, **the general goal of this assignment is to start getting you to think about these data structures as abstract mathematical objects rather than constructs in programming**. 

## Instructions
Work with your groups on the problems below. Each section also includes the question marked **Bonus**, which you should only attempt **AFTER** solving all of the non-bonus questions in each section. 

I encourage you to work through these problems with *examples*. Some of these questions are fairly abstract, and so it may be tempting to work through them entirely abstractly. However, you might find that your intuitions about these abstract structures aren't great (or worse, *wrong*!). I recommend that you develop explicit, concrete examples for each of these problems. This may involve working through the problem after picking specific values for unknown constrants (i.e., solve the hashing question with $m=5$ and then with $m=6$! How does changing $m$ change how collisions work out? Can I generalize to all possible $m$?), or explicitly writing out the adjacency list and matrix representations for a few graphs before you get an intuition for which ones are best suited for adjacency matrices vs. lists.

#### Hashing and Maps
Suppose you have a hashtable of size $m$ that you use to implement a map with String keys and Integer values. You map keys to indices in the hashtable using the following function:

```plaintext
function hash(String s, Integer m):
    hc <- 0 
    for i <- 1 to length(s):
        hc <- hc + letter_num(s[i])
    return hc % m
```
Where letter\_num returns the position of the letter in the alphabet (i.e., letter\_num("a") = 1, letter\_num("b") = 2, ..., letter\_num("z") = 26). 
For what values of $m$ will the following insertions collide?

```plaintext
insert("bald")
insert("area")
~~insert("sea")~~
```

What about the following inserts?

```plaintext
insert("cheddar")
insert("comic")
insert("fern")
insert("nerf")
```

Can you conclude anything *in-general* about your choice of $m$ if you were to implement this hashmap? what $m$ would minimize collisions? What collisions can you not avoid? (If it helps, feel free to make some assumptions: What if the length of string keys have length $\leq k$, for some $k$? Can you construct a good $m$ in terms of $k$). 

Feel free to write small pieces of code if it helps you work through the problem!

**Bonus**: For those of you with some probability background, let's consider the odds of a collision occurring: Suppose you have a hash function $f$ that is *distributed uniformly*. This means for random $k$ in our space of keys, the corresponding values $f(k)$ are equally likely to be hashed to any of the $m$ slots in our hashtable. Formally, we can say that this means for a sequence of insertions with keys $k_1, \dots, k_n$, $P(f(k_i) = j) = \frac{1}{m}$ for any $1 \leq i \leq n$ and $1 \leq j \leq m$. What is the likelihood of a collision after $n$ insertions (that is, that $\exists l,m$ such that $f(k_l) = f(k_m)$). Like many probability problems of this type, it might be easier to reason about the likelihood that there *aren't* any collisions.

#### PQueues and Heaps
1. Suppose you have a priority queue implemented with a min-heap. Suppose 9 items were successfully inserted into it. What is the structure of the tree? Draw the nodes and parent-child structure. 

    > ##### HINT
    > How does a heap maintain balance? What property does the tree underlying the heap always have?
    {: .block-tip}

2. Recall that a min-heap has an ordering property such that if node $a$ is a child of node $b$, then $a \geq b$. **Show (formally) that this means that a path from root to leaf $c_1, c_2, \dots, c_h$ is sorted.** For clarity, since $c_1, \dots c_h$ is a path from root to leaf, this means that for each $1 < i \leq h$, $c_i$ is the child of $c_{i-1}$.   

**Bonus**: When we insert or remove an element from the heap, our algorithm from data structures was to insert it to an incorrect position (i.e., one that violates our ordering property), and then swap it with elements above until it was greater than it's parent. This is, essentially, a single pass of BubbleSort on the path from the root to the new leaf. Show that this always works! Make sure to use the proper assumptions: What do you know about the structure of the heap before the insert? Write out the pseudocode for the insert and see if you can prove it's correctness (i.e., that the element is added and that the heap ordering and balance properties are preserved.

#### (Binary Search) Trees
1. Suppose you have an empty (non-self-balancing) binary search tree and insert $k$ elements into it. What is the worst-case time complexity of a look-up for a particular value (in big-$\Theta$). What does a worst case sequence of insertions look like?

**Bonus** (Skiena 3-15) Suppose you want to convert an un-balanced binary search tree to a balanced one. Write an $O(n)$ algorithm that will convert a binary search tree with $n$ nodes to one that is perfectly balanced. Here, take balanced to mean that the depth of any two *null pointers* (i.e., a missing child) differs by at most 1. 

    > ##### HINT
    > Look back at the answer to the hint question in the PQueue/Heap section. Could you borrow a balancing idea from there?
    {: .block-tip}

**BONUS**: (Skiena 3-21) Given two BSTs $A$ and $B$ such that $\forall a \in A, b \in B$, $a < b$, write pseudocode to construct a new BST $C$ that contains all of the elements in $A$ and $B$ (that is, $\forall a \in A$, $a \in C$ and $\forall b \in B$, $b \in C$). Do this in $O(h)$ (worst-case) time, where $h$ is the maximum height between $A$ and $B$.

    > ##### HINT
    > Focus on ensuring that $C$ satisfies the ordering property for BSTs. Both trees are given to you as ordered BSTs, so try to change the structure of $A$ and $B$ as little as possible when merging them.
    {: .block-tip}

#### Graphs
1. Construct a graph which will take up less memory as an adjacency list vs. as an adjacency matrix.

2. Consider a *complete* graph $G = (V, E)$. Being complete means that for any $v_1, v_2 \in V$, $(v_1, v_2) \in E$ (every pair of vertices has an edge connecting them). Suppose the graph in undirected. What is $\|E\|$? That is, how many edges are in $G$? For simplicity, allow for self-edges.

3. What is the smallest $\|E\|$ one can have such that $G = (V, E)$ is *connected*?  

**BONUS**: We can think of trees as a special case of graphs. Two equivalent definitions are (1) an undirected graph that is *connected* and *acyclic* or (2) a graph where any two vertices are connected by exactly 1 path. Convince yourself (and attempt to show, formally) that (1) these definitions match the way we talk about trees and (2) that these two definitions are equivalent. 

#### Submission

Upload to Moodle your work on at least one problem per data structure. Convince yourself that you could solve all the problems here independently (with the exception of the bonus problems) to make sure that you're sufficiently caught up with data structures! 
