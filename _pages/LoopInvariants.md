---
layout: post
title:  "Loop Invariants and Asserts in Code"
categories: Supplement Loop Invariant Assert
---


When learning about loop invariants, it may be helpful to see how they correspond to their equivalent `assert`-ions in code. That's what this document aims to do, in Python (the closest thing to pseudocode one can get!). 


```python
import numpy as np # This gives us real arrays in Python
```

First, let's implement insertion sort as close to our pseudocode as possible:


```python
def insertionSort(arr : np.array) -> None:
    for i in range(1, len(arr)):
        j : int = i
        while (j > 0) and (arr[j] < arr[j-1]): 
            # Swap!
            temp = arr[j]
            arr[j] = arr[j-1]
            arr[j-1] = temp
            j -= 1
```

Now let's spot check that the algorithm works on some input:


```python
A = np.array([5,4,3,2,1])
print("Before:\t\t", A)
insertionSort(A)
print("After:\t\t", A)
```

    Before:		 [5 4 3 2 1]
    After:		 [1 2 3 4 5]


Good!

Now, our goal is to determine the reality of our loop invariant, so we must inspect the behavior of the algorithm on every loop iteration. We ask ourselves: *How does this algorithm make progress in each iteration of the loop?* Additionally, *How can I formally declare that progress is being made?*

Let's add a print statement to track the state of the array after each iteration of the outer for-loop to take a look:


```python
def insertionSort(arr : np.array) -> None:
    for i in range(1, len(arr)):
        j : int = i
        while (j > 0) and (arr[j] < arr[j-1]): 
            # Swap!
            temp = arr[j]
            arr[j] = arr[j-1]
            arr[j-1] = temp
            j -= 1
        print("At i = {},\t {}".format(i, arr))
```


```python
A = np.array([5,4,3,2,1]) # Worst-case input!

print("Before:\t\t", A)
insertionSort(A)
print("After:\t\t", A)
```

    Before:		 [5 4 3 2 1]
    At i = 1,	 [4 5 3 2 1]
    At i = 2,	 [3 4 5 2 1]
    At i = 3,	 [2 3 4 5 1]
    At i = 4,	 [1 2 3 4 5]
    After:		 [1 2 3 4 5]


Now, inspect the output and...

### LI 1: Construct a statement $P(n)$ that is true after the iteration where $i=n$

That is an *invariant* that is true after every *loop* iteration: A **Loop Invariant!**. Here, we note that we're building a *sorted subarray from the left edge that grows with each step: *After iteration $i$, `arr[i]` is sorted*. 

Now to show that this loop invariant is true, we have to understand that insertion operation happening in each iteration. It's helpful to decompose our insertion sort into two pieces: The part the performs the insert and the loop that repeatedly inserts. Let's rewrite with this decomposition and more print statements:


```python
def insert(arr : np.array, i : int):
    """ inserts arr[i] into it's sorted position in arr[:i+1]

    Precondition: arr[:i] is sorted
    Postcondition: arr[:i+1] is sorted """

    j : int = i # preserve the value of i 
    
    while (j > 0) and (arr[j] < arr[j-1]): 
        # Swap!
        temp = arr[j]
        arr[j] = arr[j-1]
        arr[j-1] = temp
        j -= 1
        print("\t After j = {}, \t arr[:i+1] = \t{}"
              .format(j, arr[:i+1]))

def insertionSort(arr : np.array) -> None:
    for i in range(1, len(arr)):
        print("\ni = {}".format(i))
        insert(arr, i)
        print("\nAfter i = {},\t\t arr = \t\t{}"
              .format(i, arr))
```


