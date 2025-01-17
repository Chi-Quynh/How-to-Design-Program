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

;Fixed code after comparing solution
;output: cent

(define (sum-coins pennies nickel dime quarter)
  (+ pennies (* nickel 5) (* dime 10) (* quarter 25)))


;test the function, compare it with real result
( sum-coins 1 0 0 0 )
( sum-coins 0 1 0 0 )
( sum-coins 0 0 1 0 )
( sum-coins 0 0 0 1 )
( sum-coins 1 1 1 1 )
## Exc 2.3.3

2.4 Errors
## Exc 2.4.1
(+(10) 20)
function call: expected a function after the open parenthesis, but found a number
(+ +)
function call: expected a function after the open parenthesis, but found a number
(10 + 20)
function call: expected a function after the open parenthesis, but found a number

## Exc 2.4.2
; the parameter cannot be number
(define (f x)
  (+ x 10 ))
; the expression + x 10 did not have an opening (
(define (g x )
  (+ x 10))
; the primitive function must follow the open parenthesis
(define( h x))
  (+ x 10 ))

## Exc 2.4.3
(+ 5 (/ 1 0))

(sin 10 20)

(somef 10)

; this function is not defined. It's true bc the open parenthesis expect either an operation or name of the primitive function

## Exc 2.4.4
( define (somef x)
  (sin x x ))

(somef 10 20)
; Expected 1 arguement for the function parameter
(somef 10)
; sin expression expected only 1 arguement

# Lesson:
- Breaking problems down into input, out put and rules
