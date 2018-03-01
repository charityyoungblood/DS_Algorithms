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
