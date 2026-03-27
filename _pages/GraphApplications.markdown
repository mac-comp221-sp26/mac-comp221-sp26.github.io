---
layout: post
title: "Graph Applications"
categories: Activity Graph 
---

## Learning Goals

You will work towards being able to...

1. Translate problem specifications into graph problems to be solved with standard algorithms.

## Instructions
Work with your groups on the following problems. You may work on them in any order:

So far, we've spent a lot of time talking about various graph problems (Shortest Paths, MSTs, Max-Flow) and very little time talking about why these problems are so ubiquitous. The goal for this lab is to see a handful of real-world-ish problems and translate them into the language of the algorithms we've seen. This typically involves froming the problem as a graph (as you did in 128!) and choosing the right object (shortest path, MST, max-flow) that corresponds to the solution of the original problem. 


### Problems

#### Problem 1: A Stop Along the Way (Skiena 8-19)
Suppose you have a set of cities and edges representing roads connecting them. Edges are weighted with the travel time between the relevant cities. Determine an algorithm to find the shortest path between city $s$ and city $t$ that makes a stop at city $v$ along the way!

#### Problem 2: Maximizing Utility
Suppose you are a utility company contracted by a local government to connect a collection of houses to the utility grid. You've surveyed the site and determined the cost to connect each pair of buildings, including one that links up to the main grid. You would like to maximize the cost of connecting buildings (since you take a percentage of that cost as profit), but your contract specifies that you won't be paid for redundant connections (connecting two buildings that are otherwises connected through another path in the grid). Find an efficient algorithm to compute the set of building-to-building connects that will maximize the cost to the local government.

### Challenging Problems

These problems will require you to be a bit creative, but can be solved with the algorithms we've seen so far! Sometimes you need to modify an algorithm creatively (say, Prob 3) and sometimes you may need to build a very clever graph (Problem 5). 

#### Problem 3: Two-Tabled Wedding (Skiena 7-15): 
You are organizing seating for a wedding where all guests in a list $V$ must be organized into two tables. You also have a list $E$ of pairs of people who hate each other. Discuss how you might, if possible, construct a table assignment that avoids any enemies being at the same table. What kind of a graph problem is this?

#### Problem 4: Height Limited Shortest Paths (Skiena 8-22)
Suppose you have a set of cities and of roads connecting pairs of cities. For each road, you are told the maximum allowable height of a vehicle navigating that road. Construct an algorithm to find the maximum height of a vehicle that could successfully transit from city $s$ to city $t$.

#### Problem 5: Best Matches
Suppose you would like to assign $n$ tasks to $k$ people. Every person has some number of tasks that they can do, but they can only be assigned to one of them. Every task only needs a single person, so assigning multiple people the same job is useless. You would like to figure out, given this arrangement, the number of jobs that can get done. 

### Submission
Submit an artifact of your work for one of the two problems.

