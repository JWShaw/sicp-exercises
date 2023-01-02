# Exercise 1.7

```scheme
(define (good-enough? guess x)
  (< (abs (- (square guess) x)) 0.001))
```

For small radicands, the constant tolerance will be close in magnitude to the radicands themselves, leading to a poor estimate of the radicand.

For example, if one were to try to find the square root of 0.001 itself, `good-enough` returns true for `0.001 +/- 0.001`: clearly an unacceptably large interval.

For large radicands, the floating-point precision of the guess may be greater than 0.001, causing `sqrt-iter` to repeat infinitely.

The following program will iterate until the diffrence between `guess` and `improve guess x` is less than one thousandth of `guess`.

```scheme
(define (sqrt x)
  (sqrt-iter 1.0 x))

(define (improve guess x)
  (average guess (/ x guess)))

(define (average x y)
  (/ (+ x y) 2))

(define (sqrt-iter guess x)
  (if (new-good-enough? guess x)
      guess
      (sqrt-iter (improve guess x)
                 x)))

(define (new-good-enough? guess x)
  (< (abs (- (improve guess x) guess) (/ guess 1000))
```
