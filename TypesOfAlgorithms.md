

When creating algorithms, we generally will follow a pattern 

  - We will Define a computational problem
  - We will say what the Input is 
  - We will say what the desired Output is
  - We will proceed to giving a solution, an ALGORITHM, that transforms the Input into the Output
  
  Integer Multiplication
  
  - Computational Problem: Integer Multiplication
   
  - What is the Input: Two n-digit numbers x and y 
    ** Think of "n" as a VERY large number
    
  - What is the desired output: The PRODUCT of x * y
  
  - The way will assess the PERFORMANCE of this algorithm, is through the number of basic operations that it performs 
  - Primitive Operation: in this case the "basic operation" is to add or multiply 2 single-digit numbers 
  - We'll then move on to the number of these basic operations performed by the algorithms of a function of the number n of digits in the Input (Input length = n)
  
  - In this example, we perform at most 2n operations per row 
  - The number of operations grows - it is quadratic in the input length "n" 