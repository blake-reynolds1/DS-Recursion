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
* Just think about the property of permutation
  - A string of length n! permutation
* The time complexity is above n!
  - This algorithm is very slow
  - This function grows the fastest, among which we have learned in Discrete Structures
    - Evaluation function grows fast means the algorithm is slow
  - This is required by the problem naturally
## Keys of Backtracking
* Backtracking algorithms
  - search for a solution by
    - constructing partial solutions that remain consistent with the requirements of the problem, and then
    - extending a partial solution toward completion
    - And recovering to peer partial solution could be needed
  - When inconsistency occurs, the algorithms backs up (backtracks) by
    - removing the most recently constructed part of the solution, and then
    - trying another possibility
## Eight-Queens Puzzle
* How to place eight queens on a chess board so that no queen can take another
  - Remember that in chess, a queen can take another piece that lies on the same row, column or the same diagnol
* <img width="543" alt="Screen Shot 2022-06-14 at 5 55 26 PM" src="https://user-images.githubusercontent.com/89602311/173702623-5bd6f905-2f7f-4921-a22d-1f0902287df1.png">
* X: Gaurded sqaures
* ?: Other squares that have not been tried
* A simplier version: 4-Queens
* <img width="557" alt="Screen Shot 2022-06-14 at 5 56 25 PM" src="https://user-images.githubusercontent.com/89602311/173702742-bc9de723-de48-432e-bdbe-0ea7c1f5116d.png">
* Solutions do exist
  - requires luck coupled with trial and error
  - exhaustive computation
  - <img width="430" alt="Screen Shot 2022-06-14 at 6 03 45 PM" src="https://user-images.githubusercontent.com/89602311/173703390-e01777f2-db64-483c-8a7e-e8ade2142b1c.png">
* How will you solve the problem?
  - Put the queens on the board one by one in some systematic/logical order
    - Make sure that you will not revisit the same situation
    - The whole process is suitable for recursive programming
      - A large problem can be divided into small subproblems with a similar nature
  - Make sure that the queen placed will not be taken by another already on the board
  - If you are lucky to put eight queens on the board, one solution is found
  - Otherwise, some queens need to be removed and placed elsewhere to continue the search for a solution
* How to find the next square to try?
  - There must be a queen, exactly one in each row
    - There can never be more than one queen in a row
  - Therefore we can place the queens one row at a time in order
    - What we have decided is actually a systematic way to solve the problem
  - <img width="284" alt="Screen Shot 2022-06-14 at 6 07 11 PM" src="https://user-images.githubusercontent.com/89602311/173703682-859aec37-a602-41cd-8c4c-53f6dbda213c.png">
* Program Outline
  - Recursive function: solve_from
    - Given a configuration of queens on the chessboard, search for all solutions
  - Class Queens
    - Represent a particular configuration of queens on the chessboard
  - Code Outline
    - <img width="506" alt="Screen Shot 2022-06-14 at 6 08 36 PM" src="https://user-images.githubusercontent.com/89602311/173703819-48df6a1b-bbc9-4aa2-b53f-16feb3c45dc4.png">
  - <img width="573" alt="Screen Shot 2022-06-14 at 6 08 55 PM" src="https://user-images.githubusercontent.com/89602311/173703853-3c5bd1a6-4e6d-4716-9345-87236e444f70.png">
  - <img width="569" alt="Screen Shot 2022-06-14 at 6 10 09 PM" src="https://user-images.githubusercontent.com/89602311/173703976-3067dca7-e38e-45ca-bdf4-386d09d92f85.png">
  - <img width="544" alt="Screen Shot 2022-06-14 at 6 10 31 PM" src="https://user-images.githubusercontent.com/89602311/173704003-af1d4268-0563-40b7-a7ed-db5d92394055.png">
  - <img width="540" alt="Screen Shot 2022-06-14 at 6 10 42 PM" src="https://user-images.githubusercontent.com/89602311/173704030-b26c273c-09a1-437a-a915-3adfb2e1dba1.png">
  - <img width="557" alt="Screen Shot 2022-06-14 at 6 10 58 PM" src="https://user-images.githubusercontent.com/89602311/173704055-6fdaaa53-fc4a-4c3e-ba54-bb34713ad9e9.png">
  - <img width="528" alt="Screen Shot 2022-06-14 at 6 11 15 PM" src="https://user-images.githubusercontent.com/89602311/173704066-c96a8b4b-9489-4f7d-82b0-4e3b68f5a562.png">
* The time increases rapidly with the board size
  - exponential growth
* Number of solutions
  - not bounded by any polynomial n
  - Even not bounded by any exponential form k^n, where k is a constant
  - It is proved to be an unsolved problem 
* A refinement
  - keep track of unguarded squares by using three bool array: col_free, upward_free, downward_free
    - Diagonals from th elower lefr to the upper left area called upwards diagonals
    - Diagonals from the upper left to the lower right area called downward diagonals
  - <img width="540" alt="Screen Shot 2022-06-14 at 6 50 21 PM" src="https://user-images.githubusercontent.com/89602311/173707886-841da71a-35a4-4f38-bcdc-d03dccabab26.png">
  - <img width="551" alt="Screen Shot 2022-06-14 at 6 50 53 PM" src="https://user-images.githubusercontent.com/89602311/173707933-56232caf-aabf-49d7-8f32-b71221fc8356.png">
## Self Test
* Can you get all possible r-combinations?
  - An r-combination of elements of a set is an unordered selection of r elements from the set
  - An r-combination is simply a subset of the set r elements
  - The number of 𝑟 -combinations of a set with n distinct elements is denoted by C(n, r),  or (n r) (supposed to be a column, rather than a row)
    - The 2-combinations of set S = {a, b, c, d} are {a,b}, {a,c}, {a,d}, {b,c}, {b,d} and {c,d}. Hence C(n,r) = 6
