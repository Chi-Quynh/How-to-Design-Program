## Lesson:
- Learned to understand how Boolean condition works
- Ehanced my ability to simplify problem
- Learned the importance of abstraction 
## 4.1.1
```
1. (and ( T ) ( T ) ) => True
2. (or ( T ) ( F ) ) => True 
3. ( not (F ) ) => True
```
## 4.1.2
```
1. 
(a) => T
(b) => F
(c) => T
2. 
(a)(and (F)(T)) => F
(b)(and (T)(F)) => F
(c)(and (T)(T)) => T
3. 
(a)(= (16)4) => F
(b)(= (4)2) => F
(c)(= (49/4)7/2) => F
```
## 4.2.1
```
1. 
(and ( > x 3 )( <= x 7 ))
2.
(and ( >= x 3 ) ( <= x 7 ))
3. 
(and ( >= x 3 )( < x 9 ))
4.
(or ( and ( > x 1 ) ( < x 3)) ( and ( > x 9)(< x 11)))
5.
(or ( < x 1)( > x 3))
```
## 4.2.2
```
<img>
1. (in-interval-1? -2) T
2. (in-interval-2? -2) T
3. (in-interval-3? -2) T

Show the important steps. Use the pi
```

## 4.2.3
```
;;number->bool
;;1 check of the int is the solution
(define (int-interval-1 int)
  (= ( * 4 ( + int 2))62))

;;number->bool
;;2 check of the int is the solution
(define (int-interval-2 int)
  (=(* 2 (* int int)) 102))

;;number->bool
;;3 check of the int is the solution
(define (int-interval-3 n)
  (=( + (* 4 (* n n)) ( * 6 n ) 2) 462))

;;test
(int-interval-1 10) ;;should be F
(int-interval-1 12) ;;should be F
(int-interval-1 14) ;;should be F

(int-interval-2 10) ;;should be F
(int-interval-2 12) ;;should be F
(int-interval-2 14) ;;should be F

(int-interval-3 10) ;;should be T
(int-interval-3 12) ;;should be F
(int-interval-3 14) ;;should be F
```

## 4.2.4
```
;;## Exc 2.2.1
(define (Fahrenheit->Celsius fah)
  (/(- fah 32)(/ 9 5 )))
( = (Fahrenheit->Celsius 10) (/ 110 -9)) 


;;## Exc 2.2.2
(define (dollar->euro dollar)
  (* dollar 0.97))
( = (dollar->euro 1) 0.97)

;;## Exc 2.2.3
(define (triangle base height)
  (/(* base height) 2))
(=(triangle 10 5)25)

;;## Exc 2.2.4
(define (convert3 one two three)
  (+ one (* two 10)(* three 100)))
(=(convert3 1 2 3)321)
```
## 4.3.1
```
(cond
  [(< n 10) 20]
  [(and (> n 20) (<= n 30)) 3.0 ]
  [else 1])

;;is not legal because there is only one parameter , it's missing a parameter of type answer )

(cond [(< n 10) 20]
      [* 10 n]
      [else 555]) ;     

;;1. The 2nd condition does not have parentes to close off the function. 2) The condition does not have 2nd arguement of type answer
```
## 4.3.2
```
(a) 500=> 0.040
(b) 2800 => 0.045
(c) 15000 => 0.060
```
## 4.3.3
```
(a) 500 => 40
(b) 2800 => 121
(c) 15000 => 495
```
## 4.4.1
```
;;int -> int
;;data analysis: 1000 < 4% , 5000 4.5%, 5000 up 5%
;;ex: 1000 -> 40
;;ex: -10 -> 0 / error
;;ex: 3000 -> 135
(define (interest deposit )
  (cond
    [(<= deposit 0) 0]
    [(<= deposit 1000) ( * deposit 0.04)]
    [(<= deposit 5000) ( * deposit 0.045)]
    [ else ( * deposit 0.05)])
  )

(interest 500) ;;20
(interest 2000) ;;90
(interest 10000) ;;500
```
## 4.4.2
```
;;int gross pay ->int tax
;;get gross pay returns tax owned
(define ( tax gross-pay)
  (cond
    [(<= gross-pay 240) 0]
    [(<= gross-pay 480) (* gross-pay 0.15)]
    [ else ( * gross-pay 0.28)]
    )
  )

;;net pay
;;int-> int
;;get netpay from gross - tax
(define (net-pay hours)
  (- (gross-pay hours) ( tax (gross-pay hours)))
  )

;;int -> int
;;use hours worked to get gross pay
(define (gross-pay hours)
  (* 12 hours ))


(tax 10)
(tax 240)
(tax 300)
(tax 480)
(tax 500)

(net-pay 1 )
(net-pay 40)
```
## 4.4.3
```
(define (pay-back money )
  (cond
    [ ( <= money 500 ) ( first500 money)]
    [ ( and ( > money 500 ) ( <= money 1500))
      ( + (first500 500) ( first1000 ( - money 500))) ]
    [ (and ( > money 1500) ( <= money 2500))
      (+ (first500 500) ( first1000 1000) ( second1000 ( - money 1500) ))]
    [else (+ (first500 500) ( first1000 1000) (second1000 1000) (over ( - money 2500 )) )]
    )
  )


(define (first500 money)
  ( * 0.25 1/100 money ))
(define ( first1000 money)
  ( * 0.5 1/100 money))
(define ( second1000 money )
  ( * 0.75 1/100 money ))
(define ( over money )
  ( * 1.0 1/100 money ))


( pay-back 400)
( pay-back 1400)
( pay-back 2000)
( pay-back 2600)
```
## 4.4.4
```
;;number number number -> number
;;computes solutions of a quadratic equation
;;ex
;;x^2 + 2x + 1 = 0 has 1 solution
(define (how-many a b c )
  (cond
    [( > (discriminant a b c ) 0) 2]
    [( = (discriminant a b c ) 0) 1]
    [( < (discriminant a b c ) 0) 0]
    ))

;; number number number -> number
;; define the value of the discriminator
(define (discriminant a b c )
  ( - (* b b) ( * a c 4 ))
  )
 ;;if the equation is not proper, it would not have a =/= 0, therefore it wont be guaranteed quadratic -> bx + c = 0 -> cannot use how-many as indicator of solution anymore

```

