### Algorithm:

#### `Algorithm v/s Program`

| Algorithm                                                                                                | Program                                                                      |
| -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| step-by-step procedure or set of rules designed to solve a specific problem or perform a particular task | It is a specific implementation of an algorithm using a programming language |
| Design                                                                                                   | Implementation                                                               |
| Domain Knowledge                                                                                         | Programmer                                                                   |
| Any Language                                                                                             | Programming Lnaguage                                                         |
| Hardware and OS                                                                                          | Hardware and OS                                                              |
| Analyze                                                                                                  | Terting                                                                      |

#### `Prior Analysis v\s Posterior Testing`

|     Prior Analysis      |  Posterior Testing   |
| :---------------------: | :------------------: |
|        Algorithm        |       Program        |
| Independent of Language |  Language dependent  |
|  Hardware Independent   |  Hardware dependent  |
| Time and Space Function | Watch time and Bytes |

#### `Characteristics of Algorithm`:

1. **Input**:
   - Data or information provided to the algorithm that it operates on to produce the desired output
   - Take various forms depending on the nature of the problem being solved.
2. **Output**:
   - Represents the desired outcome or solution to a problem.
   - Without output, an algorithm would lack purpose and utility in problem-solving tasks.
3. **Definiteness**:
   - Requirement of each step of the algorithm must be precisely and unambiguously defined
   - It is a crucial characteristic of algorithms because it ensures clarity, consistency, correctness, interoperability (exchange information seamlessly) , and ease of debugging and maintenance
4. **Finiteness**:
   - Refers to the property that an algorithm must terminate after a finite number of steps (OR) there should be a clear endpoint to the execution of the algorithm, and it should not run indefinitely.
   - It is a critical property of algorithms because it ensures efficient resource utilization, predictable behavior, a positive user experience, real-world applicability, and ease of debugging.
5. **Effectiveness**:
   - Refers to the ability of an algorithm to achieve its intended purpose efficiently and accurately.
   - It in algorithms encompasses correctness, efficiency, scalability, robustness, simplicity, and adaptability.

`With the help of an example`: An algorithm, like a recipe, needs clear instructions (**definiteness**) to process information (**input**) and achieve a specific goal (**output**). Just like a recipe shouldn't take forever to bake (**finiteness**), an algorithm should run in a reasonable amount of time. The best recipes, like the best algorithms, are also efficient (**effectiveness**), using the least amount of ingredients and steps to get the job done.

- `Analyzation of Algorithm`:
  - **Time**
    - In form of time function
    - Every statement in an algorithm takes 1 unit of time
  - **Space**
    - Memory consumed
    - Total number of variables

```c
Algorithm swap()
{
    temp = a;
    a = b;
    b = temp;
}

## Time Analysis:

t = f(n)
  = constatnt
  = O(1)

s = s(n) = s(3)
  = total variables
  = O(1)

```

![alt text](image-12.png)

![alt text](image-13.png)

![alt text](image-15.png)

![alt text](image-16.png)

### DisJoint Sets:

- In a non-connected, non-directed graph with two components, each component can be represented as a set. If the intersection of these two sets is an empty set, they are said to be disjoint.
- Useful in Kruskal's algorithm for detecting cycles in a graph.
- No elements in common.
- Used where there is a need to partition a set of elements into disjoint subsets and perform operations like merging two sets or finding which set an element belongs t0

#### Operations on Disjoint Sets:

- `MakeSet(x)`: Creates a new set containing element x.
- `Union(x, y)`: Merges the sets containing elements x and y into a single set.
- `Find(x)`: Returns the representative (also known as the "root" or "leader") of the set containing element x

![alt text](image-17.png)

### `Recurrence Relation`:

- A recurrence relation in algorithms is a mathematical expression that defines the running time or resource usage of an algorithm in terms of smaller subproblems of the same nature.
- Recurrence relations are commonly used to analyze the time complexity of algorithms, particularly in divide-and-conquer algorithms, dynamic programming, and recursive algorithms.
- **A recurrence relation is an equation or inequality that describes a function in terms of its value on smaller inputs**

