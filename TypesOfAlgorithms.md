

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
  
  - We'll use the example of x = 5678 and y = 1234
  - When we multiply these two numbers, we separate the rows > start multiplying from top to bottom, until we get to our product 
  - In this example, we perform at most 2n operations per row 
  - with n rows 
  - That means the number of times this operation is performed is 2n*n or 2n squared
  - The number of operations grows - it is quadratic in the input length "n" 
  
Is there a better way, or better Algorithm, than the original Integer Multiplication algorithm we learned in grade school?

Karatsuba Multiplication 

- We'll use the same x and y values for this problem
- But we will break down the values into four variables (a, b, c, d) 
  - in Integer Multiplication Example x = 5678 and y = 1234
  - for this example: 
    a = 56
    b = 78
    c = 12
    d = 34 
- We will perform a sequence of operations only involving the above four variables (double digit numbers)
  Step 1: Compute the product of a * c = 672
  Step 2: Compute the product of b * d = 2652
  Step 3: Compute the sum of (a + b)(c + d) = 134 * 46 = 6164
  Step 4: Compute the product of Step 3 - product of Step 2 - product of Step 1 = 6164 - 2652 - 672 = 2840
  
*** NEXT: Take the results of Step 1, Step 2, and Step 4 and combine them in a simple way, to produce the product of our original x * y ***

  Step 5: Take the product of Step 1 and pad with four zeros = 6720000
          Take the product of Step 2, WITHOUT ANY PADDING    =    2652
          Take the product of Step 4, pad with two zeros     =  284000
          Add all three values                               = 7006652
          
          You have the product of x * y = 7006652
  
Recursive Algorithms - these are algorithms that invoke (call) themselves as a subroutine with a smaller input 

As this relates to the Karatsuba multiplication algorithm, 
The Input is two numbers witn "n" digits 
  x = (10*n/2)a + b (this is 10 to the power of n/2)
  y = (10*n/2)c + d
  Where a,b,c,d are n/2 - digit numbers --- here we set up the problem into smaller input
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  