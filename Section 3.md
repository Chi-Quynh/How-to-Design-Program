## 3.3.1
```
(define INCH-CM 2.54)
(define FOOT-IN 12)
(define YARD-FOOT 3)
(define ROD-YARD 5.5)
(define FUR-ROD 40)
(define MILE-FUR 8)

;;type:number->number
;;converts inches into cm
;;example: (inches->cm 1) = 2.54
;;(inches->cm 2) = 5.08
;;(inches->cm 3) = 7.62
(define (inch->cm inch )
  (* inch INCH-CM ))
;;type:number->number
;;converts feet into inches
;;example:(feet->inches 1)= 12
;;(feet->inches 2)= 24
;;(feet->inches 3)= 36
(define (foot->inch foot)
  (* foot FOOT-IN))
;;type:number->number
;;converts yards into feet
;;example: (yards->feet 1)= 3
;;(yards->feet 2)= 6
;;(yards->feet 3)= 9
(define (yard->foot yard)
  (* yard YARD-FOOT))
;;type:number->number
;;converts rods into yards
;;example: (rods->yards 1) = 5.5
;;(rods->yards 2) = 11
(define (rod->yard rod)
  (* rod ROD-YARD))
;;type:number->number
;;converts furlong into rods
;;example: (furlong->rods 1) = 40
;;(furlong->rods 2) = 80
;;(furlong->rods 3) = 120
(define (furlong->rod furlong)
  (* furlong FUR-ROD))
;;type:number->number
;;converts miles into furlong
;;example: (miles->furlong 1 ) = 8
;;(miles->furlong 2 ) = 16
;;(miles->furlong 3 ) = 24
(define (mile->furlong mile)
  (* mile MILE-FUR))

;;type:number->number
;;converts feet to cm
;;example: (feet->cm 1 ) = 30.48
;;example: (feet->cm 2 ) = 60.96
;;example: (feet->cm 3 ) = 91.44
(define (feet->cm feet)
  ( inch->cm (foot->inch feet) ))

;;type:number->number
;;converts yard to cm
;;example: (yard->cm 1 ) = 
( define (yard->cm yard)
   (inch->cm
    (foot->inch
     ( yard->foot yard))))

;;type:number->number
;;converts rod to inch
;;example: (rod->inch 1 ) =
(define (rod->inch rod)
  (inch->cm
   (foot->inch
    (yard->foot
     (rod->yard rod)))))

;;type:number->number
;;converts mile->foot
;;example: (mile->foot 1 ) =
(define (mile->foot mile)
  (yard->foot
   (rod->yard
    (furlong->rod
     (mile->furlong mile)))))
```
## 3.3.2
```
;;type: number->number
;;input base and height-> volume of cylinder
(define (volume-cylinder radius height)
  (*(area-circle radius) height))

;;area-circle: number->number
;;to get area of the circle
  (define (area-circle radius)
    (* pi radius radius))

(area-circle 1)
(volume-cylinder 3 2)
( * 18 pi) ;;should be the same as volume-cylinder

```
## 3.3.3
```
;;area-cylinder: number->number
;;to get the surface area of the cylinder
(define (area-cylinder radius height)
  (+ (cylinder-base radius) (cylinder-base radius) (cylinder-height radius height)))

;;cylinder-base: number->number
;;to get the surface area of the cylinder base
(define (cylinder-base radius)
  (* radius radius pi))

;;cylinder-height: number->number
;;to get the surface area of the cylinder height
(define (cylinder-height radius height )
  (*( base-perimeter radius) height))
;;base-perimeter: number->number
;;to get perimeter of base
(define (base-perimeter radius)
  (* 2 pi radius ))

(cylinder-base 3)
(area-cylinder 2 3)
(area-cylinder 3 4)
```
```
