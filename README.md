# algebra-driven-design-resources

I was inspired to make this as a resource for gathering helpful tools and explanations for describing an interesting way to write software. By utilizing concepts coming from a combination of abstract algebra and lambda calculus, I believe it is possible to construct abstractions and data types that can lead to software that is easy to maintain, easy to modify, and easy for new talent to reason about. 

# Useful background context for abstract algebra

This youtube [video](https://youtu.be/xAFawAKjLfA) was great to get things going. It introduces concepts of abstract algebra and the presenter's application to writing animation library in Swift.

This [playlist](https://www.youtube.com/playlist?list=PLi01XoE8jYoi3SgnnGorR_XOW3IcK-TP6) is an awesome introduction for beginners who are not familiar with abstract algebra to get familiar with concepts such as groups, rings, and isomorphism.

This [textbook](https://www.amazon.com/Applied-Abstract-Algebra-Undergraduate-Mathematics-ebook-dp-B000YIYN9C/dp/B000YIYN9C/ref=mt_other?_encoding=UTF8&me=&qid=1609381590) goes into examples of applied abstract algebra, most importantly abstract data types and their implications on software design.

[Abstract Data Types wiki](https://en.wikipedia.org/wiki/Algebraic_data_type)

This [ebook](https://algebradriven.design/) which was the first material I read regarding the subject but found it too difficult as an introduction into the subject. All the earlier listed material were very helpful in helping me connect the dots for this book.

This book "Algebra of of Programming" by Richard Bird and Oege de Moor [online book](https://themattchan.com/docs/algprog.pdf)

# Useful functional programming techniques and concepts

A great [introduction course](https://www.futurelearn.com/courses/functional-programming-haskell) that I personally completed in a week as an experienced developer

Haskell book list (Haskell is very pure in its approach to functional programming):
* [Real World Haskell](http://book.realworldhaskell.org/)
* [Learn You a Haskell](http://learnyouahaskell.com/chapters)
* [Haskell: The Craft of Functional Programming](http://www.haskellcraft.com/craft3e/Home.html)

**If/Switch/Pattern-Matching Statements**

**List as a fundamental data structure to solve problems along with list operations**

**Anonymous Functions/Functors**

**High Order Functions**

**Function Composition**

**Recursion**

**Mapping**

Algebraric datataypes are types that combine other types either as records ('products') `data Pair = Pair Int Double`
or as variants ('sums') `data Bool = False | True`

**Function currying**
Lambda Calculus has captured 2 aspects of a function:
* A mathematical object (set ordered pairs from domain and range)(map from independent variable to dependent variable)
* An abstract black box machine that takes an input and produces an output

Lambda Calculus Conversion rules:
* Computing in lambda calculus is performed using 3 conversion rules (alpha, beta, eta)
* The conversion allows you to replace an expression another "equal" one
* Some conversions simplify an expression, these are called reduction

The 3 conversion rules:
* alpha conversion: Changing name of function parameters consistently `(\x -> x + 1)` ==alpha conversion==> `(\y -> y + 1)`
* Beta conversion: Replace bound variables with instance of argument `(\x -> 2 * x + g x) 42` ==beta conversion==> `(\x -> 2 * 42 + g 42)`
* Eta conversion: A function is equivalent to lambda expression that takes argument and apply function to argument
  `(\x -> f x)`
  `(\x -> (*3) x) 50` ==eta conversion==> `(*3) 50`
  
**Monads**
(">>=") means "binds to"
3 monad laws:
* Right unit law: m >>= return = m
* Left unit law: return x >>= f = f x
* Associativity law: (m >>= f) >>= g = m >>= (\x -> f x >>= g)
* A monad is a mechanism for combining computations. It is a typeclass providing bind and return operations
* To be a monadic type, the implementation of bind and return must conform to the three monad laws

# Step by step

I think a good place to start is to imagine that you intend to write a library for a specific purpose or domain. You want to first identify a data type in there and establish a rule.
