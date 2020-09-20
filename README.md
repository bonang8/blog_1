# blog_1
~ Introduction: Haskell in a Blog ~  

   Haskell's Got Style 
   ____________________________________________
    ** Functional Programming 
    Haskell is a purely functional programming language. Functional programming is a style of programming 
    in which the basic method of computation is the application of functions to arguments(p.4). 
    To put simply, functions can be used as arguments. How does functional programming benefit us?
    Given Haskell's ability to treat functions as values, the code is easier to debug and it's more concise. 
    Furthermore, it prevents side effects. Meaning, it makes it hard to analyze your program for correctness. 
    Haskell can gaurentee that functions have no side effects, making it easier to prove the Haskell program 
    is correct. 
    
    ** How do newcomers learn functinal programming?
    
   We Love Lazy Languages
   ____________________________________________
    Haskell is lazy. To illustrate this concept, consider the following puesdo code below: 
    if(a & b) 
    {
       // do something...
       
     } 
    Similar to C++ and Java, Haskell will execute the code within the block if and only if 'a' and 'b' are true. 
    In short, if 'a' and 'b' are true, "do something." However, if 'a' is false, we immediately know that the 
    condition is not true. There is no need to evaluate/execute "do something." Better yet, we don't need to 
    evaluate 'b'- saving us time. Laziness pays off (in this sense). 
  
   Useful Tips in Haskell 
   ____________________________________________
   ** Which external sources (videos, blogs, tutorials, etc) do you find most useful?
   Top two must read resources are: 
      1. Learn you a Haskell for Great Good 
      2. Programming in Haskell. 
   Both illustrate ideas imperative to Haskell in the most simplest way. 
   
   
   
   How does Haskell compare to your favourite programming language? Give examples of the same algorithm written in your favourite language and in Haskell. 
   What are the respectives strengths and weaknesses of the two programming paradigms?
  
  
   
   No Hassle Haskell 
   ____________________________________________
   **   What are, in your opinion, the major stumbling blocks in learning Haskell?
    It is an indisputable fact (at least in my book) that Haskell can be a pain...at first. 
    The shift from a C++ background to Java and Python was not as troublesome from my transition to Haskell. 
    However, for those who did not struggle, congratulations! To start, Haskell is different from any programming
    language I have ever learned. As stated earlier, Haskell is a functional programming language but my devotion 
    to imperative OOP style programming crossfires with Haskell. You can say it's more to my style (no pun intended). 
    Second, Haskell is considered 
   

~ Haskell Activites | Recursion in Functional Programming  ~ 
   
  Recursion is Your Bestfriend 
  ____________________________________________
  In Haskell, recursion is your bestfriend. 
    I found a few interesting features about Haskell while completing the following activity: 
     Implement the following functions in Haskell 
       select_evens
       select_odds
       member
       append
       revert
       less_equal
   
   
     --select_evens :: [Int] -> [Int]
      select_evens [] = []
      select_evens (x:xs) = if x `mod` 2 == 0 then x:select_evens xs else select_evens xs
      -- extra exercise for even and odd

      -- point: is to check if the member exists in the list 
      member m [] = False 
      member m (x:xs) = if m == x then True else member m xs
      -- point: append two lists together 
      append [][] = []
      append (x:xs)(y:ys) = x:xs ++ y:ys
      -- point: to reverse the lists
      -- concatenate the head 
      revert[] = [] 
      revert(x:xs) = revert xs ++ [x]
      -- point: the less equal function compares each element from each lists and checks if the first is less than or equal to the other 
      -- only returns true if all the elements from list 1 are less than or equal to the second list 
      less_equal [] [] = True 
      less_equal (x:xs)(y:ys) = if x > y then False else less_equal xs ys
   


   Peano not Piano 
   ____________________________________________
   Yes, I did mix up piano and Peano when I first heard of Peano arithmetic. In my defense, I wasn't the only one. 
   What's the significance of Peano arithmetic? 
   When I first applied Peano-Dedekind axioms for arithmetic in Haskell, I found that Haskell's type system is central to the language. 
   Peano arithmatic is the gateway to defining the most basic of arithmatic concepts that are recursively defined. 
   Let's examine a few examples: 
   
   **EXAMPLE_1: ADDITION 
   Peano-Dedekind axiom postulates that: 
     0 is a natural number 
     
   -- numbers
data NN = O | S NN
  Data is a keyword in Haskell used to define a data type like a typedef in C or C++. What this line does is to define the natural numbers (NN) data type as being    0 or a successor to NN. 
   deriving (Eq,Show)
-- addition
add :: NN -> NN -> NN
add O n = n
add (S n) m = S (add n m)
-- add (S O) (S (S O))
-- multiplication
-- for the third line--> lets say we have two natural numbers 5 and 3--> we would have to add 5 three times therefore we call the addition function  
-- mult (S (S O)) (S (S ( S O)))
mult :: NN -> NN -> NN
mult O n = O 
mult (S n) m = add m (mult n m) 
-- subtr 
subtr :: NN -> NN -> NN 
subtr n O = n 
subtr O m = O 
subtr (S (n)) (S (m)) = subtr n m
{- 
(S (S O)) - (S O)  2-1
n = S O     m = O
S O - O     base case 
S O
-}
-- a language for arithmetic expressions
data Exp = Num Int | Plus Exp Exp | Times Exp Exp

eval :: Exp -> NN
eval (Num 0) = O
eval (Num n) = S (eval (Num (n-1)))
eval (Plus n m) = add (eval n) (eval m)
eval (Times n m) = mult (eval n) (eval m)
-- eval (Times (Num 2) (Num 3))
-- eval (Plus (Num 1) (Times (Num 2) (Num 3)))
-- data PN = I | T PN

   



