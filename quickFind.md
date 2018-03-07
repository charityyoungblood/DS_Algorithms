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

  Quick Find Algorithm - "Eager Approach"
  
  - Data Structure we'll use: Integer array id[] of size n (an integer array indexed by object) 
  - Interpretation: Two objects, p and q, are connected, if and ONLY if, they have the same id 
  
     0 1 2 3 4 5 6 7 8 9 >>>  
id[] 0 1 1 8 8 0 0 1 8 8 >>>

  - In this example, there are 10 objects (integers 0 through 9)
  - The id[] describes the situation after 7 connections 
  - In the above example 
    - 0, 5, 6 are connected, as they have the same index in the id[], which is id[0]
    - 1, 2, 7 are connected, as they all have the same index in the id[], id[1]
    - 3, 4, 8, 9 are connected
    - In this example, there are 3 "Connected Components" - 3 subsets  
     ** REMEMBER ** - Connected Components: When we have an equivalence relation a set of objects and connections divide into subsets called "Connected Components" - a maximal set of objects that are mutually connected  










