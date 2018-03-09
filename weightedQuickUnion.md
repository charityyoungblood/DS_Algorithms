<!-- Improvement on Quick Find and Quick Union Algorithms --> 

1. Weighted Quick-Union
  - When implementing the Quick Union Algorithm, take steps to AVOID having tall trees 
  - If we have a LARGE tree and a SMALL tree to combine together, we would AVOID putting the LARGE tree UNDER the SMALL tree 
  - To do this, we will KEEP TRACK of the number of objects in each tree 
  - We'll maintain balance by ALWAYS making sure that we link the ROOT of the SMALLER TREE to the ROOT of the LARGER TREE 
  - We want to make sure that NO SINGLE ITEM is too far from the ROOT
  
2. Demo of the "weighting" technique: @1:24 in Quick-Union Improvements lecture 

3. Java Implementation of Weighted Quick Union
  - We use the same data structure as Quick-Union Algorithm, BUT we create a new, extra array that for each item gives the number of objects in the tree rooted at that item (index)
  - Find: You are checking whether the roots are equal 
  - Union Command: We would need to modify the Union command to check the sizes and link the root of the smaller tree to the root of the larger tree in each case 
  - We then change the id length and update the size array 
  
4. Weighted Quick-Union Analysis
  - Running Time
    - Find operation: takes time proportional to how far down the nodes are in the tree (i.e. the depth of p and q), but we can show that it is GUARANTEED that the depth of ANY node in the tree is AT MOST is the logarithm base 2 of N 
      - this number is VERY small compared to N (i.e. if N is 1000, logarithm base 2 is 10)
    - Union command: takes constant time, given roots 
  - Why is the depth of any node X at most, log base 2 of N?
    - When does the depth of any node increase? When we attach it to a tree - X's depth will INCREASE by 1, when it's tree (T1) is merged in to another tree (T2)
    - At this point, since we would only do the above step if the size of T2 was greater than or equal to T1 
    - When the depth of X INCREASES, the size of it's tree AT LEAST DOUBLES - ** THIS IS THE KEY ** 
      - This means the SIZE of the tree containing X can double AT MOST log base 2 of N times 