- `Implementation & Solving Techniques of Recurrence Relation`:

  - **Substitution Method**: In this approach, we make an educated guess about the form of the solution and then prove its correctness by induction or other means.

  - **Recursion Tree Method**: This method involves drawing a tree to represent the recursive calls made by the algorithm and then analyzing the total work done at each level of the tree.

  - **Master Theorem**: The Master Theorem provides a concise way to solve recurrence relations of a specific form, particularly those that arise in divide-and-conquer algorithms. It gives solutions in terms of asymptotic bounds.

![alt text](image-18.png)

![alt text](image-19.png)

![alt text](image-20.png)

![alt text](image-22.png)

### `Masters Theorem`:

- The Master Theorem is a tool used in the analysis of algorithms, particularly in the context of recursive algorithms.
- Determine the time complexity of divide-and-conquer algorithms by providing a simple formula to calculate their time complexity.

![alt text](image-21.png)

### Binary Search:

- Algorithm used for finding a target value within a sorted array or list
- Repeatedly divide the search interval in half until the target value is found or determined to be not present in the array.
- Here we need two index pointers: **low** and **high**
- No. of comparison are less than linear search.
- If the low cross high then the index is not found.
- Time Complexity:
  - Minimum = O(1)
  - Maximum = O(log n)
- `Need for Binary Search` because the inefficiency of linear search when dealing with large datasets.
- We `Use Binary Search` because of its speed and efficiency, It drastically reduces the number of comparisons required to find a target value compared to linear search. Hence, ideal choice where quick search operations are necessary, such as searching in databases, sorting algorithms like quicksort and mergesort, and more.

`Binary Search Iterative Method`

```c
int Bin search(A, n, key)
{
  l = 1;
  h = n;
  while(l <= h)
  {
    mid = (l + h) / 2;

    if(key == A[mid])
    {
      return mid;
    }
    if( key <= A[mid])
    {
      h = mid - 1;
    }
    else
      h = mid + 1;
  }
  return 0;
}
```

![alt text](image-23.png)

`Binary Search Recursive Method`

```c
Algorithm RBinSearch (l, h, key)
{

  if(l == h)
  {
    if(A[l] == key)
      return l;
    else
      return 0;
  }
  else
  {
      mid = (l + h)/2;
      if(key == A[mid])
        return mid;
      if(key < A[mid])
        return RBinSearch (l, mid-1, key);
      else
        return RBinSearch (mid+1, h, key);
  }
}
```

### `Binary Tree`:

- It is a fundamental hierarchical data structure where each node can have at most two children: a left child and a right child. The topmost node in the tree is called the root.
- We should a have nodes from left-right

```md
        1 ---> Root (2 & 3--> its children)
       / \
      2   3
     / \ / \
    4  5 6  7
```

![alt text](image-26.png)

- **Need and Usage of Binary Trees**:

  - _Efficient Searching and Sorting_: Enables efficient searching (lookup in a dictionary) and sorting due to their inherent ordering.
  - _Dynamic Data Management_: They can grow or shrink as needed, making them suitable for datasets that change over time.
  - _Fast Access_: By following branches based on comparisons, you can quickly locate or insert data.

- **Types**:
  - `Full Binary Tree`:
    - Every node (except possibly leaf nodes) has two children.
    - All leaf nodes are at the same level.
    - Useful for theoretical considerations or when compactness is a priority
    - Every full binary tree is a complete binary tree
    - ![alt text](image-24.png)
  - `Complete Binary Tree`:
    - A binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible.
    - If we construct a complete binary tree from an array without any gaps or missing elements, it's still called a complete binary tree.
    - A complete binary tree is a full binary tree upto a height `h-1`
    - Efficient heap implementations and certain types of balanced binary search trees where level-order traversal is important.
    - Height of the complete binary tree is minimum only i.e. `log n`
    - ![alt text](image-25.png)

### `Heap`

- A heap is a specialized tree-based data structure designed for efficient retrieval of the minimum or maximum element.
- Retrieving the minimum or maximum element takes constant time `O(1)`
- `Maximum Heap`:

  - Every node has a value greater than or equal to the values of its children.
  - Maximum value is always at the root of the tree.

    - `When to Use`

      1. Scheduling high-priority jobs in a system.
      2. Implementing the Huffman coding algorithm for data compression.

      ```md
             50
            /  \
          30    20

      / \ / \
       15 10 8 16

      Index: 0 1 2 3 4 5 6 7
      Array: [50, 30, 20, 15, 10, 8, 16]
      ```

