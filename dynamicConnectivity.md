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

    Transitive: means that if it applies between successive members of a sequence, it must also apply between any two members taken in order. Meaning, if p is connected to q and q is connected to r, then p is connected to r (indirectly connected)

  - Connected Components: When we have an equivalence relation a set of objects and connections divide into subsets called "Connected Components" - a maximal set of objects that are mutually connected 
  - These components have the property that if any two objects in them are connected and there's no object outside that are connected to those objects - our algorithms will gain efficiency by maintaining connected components and using that knowledge to efficiently answer the query that they are presented with 
  
4. To Implement the Operation
  - Find query: this will check if two objects are in the same component
  - Union command: this will replace components containing two objects with their union
  
5. Union-Find Data Type (API)
  - All of this leads up to specifying data type, which is a specification of the methods that we want to implement in order to solve this problem 
  
  - Our GOAL - to design efficient data structure for our union-find
    - The number of objects "n" can be HUGE 
    - The number of operations "m" can be HUGE
    - Find queries and union commands may be intermixed 
    - Our algorithm has to be EFFICIENT under these conditions 
    
  - In Java, we will create a Class called UF - that contains two methods 
    - one to implement union
    - one to implement conected, which returns a boolean
  - The constructor takes the number of objects as an argument, so it can build data structures based on that number of object 
  - 
  
    ** Example of the code:  public class UF
                             UF(int N)  >>>> initialize union-find data structure with "n" objects (0 to n - 1)
                             void union(int p, int q)    >>> add connection between p and q 
                             boolean connected(int p, int q) >>> are p and q in the same component? 

6. Check our API Design - BEFORE getting to far into the problem, check your API design by building a client (i.e. "test code") that will use the data type that we develop 

  - Full code example of Dynamic-Connectivity Client at Dynamic Connectivity lecture @8:49

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  