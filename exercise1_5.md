# Exercise 1.5

```scheme
(define (p) (p))

(define (test x y)
  (if (= x 0)
     0
     y))
```

When Ben evaluates the expression `(test 0 (p))`, the result will be different depending on whether the interpreter uses applicative-order or normal-order application. If the interpreter uses applicative order application, as does the actual Scheme interpreter, the result will be `0`: the two arguments to `test` will evaluate to `0` and `p` respectively.  Because the predicate of the `if` special form is satisfied, it returns the value `0` without attempting to further evaluate `p`.

In normal-order application, the program will never terminate.  The expression `(test 0 (p))` will attempt to reduce `(p)` to its most primitive form, but since `p` is recursively defined as itself, this will never complete.