- `Minimum Heap`:

  - Every node is having value smaller/equal to all its descend nodes

    - `When to Use`

    1. Finding the shortest path in Dijkstra's algorithm for graph traversal.
    2. Implementing the Prim's algorithm for finding the minimum spanning tree.

    ```md
           8
          /  \
        10    16
        / \   / \

    15 30 20 50

    Index: 0 1 2 3 4 5 6 7
    Array: [8, 10, 16, 15, 30, 20, 50]
    ```

#### `Insertion Element in Heap`:

- Add new element as a leaf at the below most position
- Then adjust its position while comparing with the ancestors
- Always the direction of adjustment is upward
- _Time Complexity_: **O(1) to O(log n)**

#### `Deletion element from Heap`:

- **Time Complexity**: log n
- **Delete Root**: The element at the root (the maximum in a max-heap, minimum in a min-heap) is removed
- **Move Last Element to Root**: The last element in the heap (which might not be the largest or smallest) is placed in the root position.
- **Heapify Down**
  - If either child is greater/smaller than the new root, swap the new root with the larger/smaller child.
  - Repeat the comparison and swapping process until a position is found where the parent is greater/less than or equal to both children. This ensures the largest/smallest element eventually reaches the root.
- **Result**:
  - Max-Heap: After deletion and heapify down, the new root element will be the next largest element in the heap.
  - Min-Heap: After deletion and heapify down, the new root element will be the next smallest element in the heap
- **Idea**: Delete the element & fill it on an empty array-sorted array

![alt text](image-27.png)

#### `Heap Sort`:

- Heap-sort is an efficient sorting algorithm that utilizes the properties of a heap data structure to sort an array in `O(n log n)` time complexity
- `Process`
  1. **Create a Maximum Heap**: Convert given array to maximum heap
  2. **Extract Maximum**:
     - Remove the element at the root (the largest in a max-heap).
     - Place it at the end of the unsorted array
  3. **Reduce Heap Size**:
     - Reduce the size by 1
     - Rest of the elements in the heap (size reduced by 1) might violate the heap property because the new root might be smaller than its children.
  4. **Repeat**:
     - Repeat steps 2-4 i.e,
     - Continue extracting the maximum element & place it at the end of the sorted portion & size reduced by 1
  5. **Get Sorted Array**: The entire array becomes sorted. The largest element is at the end, the second largest is second to last, and so on.

#### `Heapify`:

- Process of creating heap froman array
- **Main idea** is to start from the last non-leaf node (i.e., the parent of the last element) and repeatedly heapify each subtree to build the heap from the bottom up.
- Time Complexity: `O(log n)`

#### `Priority Queue`:

