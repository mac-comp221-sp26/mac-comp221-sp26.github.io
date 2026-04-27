---
layout: post
title: "Activity: Computational Complexity Lab"
categories: Activity NP NP=hard P complexity
---

## Learning Goals

You will work towards being able to...

1. Prove that problems are in P or NP.

2. Prove that problems are NP-Hard and NP-Complete using reductions

3. Recall and state canonical NP-Complete Problems

## Activity
For each of the following questions, show that the problem in NP (by providing a polynomial time verifier) and that the problem is NP-Hard (by providing and briefly justifying a reduction from a known NP-Hard problem). 

Do them in any order!

### Preliminaries

Re-familiarize yourself with the following problems: SAT, 3-SAT, Hamiltonian Cycle, Independent Set, Vertex Cover, Clique, and Subset Sum. 

### Dense Subgraph

**Problem** (*Dense Subgraph*): \\
**Input**: A Graph $G = (V, E)$, Integers $k$, $y$ \\
**Output**: True if there exists a subgraph $G' = (V', E')$ of $G$ where $\lvert V' \rvert = k$ and $\lvert E' \rvert \geq y$. 

Prove that the Dense Subgraph problem is NP-Complete. 

### (Integer) Partition

**Problem**: (*Partition*) \\ 
**Input**: A multiset of integers $S$ \\
**Output**: True if there exists a partition of $S$ into $S_1, S_2$ such that $\sum_{s \in S_1} s = \sum_{s \in S_2}$.

Prove that the Partition problem is NP-Complete. 

### Double SAT

**Problem**: (*Double SAT*) \\
**Input**: A boolean formula $\phi$ \\
**Output**: True if there are two unique satisfying assignments for $\phi$. 

Prove that the Double SAT problem is NP-Complete. 

### Kite 

**Problem**: (*Kite*) \\ 
**Input**: A graph $G$, Integer $k$ \\
**Output**: True if there exists a subgraph that forms a *kite* of size $k$ --- a clique of size $k$ with a "tail" of $k$ nodes in a chain. 

Prove that the Kite problem is NP-Complete. 

#### Submission

Submit some artifact of your work to Moodle.

