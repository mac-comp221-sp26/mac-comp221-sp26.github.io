---
title: COMP221 - Algorithm Design & Analysis (Spring 2026) 
author: Suhas Arehalli
category: Syllabus
layout: post
---

Welcome to the COMP221 (Algorithm Design & Analysis) Course Page. For course policies, please check the [syllabus](https://docs.google.com/document/d/1PG1b4zjEanR0XgWdJeIcvYNZT_LwgkeP0a0kTatZBlY/edit?usp=sharing).

### Resources

#### Office Hours
Me and the preceptors will hold OH from the 2nd week of the semester onward. Times can be found [in this google calendar](https://calendar.google.com/calendar/u/0?cid=Y183Y2IzMjliOTYxY2ZlM2YyNDZmZDBkNzQzNmM4OTE4YWI2OWEyZTY4MTBiNGU1MjAwNWU1MjUxM2ExNzdkYTIyQGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20). If posted times don't work for you, please email me and we can schedule a separate meeting!

#### Textbook
Our primary text this semester will be *Algorithms* by Jeff Erickson, which is freely accessible [here](https://jeffe.cs.illinois.edu/teaching/algorithms/). There will occasionally be a reading from me or another source which will be linked below. 

Note that many of the readings (particularly the ones early on) suggest skimming or previewing my lecture notes ahead of time. You are meant to see the materials multiple times from multiple perspectives, and my notes are more thorough (and often more tedious) than what I can reasonably get through in lecture, so you should (even when not explicitly asked) look ahead to my notes and identify areas where you need more clarity in-class.

For additional reference, I recommend...

 - *The Algorithm Design Handbook* by Steve Skiena, which we used in prior semesters. This book focuses more on implementation details and practical design tips.
 - *Introduction to Algorithms* by Cormen, Leiserson, Rivest, \& Stein (colloquially called CLRS). This book prioritizes formal, rigorous analysis and is a bit dense.

For background material on the formal mathematical tools we'll be using, you should reference your notes and textbook from Discrete Mathematics first. In addition, I recommend (and will have you read from) 

 - *Building Blocks for Theoretical Computer Science* by Margaret M. Fleck, available online [here](https://mfleck.cs.illinois.edu/building-blocks/). I will link to version 1.3b simply because of it's pdf format.

### Schedule
The schedule below will be updated to keep track of all released course materials. Keep in mind that I may shift planned topics to adjust pace.

<div class="table-wrapper" markdown="block">

| Week | Date | Topic | Reading | Materials |
| :-: | :- | :- | -: | :- |
| 0 | FRI 1/23 | No Class  | [Syllabus](https://docs.google.com/document/d/1PG1b4zjEanR0XgWdJeIcvYNZT_LwgkeP0a0kTatZBlY/edit?usp=sharing) | |
| 1 | MON 1/26 | Mathematical Foundations (RAM Model & Proofs) | Skim [Fleck Ch.1](https://mfleck.cs.illinois.edu/building-blocks/updates-fa2017/math-review.pdf), [Fleck Ch.3](https://mfleck.cs.illinois.edu/building-blocks/version-1.3/proofs.pdf), [Proof-Writing Guide]({{site.url}}/notes/ProofGuide.pdf)  | [Beginning-of-Semester Survey](https://docs.google.com/forms/d/e/1FAIpQLSd7l7ye6QqFnSu00eHDEMFnGW79RjScoR8KGFHErKsa-CnPMQ/viewform?usp=publish-editor)  |
| - | WED 1/28 | Big-O(h) Analysis  | \*[Fleck 14.1, 14.5--14.8](https://mfleck.cs.illinois.edu/building-blocks/updates-fa2017/big-o.pdf), skim [Time Complexity Notes]({{site.url}}/notes/TimeComplexity.pdf) | |
| - | FRI 1/30 | Big-O(h) Analysis Lab  | -  | [Activity: Sorting](pages/ActivitySort)  |
| 2 | MON 2/02 | Proofs of Correctness (Iteration/Loop Invariants) | \*CLRS 2.1 (Moodle), Preview [Loop Invariants Notes]({{site.url}}/notes/CorrectnessAndLoopInvariants.pdf)  | [Loop Invariants and Assertions](pages/LoopInvariants) [Tao on rigor](https://terrytao.wordpress.com/career-advice/theres-more-to-mathematics-than-rigour-and-proofs/)  |
| - | WED 2/04 | Proofs of Correctness (Recursion) | Skim [Recursive Correctness Notes]({{site.url}}/notes/CorrectnessRecursion.pdf)  |  |
| - | FRI 2/06 | Proofs of Correctness Lab  | -  | [Activity: Sorting 2](pages/ActivityLoopInv) |
| 3 | MON 2/09 | Revisiting Data Structures (Trees & Self-Balancing) | Preview [DS Notes]({{site.url}}/notes/DataStructures.pdf) on AVL Trees  | |
| - | WED 2/11 | Revisiting Data Structures (Array Stack & Amortization) | Preview [DS Notes]({{site.url}}/notes/DataStructures.pdf) on Amortization |   |
| - | FRI 2/13 | Sorting: (Heap-/Tree- Sorts) |   | [Activity: DS Sort Activity](pages/ActivityHS)
| 4 | MON 2/16 | Sorting: MergeSort | \*Erickson 1.4, Preview [MergeSort Notes]({{site.url}}/notes/MergeSort.pdf) |  |
| - | WED 2/18 | Sorting: QuickSort | \*Erickson 1.5, Preview [QuickSort Notes]({{site.url}}/notes/QuickSort.pdf) | [Optional Activity: Partition and Quicksort](pages/ActivityQS) |
| - | FRI 2/20 | **Exam 1** |  | |
| 5 | MON 2/23 | Divide & Conquer (Binary Search) | Erickson 1.6 | [Activity: Binary Search Variants](pages/ActivityBS) [Binary Search Notes]({{site.url}}/notes/BinarySearch.pdf) |
| - | WED 2/25 | The Master Theorem | \*Erickson 1.7, Preview [Master Theorem Notes]({{site.url}}/notes/MasterThm.pdf) | [Activity: Master Theorem](pages/ActivityMT) | 
| - | FRI 2/27 | More Divide & Conquer Design  | Erickson 1.9--1.10 | [Activity: Divide & Conquer](pages/ActivityDC) |
| 6 | MON 3/02 | Greedy Algorithms | Erickson 4.1--4.3 | |
| - | WED 3/04 | Graphs: BFS | Skim Erickson 5.1--5.4, Then \*Erickson 8.1--8.4  | [BFS  Notes]({{site.url}}/notes/BFS.pdf)  |
| - | FRI 3/06 | **Capstones** | | |
| 7 | MON 3/09 | SSSP: Dijkstra's | Erickson 8.6 + Skim [Dijkstra Notes]({{site.url}}/notes/Dijkstra.pdf) | |
| - | WED 3/11 | MSTs: Prims | \*Erickson 7.1--7.2, 7.4, Preview [MST  Notes]({{site.url}}/notes/MSTs.pdf) on Prim's | |
| - | FRI 3/13 | MSTs: Kruskal's & Union-Find | Erickson 7.5, Preview [MST Notes]({{site.url}}/notes/MSTs.pdf) on Kruskal's | |
| 8 | - | **SPRING BREAK** | | |
| 9 | MON 3/23 | APSP: Floyd-Warshall | Erickson 9.1--9.2, 9.8 | |
| - | WED 3/25 | Max-Flow = Min-Cut | \*Erickson 10.1 -- 10.3 | [Ford-Fulkerson Notes]({{site.url}}/notes/NetworkFlow.pdf) |
| - | FRI 3/27 | Ford-Fulkerson | 10.4 -- 10.6 | |
| 10 | MON 3/30 | Flex Day | | [Graph Application Activity](pages/GraphApplications) |
| - | WED 4/01 | **Exam 2** | | |
| - | FRI 4/03 |  Backtracking & Combinatorial Search | Erickson 2.1--2.4 | |
| 11 | MON 4/06 | Dynamic Programming | Erickson 3.1--3.4 | [Dynamic Programming Activity 1]({{site.url}}/pages/ActivityDP1) |
| - | WED 4/08 | Approximate String Match | \*Erickson 3.7 |  |
| - | FRI 4/10 | Subset Sum | Erickson 3.8 | |                                                                      
| 12 | MON 4/13 | CKY Parsing | TBD  | [Dynamic Programming Notes]({{site.url}}/notes/DynamicProgramming.pdf) |           
| - | WED 4/15 | Dynamic Programming Lab | | [Dynamic Programming Activity 2]({{site.url}}/pages/ActivityDP2) | 
| - | FRI 4/17 | Intro to Complexity Theory | Erickson 12.1--12.3 | |
| 13 | MON 4/20 | Reduction as a Proof Technique | \*Erickson 12.5--12.6 | |
| - | WED 4/22 | More NP Reductions | \*Erickson 12.6--12.9 | |
| - | FRI 4/24 | Flex Day | | |
| 14 | MON 4/27 | Complexity Lab | Erickson 12.13--12.14 | [Complexity Theory Notes]({{site.url}}/notes/ComplexityTheoryAndReductions.pdf) |
| - | WED 4/29 | Approximate/Random Methods for Hard Problems | TBD | |
| - | FRI 5/01 | Report Peer Review   | | |
| 15 | MON 5/04 | **Exam 3** | | |
| FINALS | THU 5/07 <br> 1:30--3:30pm | Section 01 Final | | |
| FINALS | FRI 5/08 <br> 4:00--6:00pm | Section 02 Final | | |

</div> 
\*s indicate the presence of an assigned reading problem. Enrolled students should see the Moodle to complete the problem before classtime.

### Homeworks
Solutions for written assignments should be submitted through Moodle. Solutions for programming assignments should be submitted through the Github Classroom, which can be joined through Moodle. 

#### Homework 0
The goal of this assignment is to review material from Data Structures and Discrete Math.

**Out:** Mon. 1/26
**Due:** Mon. 2/02 9pm on Moodle

[Instructions]({{site.url}}/hws/COMP221_HW0.pdf) | [Tex]({{site.url}}/hws/COMP221_HW0.tex)

#### Homework 1
This assignment evaluates your ability to prove Big-$O/\Omega/\Theta$ by definition with some degree of abstraction. I recommend working through examples with specific coefficients/etc. if you feel stuck.

**Out:** Tue. 2/3
**Due:** Mon. 2/9 9pm on Moodle

[Instructions]({{site.url}}/hws/COMP221_HW1.pdf) | [Tex]({{site.url}}/hws/COMP221_HW1.tex)

#### Homework 2
This assignment evaluates your ability to prove the correctness of iterative and recursive algorithms. Spend time working through the algorithm on various examples before trying to start writing a proof!

**Out:** Tue. 2/10
**Due:** Mon. 2/16 9pm on Moodle

[Instructions]({{site.url}}/hws/COMP221_HW2.pdf) | [Tex]({{site.url}}/hws/COMP221_HW2.tex)
