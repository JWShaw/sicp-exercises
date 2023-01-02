# Exercise 1.11

$f(n) = n$ if $n < 3$ and $f(n) = f(n-1) + 2f(n-2) + 3f(n-3)$ if $n \geq 3$.

A recursive procedure for calculating $f(n)$:

```scheme
(define (f-recursive n)
  (if (< n 3)
      n
      (+ (f-recursive (- n 1)) 
         (* 2 (f-recursive (- n 2))) 
         (* 3 (f-recursive (- n 3))))))
```

An iterative procedure for computing the same:

```scheme
(define (f-iterative n)
  (define (f-iter x y z count)
    (cond ((< n 3) n)
          ((= count n) x)
          (else (f-iter (+ x (* 2 y) (* 3 z)) x y (+ count 1)))))
  (f-iter 2 1 0 2))
```
