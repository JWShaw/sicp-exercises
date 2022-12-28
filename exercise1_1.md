# Exercise 1.1

```scheme
10

;Value: 10
```

```scheme
(+ 5 3 4)

;Value: 12
```

```scheme
(- 9 1)

;Value: 8
```

```scheme
(/ 6 2)

;Value: 3
```

```scheme
(+ (* 2 4) (- 4 6))

;Value: 6
```

```scheme
(define a 3)

;Value: a
```

```scheme
(define b (+ a 1))

;Value: b
```

```scheme
(+ a b (* a b))

;Value: 19
```

```scheme
(if (and (> b a) (< b (* a b)))
    b
    a)

;Value: 4
```

```scheme
(cond ((= a 4) 6)
      ((= b 4) (+ 6 7 a))
      (else 25))

;Value: 16
```

```scheme
(+ 2 (if (> b a) b a))

;Value: 6
```

```scheme
(* (cond ((> a b) a)
         ((< a b) b)
         (else -1))
   (+ a 1))

;Value: 16
```
