# Exercise 1.12

It is helpful to visualize the triangle in a grid format:

```
1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
```

A recursive procedure to compute a given number in the triangle is the following:

```scheme
(define (pascal row col)
  (cond ((= col 1) 1)
        ((= col row) 1)
        (else (+ (pascal (- row 1) (- col 1)) (pascal (- row 1) col)))))
```
