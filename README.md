# Data-structure-and-algorithm

1. [BIG O](#big-o)
2. [Arrays](#arrays)
3. [Hash Tables](#hash-tables)
4. [Linked Lists](#linked-list)
5. [Stacks + Queues](#stacks-queues)
6. [Trees](#tree)
7. [Graphs](#graphs)
8. [Recursion](#recursion)
9. [Sorting](#sorting)
10. [Searching + BFS + DFS](#searching-bfs-dfs)
11. [Dynamic Programming](#dynamic-programming)

- [Resources](#resources)

### BIG O

### What is a good code?

- Readable
- Scalable == memory && speed

  **scalable?** - Speed at which a code runs and its memory usage.

  **memory === space complexity**

  **speed === time complexity**

**BIG O:** Is used to determine how long an algorithm takes to run/execute. || Big O notation is used to classify algorithms according to how their run time or space requirements grow as the input size grows

**run time?** - Simply how long a function/task takes to run.

### Big Os

```
1. O(1) Constant Time- no loops
2. O(log N) Logarithmic- usually searching algorithms have log n if they are sorted (Binary Search)
3. O(n) Linear Time- for loops, while loops through n items
4. O(n log(n)) Log Liniear- usually sorting operations
5. O(n^2) Quadratic Time- every element in a collection needs to be compared to ever other element. Two
   nested loops
6. O(2^n) Exponential- recursive algorithms that solves a problem of size N
7. O(n!) Factorial- you are adding a loop for every element

   **Iterating through half a collection is still O(n)**

   **Two separate collections: O(a\*b)**
```

**What is the difference between big oh, big omega and big theta notations?**

```
What is the mileage that your car gives?

So let's discuss different scenarios.

Let's say the car gives an average of 12 km/hr in Traffic, an average of 20 km/hr on Highway and an average of 16 km/hr in Normal City Traffic.

Traffic is your worst case, Highway is your best case and Normal City Traffic is your average case.

This is similar to the notations that we use for Algorithm runtime Analysis.

Omega Notation ( Ω ) gives the best case complexity (highway in above case), Big O Notation ( O ) gives the worst case complexity (traffic in above case) and Theta Notation ( θ ) gives the average case complexity of an algorithm (normal city traffic in above case).
```

### Rule Book

```
BIG O == Worst Case
```

Four rules to follow to determine BIG O.

1.  Rule 1: Always worst Case scenarios
2.  Rule 2: Remove Constants
3.  Rule 3: Different inputs should have different variables. O(a+b). A and B arrays nested would be
    O(a\*b)

    \- for steps in order

    \* for nested steps

4.  Rule 4: Drop Non-dominant terms

### What can cause time in a function?

1.  Operations (+, -, \*, /)
2.  Comparisons (<, >, ==)
3.  Looping (for, while)
4.  Outside Function call (function())

### What causes Space complexity?-

1. Variables
2. Data Structures
3. Function Call
4. Allocations

**BIG O COMPLEXITY CHART**

[Know thy complexities](https://www.bigocheatsheet.com/)

Below is the list of some of the most used Big O notations and their performance comparisons against different sizes of the input data.

| Big O Notation | Type        | Computations for 10 elements | Computations for 100 elements | Computations for 1000 elements |
| -------------- | ----------- | ---------------------------- | ----------------------------- | ------------------------------ |
| **O(1)**       | Constant    | 1                            | 1                             | 1                              |
| **O(log N)**   | Logarithmic | 3                            | 6                             | 9                              |
| **O(N)**       | Linear      | 10                           | 100                           | 1000                           |
| **O(N log N)** | n log(n)    | 30                           | 600                           | 9000                           |
| **O(N^2)**     | Quadratic   | 100                          | 10000                         | 1000000                        |
| **O(2^N)**     | Exponential | 1024                         | 1.26e+29                      | 1.07e+301                      |
| **O(N!)**      | Factorial   | 3628800                      | 9.3e+157                      | 4.02e+2567                     |

### Data Structure Operations Complexity

| Data Structure         | Access | Search | Insertion | Deletion | Comments                                             |
| ---------------------- | :----: | :----: | :-------: | :------: | :--------------------------------------------------- |
| **Array**              |   1    |   n    |     n     |    n     |                                                      |
| **Stack**              |   n    |   n    |     1     |    1     |                                                      |
| **Queue**              |   n    |   n    |     1     |    1     |                                                      |
| **Linked List**        |   n    |   n    |     1     |    n     |                                                      |
| **Hash Table**         |   -    |   n    |     n     |    n     | In case of perfect hash function costs would be O(1) |
| **Binary Search Tree** |   n    |   n    |     n     |    n     | In case of balanced tree costs would be O(log(n))    |
| **B-Tree**             | log(n) | log(n) |  log(n)   |  log(n)  |                                                      |
| **Red-Black Tree**     | log(n) | log(n) |  log(n)   |  log(n)  |                                                      |
| **AVL Tree**           | log(n) | log(n) |  log(n)   |  log(n)  |                                                      |
| **Bloom Filter**       |   -    |   1    |     1     |    -     | False positives are possible while searching         |

### Array Sorting Algorithms Complexity

| Name               |     Best      |         Average         |            Worst            | Memory | Stable | Comments                                                      |
| ------------------ | :-----------: | :---------------------: | :-------------------------: | :----: | :----: | :------------------------------------------------------------ |
| **Bubble sort**    |       n       |      n<sup>2</sup>      |        n<sup>2</sup>        |   1    |  Yes   |                                                               |
| **Insertion sort** |       n       |      n<sup>2</sup>      |        n<sup>2</sup>        |   1    |  Yes   |                                                               |
| **Selection sort** | n<sup>2</sup> |      n<sup>2</sup>      |        n<sup>2</sup>        |   1    |   No   |                                                               |
| **Heap sort**      | n&nbsp;log(n) |      n&nbsp;log(n)      |        n&nbsp;log(n)        |   1    |   No   |                                                               |
| **Merge sort**     | n&nbsp;log(n) |      n&nbsp;log(n)      |        n&nbsp;log(n)        |   n    |  Yes   |                                                               |
| **Quick sort**     | n&nbsp;log(n) |      n&nbsp;log(n)      |        n<sup>2</sup>        | log(n) |   No   | Quicksort is usually done in-place with O(log(n)) stack space |
| **Shell sort**     | n&nbsp;log(n) | depends on gap sequence | n&nbsp;(log(n))<sup>2</sup> |   1    |   No   |                                                               |
| **Counting sort**  |     n + r     |          n + r          |            n + r            | n + r  |  Yes   | r - biggest number in array                                   |
| **Radix sort**     |    n \* k     |         n \* k          |           n \* k            | n + k  |  Yes   | k - length of longest key                                     |

---

### Arrays

---

### Hash Tables

---

### Linked Lists

---

### Stacks + Queues

---

### Trees

---

### Graphs

---

### Recursion

---

### Sorting

---

### Searching + BFS + DFS

---

### Dynamic Programming

---

### Resources

[ :notebook: DATA STRUCTURE VISUALIZATION](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html)

[ :black_nib: Data Structure sketches](https://okso.app/showcase/data-structures)

[ :bookmark: Edabit](https://edabit.com/challenges/javascript)
