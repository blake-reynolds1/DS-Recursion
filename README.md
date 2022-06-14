# Recursion: Backtracking
## Objectives
* Understand backtracking algorithms and use them to solve problems
* Use recursive functions to implement backtracking algorithms
* See how the choice of data structures can affect the efficiency of a program
## Outline
* Example 1: Permutation
* Permutation Extension: Iterative
* Performance Evaluation
* Keys of Backtracking
* Example 2: N-Queens Problem
## Permutation
* A permutation of a set of distinct objects is an ordered arrangement of these objects. 
* An ordered arrangement of r elements of a set is called an 𝑟 -permutation.
  - A string of length n has n! permutation
* The number of r - permutations of a set with n elements is denoted by P(n, r)
  - The 2-permutations of 𝑆 ൌ ሼ1,2,3ሽ are 1,2; 1,3; 2,1; 2,3; 3,1; and 3,2. Hence, 𝑃(3,2) = 6
  - P(n, r) = n(n-1)... (n -r + 1) = n!/(n-r)
* <img width="745" alt="Screen Shot 2022-06-14 at 4 48 09 PM" src="https://user-images.githubusercontent.com/89602311/173695208-6cecceb6-f88b-45a7-a4a7-97923377cba2.png">
* Question
  - Given a string without duplicated characters, retuen all the possible permutations. You can return the answer in any order.
  - Example:
    - Input: str = "ABC"
    - Output: "ABC", "ACB", "BAC", "BCA", "CBA", "CAB"
* A recursive strategy
  - For each char ch, swap it with each of other char on the right
    - After swapping, this is a new permutation
    - Then fix this char ch, and look for other permutations
  - Keep doing this for other char on the right
* <img width="530" alt="Screen Shot 2022-06-14 at 4 58 49 PM" src="https://user-images.githubusercontent.com/89602311/173696313-664ea399-af80-45af-87ca-4b4a70667325.png">
* <img width="864" alt="Screen Shot 2022-06-14 at 5 01 42 PM" src="https://user-images.githubusercontent.com/89602311/173696708-a652608f-b5a7-4bf4-9468-40f18bb81aba.png">
## Permutation Extension
* It is always true that recursion can be replaced by iteration and stacks
  - This iterative solution will work the same as what just happened in the call stack dor a recursive solution
  - Look at the recursion tree and call stack
  - <img width="554" alt="Screen Shot 2022-06-14 at 5 30 30 PM" src="https://user-images.githubusercontent.com/89602311/173700028-4252fd5a-8cc2-4c17-8b28-2b78fbccdfdf.png">
* Can you develop an iterative solution for permutation
  - make a try
    - this is a bit challenging
    - but this will help improving your skills
  - Optional
## Analysis of Backtracking
* 
