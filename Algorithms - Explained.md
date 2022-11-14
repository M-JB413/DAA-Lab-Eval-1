### Graph: Web-Graphs   

    Algorithms Implemented:  
        * Reachability (modified BFS to record paths)
        * Exploring Topological Ordering
        * Navigation (Bi-Connected Components and Strongly Connected Components using Kosaraju's Algorithm)
### Sorting: Bubble Sort
    * Implementation of bubble sort algorithm
    * Performance Analysis

## Graphs

### 1. BFS Algorithm - 
    Data Structures required:
        1. Queue
        2. Visited Array of size N (Number of nodes)

###### Algorithm:  

    * Declare a queue and insert the starting vertex.
    * Initialize a visited array and mark the starting vertex as visited.
    * Follow the below process till the queue becomes empty:
        * Remove the first vertex of the queue.
        * Mark that vertex as visited.
        * Insert all the unvisited neighbours of the vertex into the queue.

###### Result:
A triplet gets returned -> (home page, destination page, number of clicks to reach destination page 
from home page)
This is then written into a CSV file using fwrite function in python.

**Time Complexity** - O(V + E)
**Space Complexity** - O(V^2) - Using an adjacency list. 

### Topological Ordering : DFS is applied to get the topoligcal order -

    Data Structures required: 
        1. Stack (comes into play when using recursion)
        2. Visited array of size N (Number of nodes)
   
###### Algorithm:
    * Create a stack to store the nodes.
    * Initialize visited array of size N to keep the record of visited nodes.
    * Run a loop from 0 till N
        * If the node is not marked True in visited array
            * Call the recursive function for topological sort and perform the following.
                * Mark the current node as True in the visited array.
                * Run a loop on all the nodes which has a directed edge to the current node
                    * If the node is not marked True in the visited array:
                        * Recursively call the topological sort function on the node
                * Push the current node in the stack.
    * Print all the elements in the stack.

###### Result:
The topological order is printed partially and it stops because a cycle exists in the given Web Graph
data set. Topological Order exists only for a DAG(Directed Acyclic Graph)

**Time Complexity** - O(V + E)
**Space Complexity** - O(V)
### 3. Strongly connected components - Kosaraja's Algorithm

**Definition:** 
    -> A directed graph is strongly connected if there is a path between all pairs of vertices. 
    -> A strongly connected component (SCC) of a directed graph is a maximal strongly connected              subgraph.
    -> Individual Nodes can also be considered as strongly connected components

    Data Structures required:
        * Stack
        * Visited Array
   
###### Algorithm:
    * Create an empty stack ‘S’ and do DFS traversal of a graph. 
    * In DFS traversal, after calling recursive DFS for adjacent vertices of a vertex, push the vertex to stack. 
    * Invert the graph by switching the directions. u -> v becomes v -> u. Note that inverting the edge directions won't affect the cycles because they'll remain unchanged.
    * From the stack 'S', pop each vertex 'V' while S is not empty.
        * Take every popped vertex 'V' as the source node and perform DFS to get the Strongly                   Connected Component of 'V'. 

###### Result:
    A tuple is returned with every node in each Strongly Connected Component and each tuple is written into a CSV file and at the end, the number of Strongly Connected Components for the given Web Graph. 
     
**Time Complexity** - O(V + E) -> Since multiple DFS calls are only made
**Space Complexity** - O(V)
## Sorting
### 1. Bubble Sort

**Algorithm -** 
    * Run a nested for loop to traverse the input array using two variables i and j,such that 0 ≤ i < n-1 and 0 ≤ j < n-i-1
    * If arr[j] is greater than arr[j+1] then swap these adjacent elements, else move on
    * Print the sorted array
    
**Inference -** 
During every pass, the largest element gets placed in its correct position. Ex: 1st pass, largest element is placed at the end, 2nd pass, 2nd largest element is in 2nd last position and so on.

**Time Complexity** - O(N^2)
**Space Complexity** - O(1)
