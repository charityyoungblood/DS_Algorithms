<!-- Quick-Union Algorithm --> 

## Steps to Developing a Usable Algorithm 
    1. Model the problem: try to understand the main elements of the problem that needs to be solved 

    2. Find an algorithm to solve it 

    3. Is the algorithm fast enough? Does it fit in memory?

    4. If not, figure out why

    5. Find a way to address the problem 

    6. Iterate until satisfied 
    
# ###############################################

We are currently at Step 4 - 5 in Developing a Usuable Algorithm (for the Dynamic Connectivity Problem)

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
    
C. Java Implementation of Quick-Union Algorithm 
 
## First, we declare class QuickUnionUF ## 

    public class QuickUnionUF { 
    
## Second, we create our data structure, the id array, which will hold "type" Integer ##

      private int[] id; 
      
## Third, we create a QuickUnionFindUF method, which takes on one argument, N, of type Integer 

      public QuickUnionUF(int N) {
 
## Fourth, we initialize a new id array with N length

        id = new int[N]; 

## Fifth, we create a for loop, to loop over the id array, under the condition: "while i is less than the length of the array", increment i by one  
        
        for (int i = 0; i < N; i++)  
        
## Sixth, we set each element to be it's OWN ROOT, id[i] = i 

          id[i] = i; 
      }
    
## Seventh, we create a private method that implements the process of finding the root, by chasing "parent pointers" i.e. the root, until we get to the point where i is equal to id[i]

      private int root(int i) { 
        while (i != id[i])
        
## If i is NOT EQUAL to id[i], we move i up one level in the tree, set i = id[i] 
          i = id[i]; 
          return i; 
      }
    
## Eighth, create a public method "connected", that checks if the root of p is equal to the root of q 

      public boolean connected(int p, int q) {
        return root(p) == root(q); 
      }
      
## Ninth, create a union operation that finds the two roots and then set the id of the first root to the id of the second root 
      public void union(int p, int q) {
        int i = root(p);
        int j = root(q); 
        id[i] = j;
      }  
    }
  
Now, we are back to Step 3 in Developing a Usuable Algorithm (for the Dynamic Connectivity Problem)

D. Is the Quick-Union algorithm fast enough? Does it fit in memory?
  - Unfortunately, Quick-Union is also too slow 
  - Cost Model: Think about the number of times the code has to access the array (Number of array accesses)
  - In our above example, the QuickUnionUF operation involved a "for" loop, and the "root" function/operation, involved a while loop
    - these both go through the entire array, in a constant proportional to "N" times they have to touch the array entry
  - The "union" operation is "quick", it just sets the two roots with the same id
    - this ALSO has a "constant" number of "N" times to check array entries 
  - We have N initialization, N objects and N operations - making the Quick Union Algorithm a 
  - Defect for Quick-Union is the "trees" can get TOO TALL, which would mean that the "find" operation would be too expensive 
    - You could wind up with a long, skinny tree of each object pointing to the next and then to do a find operation for object at the bottom, would involve going all the way through the tree involving "N" array accesses - JUST for the "find" operation
    - This will be TOO SLOW if you have a lot of operations 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  