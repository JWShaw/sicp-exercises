# Exercise 1.5

```scheme
(define (p) (p))

(define (test x y)
  (if (= x 0)
     0
     y))
```

When Ben evaluates the expression `(test 0 (p))`, the result will be different depending on whether the interpreter uses applicative-order or normal-order application. If the interpreter uses applicative order application, as does the actual Scheme interpreter, the program will never terminate.  The application rule will attempt to evaluate both `0` and `p`--however, since `p` is defined recursively as itself, the evaluation of `p` will never complete.

In normal-order application, by contrast, the operands will not be evaluated until their values are needed.  In this case, the special form `if` short-circuits the program after seeing that `x` evaluates to `0`, so the program will output `0` without ever needing to evaluate `(p)`.
