# ASYMPTOTIC NOTATION

## Upper Bound
We can say that a linear function of n is an upper bound in all cases, however,
and we have a notation for that: O(n). When we speak this notation, we say
“big-oh of n” or just “oh of n.” A function f(n) is O(g(n)) if, once n becomes
sufficiently large, f(n) is bounded from above by some constant times g(n)
We use O-notation to indicate that a running time is never worse than a
constant times some function of n

## Lower Bound
Never better than
we use Ω-notation, which mirrors O-notation: a function f(n) is Ω(g(n)) if,
once n becomes sufficiently large, f (n) is bounded from below by some constant
times g(n). We say that “f (n) is big-omega of g(n)” or just
“f (n) is omega of g(n),” and we can write f (n) = Ω(g(n))

## Upper and Lower Bounds
Since O-notation gives an upper bound, Ω-notation gives a lower bound, and
Θ-notation gives both upper and lower bounds, we can conclude that a
function f (n) is Θ(g(n)) if and only if f(n) is both O(g(n)) and Ω(g(n))
