<!-- Quick-Union Algorithm --> 

## Steps to Developing a Usable Algorithm 
    1. Model the problem: try to understand the main elements of the problem that needs to be solved 

    2. Find an algorithm to solve it 

    3. Is the algorithm fast enough? Does it fit in memory?

    4. If not, figure out why

    5. Find a way to address the problem 

    6. Iterate until satisfied 
    
# ###############################################

We are currently at Step 4 in Developing a Usuable Algorithm (for the Dynamic Connectivity Problem)

Since Quick-Find was not deemed EFFICIENT or fast enough, we will try to implement another algorithm called Quick-Union

A. Quick-Union: a "Lazy Approach" to algorithm design - where we try to avoid doing work until we have to 
  
  i   0 1 2 3 4 5 6 7 8 9 
id[i] 0 1 9 4 9 6 6 7 8 9 

- Each "i" value is "mapped/connected" to an id[i] value 
- In the above example, here are the connections: the first number is "i" value, second "connected number" is the id[i] value
  - 0 is connected to 0, the "root" of 0 is also 0, as there are no other connection that go "up" the ladder 
  - 1 is connected to 1, the "root" of 1 is also 1, as there are no other connection that go "up" the ladder
  - 2 is connected to 9, and 9 is connected to 9 - which means the root of 2 is 9, or 9 is the root of 2 (same)
  - 3 is connected to 4, 4 is connected to 9, 9 is connected to 9 - 9 is the root of 3 
  - 4 is connected to 9, 9 is connected to 9 - 9 is the "root" of 4
  - 5 is connected to 6, 6 is connected to 6, - which means 6 is the "root" of 5 
  - 6 is connected to 6, 6 is the root of 6 
  - 7 is connected to 7, 7 is the root of 7
  - 8 is connected to 8, 8 is the "root" of 8
  - 9 is connected to 9, 9 is the "root" of 9 
  
B. The Data Structure for Quick-Union
  - Integer Array id[] of size N
  - Interpretation: id[i] is a parent of i - we will think of the integer id array id[] as representing a set of trees, or "forest"
  
    - Each entry in the id[] array is going to contain a reference to its parent in the tree 
    - For example, using the id[] and i structure above, the parent of 3 is 4, the parent of 4 is 9 - so 3's entry on the id[] is 4 and 4's entry in id[] is 9
    - Each entry in the array has a ROOT associated with it, this is the ROOT of it's tree - elements that are all by themselves, i.e. they are their own CONNECTED COMPONENT, point to themselves 
    - From this data structure we can associate with each item, a ROOT which is representative of its CONNECTED COMPONENT 
    - Once we CALCULATE the ROOTS, we can implement the FIND operation
    
  - Find operation: will check if p and q have the same root - this is the equivalent of saying "are they in the same CONNECTED COMPONENT"? - this will require some degree of work 
  
  - Union operation: this is very easy - to merge components containing p and q, set the id of p's root to the id of q's root 
    - For EACH one of the union operations, ONLY involves changing ONE entry in the array - VERY EFFICIENT 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  