- A priority queue (**Prioritizing Elements for Efficient Processing**) is a data structure where elements have priorities and they can be inserted or deleted accordingly
- Smaller the number higher the priority [MIN HEAP]/ Larger the number higher the priority [MAX HEAP]
- Heap is the best DS for implementing priority queue
- The time complexity of insertion and deletion in a heap is `O(log n)`
- `Need`:
  - **Efficient Handling of Urgent Tasks**: Allows you to focus on the most critical items first
  - **Optimization Algorithms**: Various optimization algorithms (Dijkstra's algorithm)
- _Standard queues_ adhere to FIFO, while _Priority queues_ prioritize based on assigned values.

![alt text](image-29.png)

![alt text](image-28.png)

#### `Pros & Cons of Merge Sort`:

- Large size list
- Linked List
  - We can merge two linked list without creating 3rd linked list
- External Sorting:
  - We can bring pieces or chunck of files from harddisk & merge them
- Stable:

  - If there is a duplicate element in the array/ then the merge will preserve the order

  ```md
  Element of Array: 8, 6, 4, 3, 8, 5, 9 [8 --> (for R); 8 --> (for A)]

        ||  After Merging  ||

  Element of Array: 3, 4, 5, 6, 8(R), 8(A), 9
  ```

![alt text](image-31.png)

### `Greedy Method`:

- A greedy method is a particular approach to solving optimization problems (problems which require either minimum/ maximum result) by making a series of choices that appear best at each stage.
- Makes a series of seemingly best choices at each step to solve optimization problems
- May not find the absolute best solution but offers a fast and efficient approach
- Problems should be solved in stages, i.e, in each stages we consider one problem and if the input is feasible, we include it in soln, hence by including all feasible soln, we got optimal solution.
  ```c
   Algorithm Greedy(a, n)
   {
     for( int i = 1; i<= n; i++)
     {
       x = Select (a);
       if (Feasible(x))
       {
         Solutoin =  Solution + x;
       }
     }
   }
  ```

#### `Knapsack Problem`(Greedy-Method):

- It is an optiomization problem, we try to pick objects froma list to maximize the total profit while keeping the weight under a certain limit
- It is a container loading problem
- There are two types of Knapsack Problem:
  - Knapsack and 0-1 Knapsack
  - In **Knapsack**, we can take fraction of an object, but in **0-1 Knapsack** Problem, we can only take the whole object or none of it.
- ![alt text](image-32.png)
  - Way to solve it:
    1. Calculate the profit per weight ratio for each object
    2. Sort the objects by their profit per weight ratio in descending order
    3. Now, start adding object a/c to the highest profit per weight ratio.
    4. If adding an object exceed the weight capacity, skip the object
    5. Continue, till the bag is full or there are no more objects to add

#### `Job Sequencing with Deadlines`(Greedy-Method):

- The goal is to sequence the jobs in a way that maximizes the total profit while meeting all the deadlines
  ![alt text](image-33.png)

#### `Optimal Merge Sort`(Greedy-Method):

- Here, in these kind of problems we use the concept of merging sorted list and combining them into one sorted list
- Time Complexity is O(m+n)
- **Goal** is to find the way to merge multiple sorted lists that minimizes the total merging cost
  ![alt text](image-34.png)
  ![alt text](image-35.png)

#### `Huffman Coding`(Greedy-Method):

- Huffman coding is a compression tecnique that is used to reduce the size of a file or data before transmission over a network
- Here, the frequently used alphabets are assigned shorter codes and less frequent alphabets are assigned longer codes. This way, the overall size of the encoded message is reduced
  ![alt text](image-37.png)

#### `Minimum-Cost Spanning Tree`:

- **Spanning tree** is a subgroup of a graph having all vertices but only (n-1) edges
- They do not have cycles
  ![alt text](image-38.png)
- For non-connected graphs, we cannot calculate the spanning tree
- Ways to find minimum-cost spanning tree:
  - Prim's Algorithm
  - Krushkal's Algorithm

#### `Prim's Algorithm`:

![alt text](image-39.png)

- Time Complexity = **O(V^2)**

#### `Krushkal's Algorithm`:

![alt text](image-40.png)

- Time Complexity can be improved to **O(E log V)** using a min-heap data structure.

#### `Dijkstra Algorithm`:

- Dijkstra's algorithm, is a powerful tool for finding the shortest paths between a starting point and all other reachable nodes in a weighted graph.
- For single source path problem/minimization problem/optimization problem(Greedy Method).
- Works for non-negative edge weights (travel times cannot be negative).
- It guarantees finding the shortest path for all reachable nodes in the graph.
  ![alt text](image-41.png)

### `Dyanmic Programming`:

- **Dynamic programming** is a powerful technique that efficiently solves complex problems by breaking them into overlapping subproblems, and storing solutions for reuse to avoid redundant computations.
- It is a technique where you find all the solutions and then pick up the best solution, the optimal solution
- Follows the `principle of optimality` (Problems must be solved in the sequence of decisions)
- Time consuming process
- We use **iterative** instead recursion to save time
- `Cons`:
  - **Memory usage**: Uses tables or caches to store subproblem solutions and leads to high memory usage, especially for problems with large input sizes
  - **Limited applicability**: All problems can't be solved and works best for problems with optimal substructure and overlapping subproblems

![alt text](image-47.png)

#### `Greedy Method v/s Dynamic Programming`:

|            Feature            |      Greedy Method      |    Dynamic Programming     |
| :---------------------------: | :---------------------: | :------------------------: |
|           Approach            | Locally optimal choices |    Optimal substructure    |
| Guarantee of Optimal Solution |           No            |  Yes (if solution exists)  |
|        Execution Speed        |         Faster          |    Slower (potentially)    |
|   Implementation Complexity   |    Generally simpler    | More complex design needed |

### `MultipleStage Graph`(Dynamic Programming):
- 

![alt text](image-48.png)
