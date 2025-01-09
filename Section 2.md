## Exc 2.1.1
(sqrt 4)
(sin pi)
(max 2 4)
## Exc 2.1.2
(sqrt 4)
(sqrt 2)
(sqrt -1)
(tan 30)

## Exc 2.2.1
(define (Fahrenheit->Celsius fah)
  (/(- fah 32)(/ 9 5 )))
(convert-gui Fahrenheit->Celsius)

## Exc 2.2.2
(define (dollar->euro dollar)
  (* dollar 0.97))
(dollar->euro 1)

## Exc 2.2.3
(define (triangle base height)
  (/(* base height) 2))
(triangle 10 5)

## Exc 2.2.4
(define (convert3 one two three)
  (+ one (* two 10)(* three 100)))
(convert3 1 2 3)

## Exc 2.3.1
(define (tax income)
  (* 0.15 income))
(define (netpay wage)
  (- wage (tax wage)))
(define (wage hour)
  (* hour 12))
(wage 100)
(tax (wage 100))
(netpay(wage 100))

## Exc 2.3.2
;output: cent

(define (sum-coins pennies nickels dimes quarters)
  (+ pennies (nickel nickels) (dime dimes) (quarter quarters)))
;output cent of nickel
(define (nickel amount)
  (* 5 amount))
(define (dime amount)
  (* 10 amount))
(define (quarter amount)
  (* 25 amount))

;test the function, compare it with real result
( sum-coins 1 1 1 1 )
(+ 1 5 10 25)

## Exc 2.3.3


Lesson:
- Breaking problems down into input, out put and rules
