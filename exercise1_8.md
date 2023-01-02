# Exercise 1.8

```scheme
(define (cube-root x)
  (cube-root-iter 1.0 x))

(define (improve guess x)
  (/ (+ (/ x (* guess guess)) (* 2 y)) 3)

(define (cube-root-iter guess x)
  (if (good-enough? guess x)
      guess
      (cube-root-iter (improve guess x)
                 x)))

(define (good-enough? guess x)
  (< (abs (- (improve guess x) guess) (/ guess 1000))
```
