## Exercise 1.6

```scheme
(define (new-if predicate then-clause else-clause)
  (cond (predicate then-clause)
        (else else-clause)))

(define (sqrt-iter guess x)
  (new-if (good-enough? guess x)
          guess
          (sqrt-iter (improve guess x)
                     x))
```

By turning `new-if` into a procedure of its own, we make it so that, in accordance with applicative order rules, the operands supplied to `new-if` are evaluated before the procedure body is entered.  As such, `(sqrt-iter (improve guess x) x)` (and thus `(improve guess x)`) will be recursively called in an infinite loop.  
