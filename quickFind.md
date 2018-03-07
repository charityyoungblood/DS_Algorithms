<!-- Quick-Find Algorithm to Solve Dynamic Connectivity Problem -->

  ## Steps to Developing a Usable Algorithm 
    1. Model the problem: try to understand the main elements of the problem that needs to be solved 

    2. Find an algorithm to solve it 

    3. Is the algorithm fast enough? Does it fit in memory?

    4. If not, figure out why

    5. Find a way to address the problem 

    6. Iterate until satisfied 
    
# ###############################################

We are currently on Step 2 of Developing a Usable Algorithm:

A. Quick Find Algorithm - "Eager Approach"
  
  - Data Structure we'll use: Integer array id[] of size n (an integer array indexed by object) 
  - Interpretation: Two objects, p and q, are connected, if and ONLY if, they have the same id 
  
     0 1 2 3 4 5 6 7 8 9 >>>  
id[] 0 1 1 8 8 0 0 1 8 8 >>> each entry is equal to it's index into the id array

At the start, ALL OBJECTS are independent, i.e. they are in their own "CONNECTED COMPONENT" 
  - as you start to add union function (i.e. union (4,3)) - the points are then connected, either directly or indirectly (@2:40 in Quick-Find video lecture)
  - For union(4,3) we will change all entries who's id is equal to the first id, to be equal to the second id
    id[3], id[3] - now index 3 and index 4 are equal to 3

  - In this example, there are 10 objects (integers 0 through 9)
  - The id[] describes the situation after 7 connections 
  - In the above example 
    - 0, 5, 6 are connected, as they have the same index in the id[], which is id[0] - they also have the SAME "CONNECTIED COMPONENT"
    - 1, 2, 7 are connected, as they all have the same index in the id[], id[1] - they also have the SAME "CONNECTIED COMPONENT"
    - 3, 4, 8, 9 are connected, as they all have the same index in the id[], id[8] - they also have the SAME "CONNECTIED COMPONENT"
    - In this example, there are 3 "Connected Components" - 3 subsets  
     ** REMEMBER ** - Connected Components: When we have an equivalence relation a set of objects and connections divide into subsets called "Connected Components" - a maximal set of objects that are mutually connected  

B. This above example will support a QUICK implementation of the Quick-Find Algorithm, as we will check the array entries to see if they are equal 
  - Implementation of Quick-Find Algorithm
  
    Find: Check if p and q have the same id 
    
    Union: In order to merge the components of two given objects, p and q, we have to change all the entries whose id equals id[p] to equal id[q] - i.e. we will "switch" values
   
      - After union of 6 and 1, we have to change all the entries having an id[0] to an id[1] 
      - We'll see this Union command as a problem, when we have a huge number of objects as values can change
      
    ** Breakdown at video lecture: @1:30
    
    
C. Java Implementation of Quick Find
    
      pulic class QuickFindUF  - The "Constructor"
      
      {
        private int[] id; - Data Structure: we use a private integer array (for our id[]) which is the data structure we will use to support this implementation 
        
        public QuickFindUF(int N) -  The "Constructor" has to create the array (in line 64) - then go through and set the value corresponding to each index [i] to [i] 
        {
          id = new int[N];
          for (int i = 0; i < N; i++)
            id[i] = i;
        }
    
        public boolean connected(int p, int q) - this is the find/connected operation, which is the Quick-Find Algorithm
          - it takes two arguments, integer values p and q, and checks whether their id entries are equal, i.e. index in the id array 
          - if the two id indexes are equal this function will return true, if not, it will return false 
          
        { return id[p] == id[q]; }
        
        public void union(int p, int q) - We first find the id index corresponding to the first argument, then the id index corresponding to the second argument 
          - We then go through the whole array (id[]) and look for the entries who's id's are equal to the id of the first argument, and set those equal to the id of the second argument 
        {
          int pid = id[p];
          int qid = id[q;]
          for (int i = 0; i < id.length; i++)
            if (id[i] == pid) 
              id[i] = qid;
        }
    }
    
We are now at Step 3 of Developing a Usable Algorithm

D. Is the Quick-Find Algorithm Fast Enough? Does it Fit in Memory?

  - Cost Model: Think about the number of times the code has to access the array (Number of array accesses)
  - In our above example, both the initialize and the union operation involved a "for" loop that go through the entire array, in a constant proportional to "N" times they have to touch the array entry
  - The "find" operation is "quick", it just has a "constant" number of times to check array entries 
  - However find operation is problematic, because the "union" command is TOO EXPENSIVE, meaning if you have N union commands on N objects - that will take "QUADRATIC TIME" or N^2 time
  
## IMPORTANT ##   
   - One of the themes that we'll cover over and over in this course is that QUADRATIC TIME (when the number of commands "N" is equal to to the squaure of it’s input value "N" objects, N * N) is MUCH TOO SLOW 
   - We CAN'T accept QUADRATIC TIME algorithms for LARGE PROBLEMS, because they DON'T SCALE 
   - As computers get faster and bigger, QUADRATIC ALGORITHMS get slower 
  
  
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      

