```python
A = np.array([5,4,3,2,1]) # Worst-case input!

print("Before:\t\t\t\t\t{}".format(A))
insertionSort(A)
print("After:\t\t\t\t\t{}".format(A))
```

    Before:					[5 4 3 2 1]
    
    i = 1
    	 After j = 0, 	 arr[:i+1] = 	[4 5]
    
    After i = 1,		 arr = 		[4 5 3 2 1]
    
    i = 2
    	 After j = 1, 	 arr[:i+1] = 	[4 3 5]
    	 After j = 0, 	 arr[:i+1] = 	[3 4 5]
    
    After i = 2,		 arr = 		[3 4 5 2 1]
    
    i = 3
    	 After j = 2, 	 arr[:i+1] = 	[3 4 2 5]
    	 After j = 1, 	 arr[:i+1] = 	[3 2 4 5]
    	 After j = 0, 	 arr[:i+1] = 	[2 3 4 5]
    
    After i = 3,		 arr = 		[2 3 4 5 1]
    
    i = 4
    	 After j = 3, 	 arr[:i+1] = 	[2 3 4 1 5]
    	 After j = 2, 	 arr[:i+1] = 	[2 3 1 4 5]
    	 After j = 1, 	 arr[:i+1] = 	[2 1 3 4 5]
    	 After j = 0, 	 arr[:i+1] = 	[1 2 3 4 5]
    
    After i = 4,		 arr = 		[1 2 3 4 5]
    After:					[1 2 3 4 5]


### LI 2: Construct a statement $P(n)$ that is true after the iteration where $j=n$ (for a fixed $i$)

Create *another* loop invariant for a call to `insert`! 

After the iterations where $j=n$, we have that `arr[j:i+1]` is sorted! But this isn't all (as we've seen in the proof of correctness): we know that `arr[1:j]` is also sorted (it began sorted and hasn't been touched!), and we know that all elements in `arr[1:j]` are less than elements in `arr[j+1:i+1]` (these are the elements of the initially sorted subarray we moved to the right of the element we're inserting!).


All we've done is inspect a couple of outputs of the algorithm to make a claim about the code (namely, we claim that our two loop invariants hold!). This is identical to the process to arrive at the claims we make about the pseudocode, except instead of working through examples by hand, we're running through real code!

One fun thing that we can do in code is *enforce* our loop invariants through programming constructs like `assert`, which will throw an error if it's argument evaluates to `false`. Here is one way of encoding our loop invariant into code:


```python
def isSorted(arr : np.array, i : int, j : int):
    """ Returns True if arr[i:j+1] (i.e., A[i...j]) is sorted.
    """
    for k in range(i, j-1):
        if arr[k] > arr[k+1]: return False
    return True

def arrSmaller(arr1 : np.array, arr2 : np.array):
    for e in arr1:
        for f in arr2:
            if f < e: return False
    return True

def insert(arr : np.array, i : int):
    """ inserts arr[i] into it's sorted position in arr[:i+1]

    Precondition: arr[:i] is sorted
    Postcondition: arr[:i+1] is sorted 
    """

    j : int = i # preserve the value of i 
    
    while (j > 0) and (arr[j] < arr[j-1]): 
        # Swap!
        temp = arr[j]
        arr[j] = arr[j-1]
        arr[j-1] = temp
        j -= 1
        assert (isSorted(arr, j, i+1) and 
                isSorted(arr, 1, j) and
                arrSmaller(arr[:j],arr[j+1:i+1])), "Insert LI False" 

def insertionSort(arr : np.array) -> None:
    for i in range(1, len(arr)):
        insert(arr, i)
        assert isSorted(arr, 0, i+1), "insertionSort LI False" 
```

And now we can show that these invariants are true for our sample (worst-case) input of length 5.


```python
A = np.array([5,4,3,2,1]) # Worst-case input!

print("Before:\t\t", A)
insertionSort(A)
print("After:\t\t", A)
```

    Before:		 [5 4 3 2 1]
    After:		 [1 2 3 4 5]


However, we can't show that our loop invariant holds true for all inputs (for the same reason that testing can't show that our algorithm is *correct* on all inputs through testing). We can, however, convince ourselves that it holds true for a random sample of inputs: Here we have our 2 LI asserts + a correctness assert going for 10 random arrays for each array size from 2 to 100: We get no assert failures!


```python
for _ in range(10):
    for n in range(2, 50):
        A = np.random.rand(n)
        insertionSort(A)
        assert (isSorted(A, 0, len(A))), "Sorting Failed"
```

But we should convince ourselves that `assert` does actually do something! 


```python
A = np.array([5,4,3,2,1])
assert isSorted(A,0, 4), "This error message should appear"
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    Cell In[48], line 2
          1 A = np.array([5,4,3,2,1])
    ----> 2 assert isSorted(A,0, 4), "This error message should appear"


    AssertionError: This error message should appear


And it does! The error message appears!
