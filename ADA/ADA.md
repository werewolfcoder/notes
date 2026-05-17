![[Pasted image 20251201230615.png]]


- **Constants don't matter:** $O(2n) \rightarrow O(n)$.
    
- **Addition:** $O(n) + O(n) \rightarrow O(n)$.
    
- **Big-O ($O$):** "$\le$" (Can be equal growth).
    
- **Little-o ($o$):** "$<$" (Must be strictly slower growth).


| **Notation**  | **Symbol** | **Meaning**         | **Mathematical Sign** |
| ------------- | ---------- | ------------------- | --------------------- |
| **Big Oh**    | $O$        | Upper Bound (Worst) | $\le$                 |
| **Big Omega** | $\Omega$   | Lower Bound (Best)  | $\ge$                 |
| **Theta**     | $\Theta$   | Tight Bound (Exact) | $\le$ AND $\ge$       |
![[WhatsApp Image 2025-12-01 at 23.04.44_006a1cc2.jpg]]
# Linear inequalities

A **Linear Inequality** is a mathematical sentence that compares two linear expressions (equations that would make straight lines) using symbols like 1$<$, 2$>$, 3$\le$, or 4$\ge$ instead of an equals sign (5$=$).6

In plain English: It's a way of saying **"The value on this side is not just equal to, but definitely bigger or smaller than the value on that side."7**

---

### 2. The Formal Breakdown

To technically count as a "Linear Inequality," it must meet two strict conditions:

#### **A. It must be "Linear" (Degree 1)**8

This means the variables ($x$, $y$, etc.) represent straight lines.

- **Allowed:** $x$, $y$, $2x$, $5y$, $a$, $b$. (Power is 1).9
    
- **NOT Allowed:** $x^2$ (Quadratic), $x^3$, $\sqrt{x}$, or $\frac{1}{x}$.
    
- **Why?** Because "Linear" comes from "Line." If you graph $x^2$, you get a curve (parabola), so it's not linear anymore.
    

#### **B. It must be an "Inequality"**

It cannot use an equals sign (10$=$).11 It must use one of the inequality symbols (12$<, >, \le, \ge$)





# Amortized analysis

**Amortized Analysis** is a way of calculating the time complexity that focuses on the **average time per operation over a sequence of operations**.1

It is used when an algorithm is generally very fast, but every once in a while, it hits a "slow" operation that takes a long time.2 Amortized analysis allows us to "spread out" that one expensive cost over all the cheap operations to show that the algorithm is actually efficient in the long run.3

> The "Rent" Analogy:
> 
> Imagine you pay $12,000 once a year for rent.
> 
> - **Worst Case View:** "Oh my god, you paid $12,000 today! That is incredibly expensive!"
>     
> - **Amortized View:** "Actually, if you spread that cost over the year, you are paying **$1,000 per month**. That is your 'amortized' cost."
>     

---

### Why do we need it?

We need Amortized Analysis because standard **Worst-Case Analysis** (4$O$) can be **too pessimistic** and misleading for certain data structures.5

If you have an algorithm that runs in $O(1)$ (instant) time for 99.9% of the cases, but takes $O(N)$ time for 0.1% of the cases, calling the whole thing "$O(N)$" (Worst Case) is technically true but doesn't reflect reality. It makes a great algorithm look bad.

Amortized analysis gives us a tighter, more realistic upper bound.6

---

### The Classic Example: Dynamic Array (Vector)

The most famous example of this is the **Dynamic Array** (like `std::vector` in C++ or `ArrayList` in Java).7

1. The "Cheap" Operation (Normal Insert):

When you push an element into a vector, and there is empty space, it just puts the number in.

- **Cost:** $O(1)$.
    

2. The "Expensive" Operation (Resize):

When the vector is full, it must expand.8 It creates a new array double the size and copies all existing elements over.9

- **Cost:** $O(N)$ (because it has to move $N$ items).
    

The Problem:

If we used normal Worst-Case analysis, we would say "Insertion into a vector takes $O(N)$ time" because that resizing could happen. But this is misleading because resizing happens very rarely.10

The Amortized Solution:

Mathematics proves that if you double the array size every time it fills up, the "expensive" copying cost is rare enough that it gets "absorbed" by the cheap operations.11

- If you insert $N$ elements, the total work done is roughly $2N$ or $3N$ operations.
    
- Dividing total work (12$3N$) by the number of elements (13$N$) gives you **3**.14
    
- Therefore, the **Amortized Complexity** is **$O(1)$**.
    

### Amortized vs. Average Case

This is a common point of confusion. They sound the same, but they are different:

| **Feature**    | **Amortized Analysis**                                                                   | **Average Case Analysis**                                                       |
| -------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Input Data** | **Deterministic.** We assume the worst possible _sequence_ of operations.                | **Random.** We assume the input data follows a random probability distribution. |
| **Guarantee**  | **Hard Guarantee.** The average cost _will_ be this low, no matter what inputs you give. | **Soft Expectation.** It _should_ be this low, assuming the data is random.     |
| **Example**    | `vector::push_back` (Vector expansion)                                                   | `QuickSort` (Pivot selection depends on luck)                                   |



