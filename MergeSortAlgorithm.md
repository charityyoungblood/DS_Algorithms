1. Merge Sort is an OLDIE, but GOODIE - about 70 years old but used very frequently in practice 

2. Divide and Conquer Paradigm- means you take a problem > break it down into smaller "sub problems" > which you then solve "recursively" > then combine the results of the smaller sub problems to get the solution to the original problem 

3. Studying Merge Sort is a great introduction to Divide and Conquer Paradigm - improves over Selection Sort, Insertion and Bubble Sort

4. Assessing if an algorithm is "good" or "bad" is in terms of it's running time and ability to scale 

5. The Sorting Problem - 
  Input: An array of n numbers, which ARE NOT sorted (i.e. [5,4,1,8,7,2,6,3]) 
  Desired Output: The input array in SORTED order (increasing) (i.e. Desired Output [1,2,3,4,5,6,7,8])
  
  Step 1: Split input into smaller sub problem
  x = [5,4,1,8]
  y = [7,2,6,3]
  
  Step 2: Sort x and y recursively (individually)
  x.sort (or some other method) = [1,4,5,8]
  y.sort (or some other method) = [2,3,6,7]
  
  Step 3: Merge (combine) x and y to get result of fully sorted array 
  x and y = [1,2,3,4,5,6,7,8]
  
** This example ignores base cases, i.e. if the array only has 2 indices, if the input is relatively small, etc - in this cases, you wouldn't use recursion, you would just return the array **

6. The Sorting Problem in Pseudocode

  Step 1: We'll use c = output array [length = n]
  Step 2: Set a to 1st part of array [n/2] sorted -- which is the array length divided by 2        
          Set b to 2nd part of array [n/2] sorted -- the array length divided in second half
  ** In order to "sort" through each array a and b, we will implement two counters 
      i counter for a set to = 1
      j counter for b set to = 1
      
  Step 3: Create k counter set to 1 , we are looking for the smallest element overall - the purpose of k is to traverse (to go through/iterate) over the output array from left to right - checking for the smallest element overall 
          Check both a and b 
          
    Final algorithm 
    
    for k = 1 to n (n is the length of the original array)
      if a(i) < b(j) 
        c(k) = a(i)
        i++
      else b(j) < a(i)
        c(k) = b(j)
        j++
    end 
    
7. Analyze how many operations are used in our Merge Sort Algorithm?
  - We have the variable assignment of i counter
  - We have the variable assignment of j counter 
  - We have the variable assignment for k in a for loop 
  - The if statement to check if a at index i is less than b at index j 
  - We have the assignment of c(k) = a(i)
  - The incrementing  of i++
  - The else statement checking if b at index j is less than a at index i
  - We have the assignment of c(k) = b(j)
  - The incrementing of j++
  - In total, we have at least 6 operations, which can be computed as <= 6n (at least, i.e. less than or equal to 6n)
  
8. Running Time of Merge Sort - How many lines of code will merge sort take?
  - The claim is that Merge sort never needs more than 6 times n, times the logirithm of n (log base 2), plus 6n operations to correctly sort an input array of n numbers 
  - The formula would look like this: <= 6nlog2n + 6n 
  - In this case, the logirithm is much, much smaller than the input - this means the running time is much faster 
  
9. Proof the claim (assuming n = power of 2)
  - We will proof this claim using the recursion tree method: this will write out all of the work done by the recursive merge sort algorithm in a "tree" structure 
    - the children of a given "node" (leaf) would correspond to the recursive calls made by that node 
  - The point of the tree structure is to facilitate an interesting way to count up the overall work done by the algorithm and will greatly facilitate the analysis 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  