# blog_1
~ Introduction: Haskell in a Blog ~  

   Haskell's Got Style 
   ____________________________________________
    ** Functional Programming 
    Haskell is a purely functional programming language. Functional programming is a style of programming 
    in which the basic method of computation is the application of functions to arguments(p.4). 
    To put simply, functions can be used as arguments. How does functional programming benefit us?
    Given Haskell's ability to treat functions as values, the code is easier to debug and it's more concise. 
  
    ** How do newcomers learn functinal programming?
    
   We Love Lazy Languages
   ____________________________________________
    Haskell is lazy. To illustrate this concept, consider the following puesdo code below: 
    if(a & b) 
    {
       // do something...
       
     } 
    Similar to C++ or Java, Haskell will execute the code within the block if and only if 'a' and 'b' are true. 
    So if 'a' and 'b' are true, "do something". 
    However, if 'a' is false, we immediately know that the condition is not true. There is no need to 
    evaluate/execute "do something". 
    
  
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
   
   