# Loop invariant 

A **Loop Invariant** is a condition (statement) about the relationship between variables that is **always true** just before and after each iteration of a loop. It is the key mathematical tool used to prove the correctness of an algorithm.

#### 2. The Three-Step Proof (IMT)

To prove an algorithm works, you must verify the invariant at three stages:

- **I - Initialization (Base Case):**
    
    - The invariant must be true **before** the first iteration of the loop starts.
        
    - _Significance:_ Ensures the algorithm starts in a correct state.
        
- **M - Maintenance (Inductive Step):**
    
    - If the invariant is true before iteration $i$, it remains true before iteration $i+1$.
        
    - _Significance:_ Ensures the loop logic doesn't break the correctness as it processes data.
        
- **T - Termination (Conclusion):**
    
    - When the loop ends, the invariant (combined with the reason the loop stopped) gives a property that shows the algorithm is correct.
        
    - _Significance:_ Proves the final answer is the right one.
        

#### 3. Example: Selection Sort (Finding Minimum)

- **Loop:** `for i from 0 to n-1`
    
- **Invariant:** "At the start of iteration `i`, the subarray `A[0...i-1]` consists of the `i` smallest elements in sorted order."
    
- **Check:**
    
    - _Init:_ $i=0$. Subarray is empty. Trivially sorted. (True)
        
    - _Maint:_ We find the min in the rest of the array and swap it to `i`. Now `A[0...i]` is sorted. (True)
        
    - _Term:_ Loop ends at `i=n`. `A[0...n-1]` contains all smallest elements sorted. (True)




# Bubble sort

Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This pass through the list is repeated until the list is sorted.

- _Name Origin:_ Smaller elements "bubble" to the top of the list (or larger elements sink to the bottom) like air bubbles in water.
    

#### 2. How it Works (Algorithm)

1. Start at the beginning of the array.
    
2. Compare the first element with the second element.
    
3. If the first is greater than the second, **swap** them.
    
4. Move to the next pair (2nd and 3rd) and repeat.
    
5. After one full pass, the largest element is guaranteed to be at the end.
    
6. Repeat the process for the remaining unsorted elements ($N-1$ times).
    

#### 3. Time & Space Complexity

|**Case**|**Complexity**|**Condition**|
|---|---|---|
|**Best Case**|**$O(n)$**|Array is already sorted (requires "swapped" flag optimization).|
|**Average Case**|**$O(n^2)$**|Elements are in random order.|
|**Worst Case**|**$O(n^2)$**|Array is reverse sorted.|
|**Space Complexity**|**$O(1)$**|It is an **In-Place** sorting algorithm (requires almost no extra memory).|

#### 4. Stability

- **Stable:** Yes. It does **not** change the relative order of elements with equal values (it only swaps if the left is _strictly_ greater than the right).
    

#### 5. Pros & Cons

- **Pros:** Very easy to implement; good for detecting if a list is already sorted.
    
- **Cons:** Very slow for large datasets. Generally outperformed by Insertion Sort for small data and Quick/Merge Sort for large data.






# Selection sort

Selection sort works by repeatedly **finding the minimum element** (considering ascending order) from the unsorted part of the list and putting it at the beginning.

- It divides the array into two parts: **Sorted** (left) and **Unsorted** (right).
    
![[Pasted image 20251201161715.png]]
#### 2. Algorithm Steps

1. Set `min_index` to the first element of the unsorted section.
    
2. Iterate through the unsorted array to find the actual smallest element.
    
3. **Swap** the found minimum element with the element at `min_index`.
    
4. Move the boundary of the sorted section one step to the right.
    
5. Repeat until the array is sorted.
    

#### 3. Complexity Analysis

- **Time Complexity:** **$O(n^2)$** in **ALL** cases (Best, Average, and Worst).
    
    - _Why?_ Even if the array is sorted, it scans the remaining list every time to ensure there isn't a smaller element.
        
- **Space Complexity:** **$O(1)$** (In-place sort).
    

#### 4. Key Characteristics

- **Not Stable:** It changes the relative order of equal elements (e.g., swapping a `5` from the start might move it behind another `5`).
    
- **Minimal Swaps:** It performs exactly **$O(n)$** swaps (at most one swap per pass). This is useful if writing to memory is expensive.






# Insertion sort

Insertion Sort builds the final sorted array one item at a time.

- **Analogy:** It works exactly like **sorting playing cards in your hand**. You pick up a card and insert it into its correct position among the cards you are already holding.
    

#### 2. Algorithm Steps

1. Assume the first element is already "sorted".
    
2. Take the next element (the **key**).
    
3. Compare the **key** with elements in the sorted sub-list (moving backwards).
    
