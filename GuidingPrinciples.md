<!-- Guiding Principles for How To Define/Analyze Algorithm --> 

1. We use "Worst-Case Analysis" - in the case of Merge Sort, our upper bound (Upper Bound: is any number that is greater than or equal to all of the elements of the set. In a set of 0,1,2,3,4 - 5 would be the upper bound) of 6 times n, times the logirithm of n (log base 2), plus 6n (6nlog2n + 6n) applies to the number of lines of executed code for every single input array of length "n" 
  - We made no assumptions about the input, where it comes from, what it looks like, etc BEYOND what the input length n was  
  - Our running time bound holds for EVERY input of length n (i.e. no matter how long the array is, it will still take <= 6nlog2n + 6n operations)
  - Two Other Methods of Algorithm Analysis (These are NOT covered in this class) 
    - "Average Case Analysis": here you analyze the "average" running time of an algorithm, under some assumption under the relative frequencies of different input
    - Bechmarks (Pre-specified): One agrees, upfront, about some set of "benchmark" input, thought to represent practical or typical inputs for the algorithm
    - Both Benchmarks and Average Case Analysis are USEFUL in certain settings, but they require additional knowledge about your problem, Domain knowledge: i.e. what input is more common than others, what input represents "typical" input than others 
  
  - By contrast, with Worst-Case Analysis, we are not making any assumptions about WHERE the input comes from 
  - As a result, Worst-Case Analysis is particularly appropriate for "general purpose" sub routines - sub routines that you design, without having any knowledge of HOW they will be used or what kinds of input they will be used on 
  - Another BONUS of doing "Worst-Case Analysis" is it's usually, Mathmatically, much more attractable in trying to perform the analysis of the running time of an algorithm under some distribution over inputs or to understand the detailed behavior of an algorithm on a particular set of benchmark inputs
    - i.e. this method is much EASIER to analyze 
    
2. We won't pay much attention to constant factors and lower-order terms 
  - Mathematically, it is WAY EASIER to analyze an algorithm if we don't have to precisely pin down what the constant factors are 
  - Since we are describing algorithms that transcends any programming language (i.e. NOT programming language specific) it would be inappropriate to specify constants - the precise constants will be determined by programming language/architecture/compiler 