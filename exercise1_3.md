# Exercise 1.3

```scheme
(define (sum-of-squares a b)
  (+ (* a a) (* b b)))

(define (f x y z)
  (cond ((and (>= x z) (>= y z)) (sum-of-squares x y))
        ((and (>= x y) (>= z y)) (sum-of-squares x z))
        (else (sum-of-squares y z))))
```