4. **Shift** (don't swap) all elements greater than the key one position to the right to create space.
    
5. **Insert** the key into the correct empty slot.
    
6. Repeat.
    

#### 3. Complexity Analysis

- **Best Case:** **$O(n)$**
    
    - _Condition:_ The array is **already sorted**. The inner loop never runs; it just makes one comparison per element.
        
- **Average & Worst Case:** **$O(n^2)$**
    
    - _Condition:_ Array is reverse sorted or random.
        
- **Space Complexity:** **$O(1)$** (In-place).
    

#### 4. Key Characteristics

- **Stable:** Yes (Doesn't change relative order of duplicates).
    
- **Adaptive:** Yes (It is very fast for data that is **already substantially sorted**).
    
- **Online:** Yes (It can sort a list as it receives it, element by element).
![[Pasted image 20251201161640.png]]


# Shell sort

Shell Sort is an **optimization of Insertion Sort**.

- Standard Insertion Sort is slow when elements are far apart (it only moves items 1 step at a time).
    
- Shell Sort allows the exchange of items that are **far apart** first, then reduces the gap between elements to finish the sort.
    
- It is also known as **Diminishing Increment Sort**.
    

#### 2. Algorithm Steps

1. **Choose a Gap:** Start with a large gap (usually $n/2$).
    
2. **Compare & Swap:** Compare elements that are `gap` distance apart. If they are in the wrong order, swap them. (Essentially performing Insertion Sort on these sub-lists).
    
3. **Shrink Gap:** Reduce the gap (usually divide by 2: $gap = gap / 2$).
    
4. **Repeat:** Continue the process until the gap becomes **1**.
    
5. **Final Pass:** The last pass (gap=1) is a standard Insertion Sort, but by then, the array is "almost sorted," so it runs very fast.
    

#### 3. Complexity Analysis

- **Time Complexity:** Depends heavily on the **Gap Sequence** used.
    
    - **Best Case:** **$O(n \log n)$**
        
    - **Average Case:** Depends on gap sequence (often around $O(n^{1.25})$ or $O(n^{1.5})$).
        
    - **Worst Case:** **$O(n^2)$** (using the default Shell sequence), but can be improved to **$O(n (\log n)^2)$** with better sequences (like Knuth's).
        
- **Space Complexity:** **$O(1)$** (In-place).
    

#### 4. Key Characteristics

- **Not Stable:** Unlike Insertion Sort, Shell Sort is **unstable** because it swaps elements across long distances, potentially changing the relative order of duplicate items.
    
- **Gap Sequences:**
    
    - _Shell's Original:_ $N/2, N/4, ..., 1$
        
    - _Knuth's:_ $1, 4, 13, 40...$ (Formula: $3k + 1$)

![[WhatsApp Image 2025-12-01 at 16.20.29_d256af7d.jpg]]






# Bucket sort

Bucket Sort is a **distribution-based** sorting algorithm (scatter-gather approach).

- It works by distributing elements into several "buckets" (bins) based on their value range.
    
- Each bucket is then sorted individually, and the buckets are concatenated to form the final sorted list.
    

#### 2. Algorithm Steps

1. **Create Buckets:** Create $k$ empty buckets (lists).
    
2. **Scatter:** Iterate through the input array and put each element into the appropriate bucket based on a specific formula (e.g., `floor(n * array[i])`).
    
3. **Sort Buckets:** Sort each non-empty bucket individually (usually using **Insertion Sort**).
    
4. **Gather:** Concatenate all the sorted buckets in order to get the final array.
    

#### 3. Complexity Analysis

- **Time Complexity:**
    
    - **Best/Average Case:** **$O(n + k)$**
        
        - _Condition:_ Input is **uniformly distributed** (elements are spread out evenly).
            
    - **Worst Case:** **$O(n^2)$**
        
        - _Condition:_ All elements fall into a **single bucket** (clustering), turning it into a normal Insertion Sort.
            
- **Space Complexity:** **$O(n + k)$** (Requires extra space for the buckets).
    

#### 4. Key Characteristics

- **Stable:** Yes (provided the algorithm used to sort the individual buckets is stable).
    
- **Constraint:** It is **NOT** a general-purpose sort. It assumes the input data is **uniformly distributed** over a specific range (often used for floating-point numbers between 0.0 and 1.0).

![[Pasted image 20251201162959.png]]




# Divide and conquer 

budhdhi queen

heere ki lalach me mar gayi 


Divide and Conquer is a top-down algorithm design paradigm that solves a complex problem by breaking it into smaller, identical sub-problems, solving them recursively, and combining the results.

#### 2. The Three Steps (DAC)

1. **Divide:** Break the original problem into smaller sub-problems (instances of the same problem).
    
2. **Conquer:** Solve the sub-problems recursively.
    
    - _Base Case:_ If the sub-problem is small enough, solve it directly (brute force).
        
3. **Combine (Merge):** Merge the solutions of the sub-problems to create the solution for the original problem.
    

#### 3. Complexity Analysis (Master Theorem)

The time complexity is usually expressed by the recurrence relation:

$$T(n) = aT(n/b) + f(n)$$

- $n$: Input size
    
- $a$: Number of sub-problems
    
- $b$: Factor by which the input size is divided
    
- $f(n)$: Cost to divide and combine
    

#### 4. Pros & Cons

- **Pros:** Efficient for large datasets (often reduces $O(n^2)$ to $O(n \log n)$); naturally parallelizable (multi-core processors).
    
- **Cons:** High memory usage due to **recursion stack**; overhead of repeated function calls.
    

#### 5. Classic Examples

| **Algorithm**         | **Divide Step**                 | **Combine Step**             | **Complexity**      |
| --------------------- | ------------------------------- | ---------------------------- | ------------------- |
| **Merge Sort**        | Split array in half.            | Merge two sorted halves.     | $O(n \log n)$       |
| **Quick Sort**        | Partition array around a pivot. | Trivial (Concat).            | $O(n \log n)$ (avg) |
| **Binary Search**     | Compare mid, go left or right.  | None (Return index).         | $O(\log n)$         |
| **Strassen’s Matrix** | Split matrices into quadrants.  | Matrix addition/subtraction. | $O(n^{2.81})$       |





# recurrence relation

![[WhatsApp Image 2025-12-01 at 16.38.49_b37d7813.jpg]]

![[WhatsApp Image 2025-12-01 at 16.39.23_6441cd7e.jpg]]




# Multiplying large integers 

![[WhatsApp Image 2025-12-01 at 17.13.42_0379853b.jpg]]




# Binary search 

Binary Search is an efficient algorithm that finds a target value within a **sorted array** by repeatedly dividing the search interval in half.

- **Paradigm:** Divide and Conquer.
    
- **Golden Rule:** The input array **MUST be sorted** (ascending or descending). If it is not sorted, Binary Search will not work.
    

#### 2. How it Works (Steps)

1. **Find Middle:** Calculate the middle element of the current range (`mid = (low + high) / 2`).
    
2. **Compare:**
    
    - If `target == middle`: Success! Return the index.
        
    - If `target < middle`: The value must be in the **left** half. Ignore the right half.
        
    - If `target > middle`: The value must be in the **right** half. Ignore the left half.
        
3. **Repeat:** Continue steps 1-2 until the target is found or the search range becomes empty.
    

#### 3. Complexity Analysis

- **Time Complexity:**
    
    - **Best Case:** **$O(1)$** (The target is the very first middle element found).
        
    - **Average & Worst Case:** **$O(\log n)$**.
        
        - _Meaning:_ If you double the input size, you only add **one** extra step to the search. It is extremely fast.
            
- **Space Complexity:** **$O(1)$** (Iterative approach) or $O(\log n)$ (Recursive approach due to stack).
    

#### 4. Pros & Cons

- **Pros:** Much faster than Linear Search ($O(n)$) for large datasets.
    
- **Cons:** The data must be sorted first (sorting takes time). Not efficient for data structures that don't support random access (like Linked Lists).
![[Pasted image 20251201174126.png]]





# Quick sort 


![[Pasted image 20251201175709.png]]

| **Case**         | **Time Complexity** | **Scenario**                                                    |
| ---------------- | ------------------- | --------------------------------------------------------------- |
| **Best Case**    | **$O(n \log n)$**   | Partition always splits array in **middle**.                    |
| **Average Case** | **$O(n \log n)$**   | Partition splits array randomly (balanced).                     |
| **Worst Case**   | **$O(n^2)$**        | Partition splits array into **1 element vs rest** (unbalanced). |
|                  |                     |                                                                 |



# Matrix multiplication  divide and conquer

![[Pasted image 20251201180304.png]]






	
# Principle of optimality

![[Pasted image 20251130111220.png]]



# Binomial cooficient using DP

![[Pasted image 20251201181025.png]]


# Coin change problem using dp
![[WhatsApp Image 2025-12-01 at 18.12.47_a723134a.jpg]]




# Assembly line scheduling

![[WhatsApp Image 2025-12-01 at 18.14.27_89a9e50d.jpg]]







# Knapsack using DP
![[WhatsApp Image 2025-12-01 at 18.33.28_7a19ebe7.jpg]]





# floyd's algorithm

![[WhatsApp Image 2025-12-01 at 18.42.45_0beb546f.jpg]]






# MAtrix chain multiplication 
![[WhatsApp Image 2025-12-01 at 18.53.18_6084cd9c.jpg]]





# Longest common subsequence

![[Pasted image 20251201185431.png]]

![[WhatsApp Image 2025-12-01 at 18.56.10_299a460a.jpg]]


# Activity selection greedy 
![[WhatsApp Image 2025-12-01 at 19.07.51_cef8327a.jpg]]




# Knapsack using greedy 

using profit/weight ratio 
![[Pasted image 20251130224312.png]]
there are two other ways 
1. by  sorting profit in asceding order
2. by sorting weight in desceding order






# Optimal substructure

This property means that the problem can be broken down into smaller pieces, and the optimal solution to the _big_ problem contains within it the optimal solutions to the _small_ sub-problems.

- If we solve the small parts optimally and combine them, we get the optimal answer for the whole problem.
    

> **Example:** If you are finding the shortest path from City A to City C, and the path goes through City B, then the path from A to B must _also_ be the shortest path between A and B. If there was a shorter way to get to B, your total path to C would have been shorter too.







# Greedy works on fractional but fails in 0/1 knapsack
### True 

A greedy strategy works perfectly for the **Fractional Knapsack** problem, but it often fails to find the optimal solution for the **0/1 Knapsack** problem.

### Explanation

- **Fractional Knapsack (Greedy Works):** Since you can break items into smaller pieces, you can always just pick the item with the highest "value per unit of weight" (highest density) and keep filling the bag. If the bag gets full, you just cut off a fraction of the last item to fill the remaining space perfectly.
    
- **0/1 Knapsack (Greedy Fails):** You cannot break items; you must either take the whole item or leave it (0 or 1). A greedy strategy might pick a high-value item that is "awkwardly shaped" (in terms of weight), leaving a small amount of empty space in the knapsack that no other item can fit into. This wasted space leads to a suboptimal total value.
    

---

### Proof with Example

Let's look at a concrete example to prove this.

**Scenario:**

- **Knapsack Capacity:** 50 kg
    
- **Items available:**
    

|**Item**|**Value ($)**|**Weight (kg)**|**Value/Weight Ratio**|
|---|---|---|---|
|**A**|$60|10|$6/kg (Highest)|
|**B**|$100|20|$5/kg (Middle)|
|**C**|$120|30|$4/kg (Lowest)|

#### 1. Applying Greedy Strategy (Best Ratio First)

The greedy approach says: "Always take the item with the highest Value/Weight ratio first."

- **Step 1:** Pick Item A ($6/kg).
    
    - Current Weight: 10 kg | Current Value: $60
        
    - Space Left: 40 kg
        
- **Step 2:** Pick Item B ($5/kg).
    
    - Current Weight: 10 + 20 = 30 kg | Current Value: 60 + 100 = $160
        
    - Space Left: 20 kg
        
- **Step 3:** Try to pick Item C ($4/kg).
    
    - Item C weighs 30 kg, but we only have 20 kg of space left.
        

Outcome for Fractional Knapsack:

We take $\frac{20}{30}$ (two-thirds) of Item C.

- Value added: $\frac{2}{3} \times 120 = \$80$.
    
- **Total Value:** $160 + 80 = \mathbf{\$240}$. (This is the maximum possible value).
    

Outcome for 0/1 Knapsack:

We cannot break Item C. It doesn't fit. We stop.

- **Total Greedy Value:** **$160**.
    

#### 2. Applying Optimal Strategy (Non-Greedy) for 0/1

If we ignore the greedy "ratio" and just look for the best combination that fits:

- We pick **Item B** (20 kg) and **Item C** (30 kg).
    
- Total Weight: $20 + 30 = 50$ kg (Fits perfectly).
    
- Total Value: $100 + 120 = \mathbf{\$220}$.
    

### Conclusion

- **Greedy Result:** $160
    
- **Optimal Result:** $220
    

Because $160 < 220$, the greedy strategy failed to find the best solution for the 0/1 Knapsack problem. To solve 0/1 Knapsack optimally, you must use **Dynamic Programming**.








# prims vs krushkal

| **Feature**         | **Prim's Algorithm**                                               | **Kruskal's Algorithm**                                                      |
| ------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| **Primary Focus**   | **Vertex-based:** It grows a tree from a starting vertex.          | **Edge-based:** It sorts edges and connects components.                      |
| **Logic**           | Adds the nearest **vertex** to the current tree.                   | Adds the lightest **edge** that doesn't form a cycle.                        |
| **Connectivity**    | The tree is always connected (it grows as one piece).              | The structure can be disconnected (a forest) during execution until the end. |
| **Data Structures** | Priority Queue (Min-Heap) & Array (visited/distance).              | Union-Find (Disjoint Set) & Sorting Algorithm.                               |
| **Time Complexity** | $O(E \log V)$ (Binary Heap) or $O(E + V \log V)$ (Fibonacci Heap). | $O(E \log E)$ or $O(E \log V)$ (dominated by sorting).                       |
| **Best Used For**   | **Dense Graphs:** Graphs with many edges ($E \approx V^2$).        | **Sparse Graphs:** Graphs with fewer edges ($E \approx V$).                  |
|                     |                                                                    |                                                                              |



![[Pasted image 20251201192837.png]]


![[Pasted image 20251201192857.png]]




# Dijkstra algo
![[Pasted image 20251201193848.png]]


# Job sequencing problem
![[Pasted image 20251201194211.png]]




# huffman code
![[WhatsApp Image 2025-12-01 at 19.45.57_35338109.jpg]]


# Greedy DP DAC

| **Feature**      | **Greedy**             | **Divide & Conquer**              | **Dynamic Programming**                   |
| ---------------- | ---------------------- | --------------------------------- | ----------------------------------------- |
| **Approach**     | Best immediate choice. | Break into independent parts.     | Break into overlapping parts & cache.     |
| **Optimality**   | Not guaranteed.        | Guaranteed (if logic is correct). | Guaranteed (Global Optimum).              |
| **Backtracking** | No.                    | No (it just recurses).            | No (but it effectively checks all paths). |
| **Speed**        | Fastest.               | Moderate (often $O(n \log n)$).   | Slowest (often $O(n^2)$ or $O(n^3)$).     |
| **Memory**       | Low.                   | High (Recursion stack).           | High (Tables/Maps).                       |
### 1. Greedy Algorithm

**"Living in the moment."**

A greedy algorithm builds a solution piece by piece, always choosing the next piece that offers the most immediate benefit.

- **Local Optimality:** At every step, it makes the choice that looks best _right now_ (local maximum) without worrying about the future.
    
- **Irrevocability:** Once a decision is made, it is never changed. It doesn't backtrack or reconsider previous choices.
    
- **Feasibility:** It ensures that every choice made satisfies the problem constraints.
    
- **Speed:** Generally very fast and efficient because it only makes one pass through the data.
    
- **No Guarantee of Global Optimum:** It often finds a "good" solution, but not always the "best" solution (except for specific problems like Fractional Knapsack or Prim's MST).
    

### 2. Divide and Conquer

**"Divide and Rule."**

This strategy solves a problem by breaking it down into smaller, independent sub-problems that are exactly the same type as the original problem.

- **Recursive Structure:** It relies heavily on recursion.
    
- **Three Phases:**
    
    1. **Divide:** Break the problem into non-overlapping sub-problems.
        
    2. **Conquer:** Solve the sub-problems recursively (or directly if they are small).
        
    3. **Combine:** Merge the solutions of the sub-problems to get the final answer.
        
- **Independence:** The sub-problems must be **independent** (solving one doesn't affect the other).
    
- **Top-Down Approach:** It starts with the big problem and breaks it down.
    
- **Examples:** Merge Sort, Quick Sort, Binary Search.
    

### 3. Dynamic Programming (DP)

**"Remembering the past."**

DP is an optimization of recursion. It is used when a problem breaks down into _overlapping_ sub-problems. It solves each sub-problem once and saves the result to avoid re-calculating it.

- **Overlapping Sub-problems:** The sub-problems share common parts (unlike Divide and Conquer where they are separate).
    
- **Optimal Substructure:** The optimal solution to the big problem can be constructed from the optimal solutions of its sub-problems.
    
- **Memoization/Tabulation:** It uses a table (array or matrix) to store results of solved sub-problems.
    
- **Exhaustive:** It explores all possible options (smartly) to guarantee the **Global Optimum**.
    
- **Bottom-Up or Top-Down:** Can be implemented iteratively (building from base cases up) or recursively (with caching).
    
- **Examples:** 0/1 Knapsack, Floyd-Warshall, Matrix Chain Multiplication.







![[Pasted image 20251128135136.png]]





# DFS
![[Pasted image 20251128135358.png]]





# DFS vs BFS
![[Pasted image 20251128135615.png]]





# Articulation point
![[Pasted image 20251128135929.png]]


# Topological sort

**Topological Sorting** is a linear ordering of vertices (nodes) in a directed graph such that for every directed edge from vertex $u$ to vertex $v$ ($u \rightarrow v$), vertex $u$ comes before vertex $v$ in the ordering.

Think of it as a **"To-Do List"** where some tasks must be finished before others can start. Topological sorting gives you a valid sequence to perform all the tasks without breaking any dependency rules.

---

### **1. The Golden Rule: DAG Only**

Topological sorting is **only** possible if the graph satisfies two conditions:

1. **Directed:** The edges must have a direction (one-way street).
    
2. **Acyclic:** The graph must **not** contain any cycles. If you start at Node A and follow the arrows, you should never be able to return to Node A.
    
    - _Why?_ If you have a cycle like $A \rightarrow B \rightarrow A$, then $A$ must come before $B$, but $B$ must also come before $A$. This is a contradiction (like the "Chicken or Egg" problem), so no linear order is possible.
        

Therefore, we say Topological Sorting applies only to a **DAG (Directed Acyclic Graph)**.

---

### **2. Real-World Analogy: Getting Dressed**

Imagine the vertices are items of clothing and the edges are dependencies ("must put on X before Y").

- **Dependencies:**
    
    - Socks $\rightarrow$ Shoes (You must wear socks before shoes)
        
    - Underwear $\rightarrow$ Pants
        
    - Pants $\rightarrow$ Belt
        
    - Shirt $\rightarrow$ Tie
        
- A Valid Topological Sort:
    
    Underwear, Socks, Pants, Shirt, Belt, Tie, Shoes
    
- Another Valid Sort:
    
    Socks, Underwear, Shirt, Pants, Tie, Belt, Shoes
    
    (Note: As seen above, a graph can have multiple valid topological sorts.)


Topological sort using DFS
![[Pasted image 20251128203308.png]]







# 1. Backtracking

What is it?

Backtracking is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time. It removes those solutions that fail to satisfy the constraints of the problem at any point of time (this is called "pruning").

- **How it works:** It uses a **Depth First Search (DFS)** approach. It dives deep into a possible path. If it hits a dead end (a point where the solution cannot be valid), it "backtracks" (goes back to the previous step) and tries a different path
    
- **Key Concept:** It explores the "State Space Tree."
    
- **Common Exam Examples:**
    
    - **N-Queens Problem:** Placing N queens on a chessboard so no two queens attack each other
        
    - **Graph Coloring:** Coloring a graph such that no two adjacent vertices have the same color.
        

# 2. Branch and Bound (B&B)

What is it?

Branch and Bound is an algorithm design paradigm generally used for solving combinatorial optimization problems. Unlike backtracking, which just looks for any valid solution, Branch and Bound looks for the best (optimal) solution (minimum or maximum)

- **How it works:** It typically uses a **Breadth First Search (BFS)** or **Best First Search** approach.
    
- **Branching:** It divides the problem into smaller sub-problems (branches).
    
- **Bounding:** It calculates a bound (a cost estimate) for each branch. If a branch's estimated cost is worse than the best solution found so far, that branch is discarded (pruned) completely without exploring it further.
    
- **Key Concept:** It uses a "Bounding Function" to estimate the cost
    
- **Common Exam Examples:**
    
    - **Traveling Salesman Problem (TSP):** Finding the shortest possible route that visits each city exactly once.
        
    - **0/1 Knapsack Problem (Optimization):** Finding the maximum value items to fit in a bag.
        

---

### 3. Key Differences (Frequently Asked)

This comparison is explicitly asked for in questions like "Differentiate branch and bound and back tracking algorithm"5.

| **Feature**            | **Backtracking**                                                                              | **Branch and Bound**                                                                                   |
| ---------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Goal**               | Finds **all** feasible solutions or **one** feasible solution. (Constraint Satisfaction)      | Finds the **optimal** solution (Optimization Problem).                                                 |
| **Traversal Strategy** | Uses **Depth First Search (DFS)**. It goes deep into one path before turning back.            | Typically uses **Breadth First Search (BFS)** or Least Cost Search. It explores level-by-level.        |
| **Optimality**         | Does not guarantee the "best" solution, just a "valid" one.                                   | Guarantees finding the optimal (minimum or maximum) solution.                                          |
| **Pruning Logic**      | Prunes the tree when a constraint is violated.                                                | Prunes the tree when the estimated cost (bound) indicates the path cannot lead to an optimal solution. |
| **Efficiency**         | generally less efficient for optimization problems as it may explore non-optimal valid paths. | More efficient for optimization as it discards large chunks of bad solutions early using bounds.       |
| **Applications**       | N-Queens, Sudoku, Maze problems.                                                              | Traveling Salesman Problem, Job Assignment, Knapsack.                                                  |


![[Pasted image 20251127135215.png]]



# Travelling salesman problem

![[WhatsApp Image 2025-12-01 at 22.03.35_03a5f77a.jpg]]


# Minimax principle

![[Pasted image 20251201222641.png]]



# STRING MATCHING

String matching is the process of finding one or more occurrences of a specific **Pattern ($P$)** within a larger **Text ($T$)**.

- **The Goal:** To find the "valid shift" (starting index) where the pattern appears in the text.
    
- **Example:**
    
    - **Text ($T$):** `GUJARAT_UNIVERSITY`
        
    - **Pattern ($P$):** `UNIVER`
        
    - **Result:** The pattern is found starting at index 8.


# NAIVE STRING MATCHING ALGO
![[Pasted image 20251127191102.png]]
![[Pasted image 20251127192625.png]]


# RABIN KARP ALGO 
![[Pasted image 20251127192022.png]]
![[Pasted image 20251127192457.png]]



# KMP algo
![[Pasted image 20251128135013.png]]
![[Pasted image 20251128134939.png]]





# hard hard shit

| **Class**       | **Simple Meaning**            | **Key Feature**                     | **Example**                 |
| --------------- | ----------------------------- | ----------------------------------- | --------------------------- |
| **P**           | Easy to solve.                | Solvable in Polynomial Time.        | Sorting, Shortest Path.     |
| **NP**          | Easy to check.                | Verifiable in Polynomial Time.      | Sudoku, Factoring numbers.  |
| **NP-Complete** | The Hardest of the Checkable. | If you solve one, you solve all NP. | Hamiltonian Cycle, SAT.     |
| **NP-Hard**     | Extremely Hard.               | At least as hard as NP.             | TSP (Optimization).         |
| **P-SPACE**     | Memory is the limit.          | Solvable with Polynomial Memory.    | Generalized Chess/Checkers. |

# Polynomial reduction

#### 1. Definition

Polynomial reduction is a technique to solve a problem by **translating** it into another problem that we already know how to solve. If the translation happens fast (in Polynomial Time), it proves a relationship between the difficulty of the two problems.

#### 2. Notation

$$A \le_p B$$

- **Reads as:** "Problem A reduces to Problem B."
    
- **Means:** Problem A is **no harder** than Problem B. (Problem B is at least as hard as A).
    

#### 3. The Mechanism (How it works)

To prove $A \le_p B$, you must construct an algorithm that does the following:

1. **Input:** Takes an input $x$ from Problem A.
    
2. **Transform:** Converts $x$ into a new input $y$ suitable for Problem B using a function $f$.
    
    - _Constraint:_ This conversion must run in **Polynomial Time**.
        
3. **Solve:** Feeds $y$ into Problem B.
    
4. **Output:** The answer (Yes/No) for B must be the **exact same answer** for A.
    


#### 4. The Two Main Implications

We use reduction for two opposite goals:

- **Goal 1: To prove a problem is EASY.**
    
    - If $A \le_p B$ and we know **B is Easy (P)** $\rightarrow$ Then **A is also Easy (P)**.
        
    - _Logic:_ Since the translation is fast and solving B is fast, A is fast.
        
- **Goal 2: To prove a problem is HARD.** (Used for NP-Completeness)
    
    - If $A \le_p B$ and we know **A is Hard (NP-Hard)** $\rightarrow$ Then **B is also Hard (NP-Hard)**.
        
    - _Logic:_ If we could solve B easily, we could solve the hard problem A easily. Since A is hard, B must be hard too.
        

#### 5. Key Example

**Hamiltonian Cycle $\le_p$ Traveling Salesman Problem (TSP)**

- We can turn a "path finding" problem (Hamiltonian) into a "cost minimization" problem (TSP).
    
- Since Hamiltonian Cycle is known to be NP-Complete, this reduction proves that TSP is also NP-Hard.
    


Let's demonstrate a reduction.

- **Problem A (Hamiltonian Cycle):** Given a graph, is there a simple cycle that visits every vertex exactly once? (We don't care about distance, just connection).
    
- **Problem B (Traveling Salesman - Decision Version):** Given a weighted graph and a limit $K$, is there a tour with total cost $\le K$?
    

**The Goal:** Prove Hamiltonian Cycle ($A$) reduces to TSP ($B$).

The Reduction Strategy:

Imagine I give you a graph for the Hamiltonian problem. You need to feed it into a "TSP Solver machine." How do you trick the TSP machine into solving your Hamiltonian problem?

1. **Transformation:** Take the graph from Problem A.
    
    - Assign a weight of **1** to every edge that exists in the graph.
        
    - (Optional: Add "invisible" edges with infinite weight between nodes that weren't connected, to make the graph complete).
        
2. **Set the TSP Limit:** Set $K$ equal to the number of vertices ($V$).
    
3. **The Logic:**
    
    - If the TSP solver finds a path with cost $V$, it means it found a path using only the edges with weight 1.
        
    - This implies a valid tour exists in the original graph.
        
4. **Conclusion:** If the TSP machine says "YES (Cost is $V$)", then the answer to the Hamiltonian Cycle is "YES".
    

We successfully turned a "connectivity" problem into a "cost" problem.
---

### 💡 Golden Rule to Remember

If **$A \le_p B$**:

- If **B** is easy, **A** is easy.
    
- If **A** is hard, **B** is hard.






# Randomization and approximation 

1. **Approximation Algorithms:** "I accept an answer that is slightly imperfect, as long as it is fast and guaranteed to be close."
    
2. **Randomized Algorithms:** "I will use luck (random numbers) to speed up the process or simplify the logic."
    

Here is a detailed breakdown of both.

---

### 1. Approximation Algorithms

When a problem is NP-Hard, finding the **Optimal Solution (Best)** is impossible in a reasonable time. Approximation algorithms settle for a **Near-Optimal Solution**.

**The Key Difference:** unlike "heuristics" (guesses), an Approximation Algorithm gives you a **mathematical guarantee** on how "bad" the answer might be.

#### Technical Metrics: The Approximation Ratio ($\rho$)

We measure these algorithms by how far off they are from the perfect answer.

Let:

- $OPT$: Cost of the Optimal (Perfect) solution.
    
- $APPROX$: Cost of our algorithm's solution.
    

For a minimization problem (like finding the shortest route), the Approximation Ratio $\rho(n)$ is:

$$APPROX \le \rho(n) \times OPT$$

- **Example:** A **2-approximation** algorithm guarantees the result will never be more than **2 times** the cost of the best possible answer. If the perfect route is 100km, our algorithm guarantees a route $\le$ 200km.
    

#### Example: Vertex Cover Problem (2-Approximation)

**Problem:** Given a graph, pick the minimum number of vertices so that every edge touches at least one picked vertex. (This is NP-Hard).

**The Approximation Strategy:**

1. Pick an arbitrary edge $(u, v)$.
    
2. Add **both** $u$ and $v$ to your set.
    
3. Remove all edges attached to $u$ or $v$.
    
4. Repeat until no edges remain.
    

Why is this "Approximation"?

In the perfect scenario, maybe only $u$ was needed to cover the edge. But we took both $u$ and $v$.

Guarantee: We might pick twice as many nodes as necessary, but never more. This is a 2-Approximation.

---

### 2. Randomized Algorithms

These algorithms use a source of **random numbers** (like flipping a coin) to make decisions during execution.

Why use randomness?

Sometimes, a deterministic (non-random) algorithm gets stuck on "tricky" inputs (Worst Case). By adding randomness, we "shuffle" the problem so that the worst-case scenario becomes incredibly unlikely.

#### The Two Main Types

This is the most critical technical distinction in this topic.

|**Feature**|**Las Vegas Algorithms**|**Monte Carlo Algorithms**|
|---|---|---|
|**Output**|**Always Correct.**|**Possibly Incorrect** (with low probability).|
|**Running Time**|**Random** (Might take long).|**Fixed/Deterministic** (Fast).|
|**Analogy**|Looking for keys in a dark room. You keep searching until you find them. **You succeed eventually, but time varies.**|Polling 1,000 people to predict an election. **You finish in 1 day, but there is a 1% margin of error.**|
|**Example**|Randomized QuickSort.|Miller-Rabin Primality Test, Karger’s Min-Cut.|

