<!-- The Dynamic Connectivity Problem/Model to Use Quick Find Algorithm -->

1. Given a set of N objects 
  - use Union command: this will connect two objects (in this case, two Integer objects)
  - use Find/connected query: this query is to "search" or check to see if there is a path, either direct or indirect, connecting the two objects 
  - visual example at Dynamic Commectivity lecture @2:10
  - The problem we are addressing is, to be able to efficiently support the two above command/query for a given set of objects 

2. For programming, as we are modeling the objects, we will associate each object with a name, and name the objects with an Integer value from 0 to n - 1 
  - We will use integers as an "index" into an array 
  - Suppresses a lot of details that are NOT relevant to Union Find 
  
3. Modeling the Connections
  - We assume "is connected to" is an equivalence relation: that means every object is connected to itself  

    Reflexive: means that every object is connected to itself, i.e. p is connected to p 

    Symmetric: if p is connected to q, then q is connected to p 

    Transitive: if p is connected to q and q is connected to r, then p is connected to r 

. Connected components