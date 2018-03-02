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
  - In total, we have at least 6 operations, which can be computed as <= 6n
  
8. Running Time of Merge Sort - How many lines of code will merge sort take?
  - Merge sort requires <= 6nlog2n + 6n 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  