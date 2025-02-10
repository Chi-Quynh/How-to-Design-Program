## 5.1.1
```
;;reply: sumbol->sumbol
;;to determine a reply for the greeting
(define (reply s )
  (cond
    [(symbol=? s 'HowAreYou?) 'ImFine]
    [(symbol=? s 'HowOldAreYou?) 'Im16]
    [(symbol=? s 'HowDoYouDo?) 'Imgood ]
    [(symbol=? s 'HowYourHealth?) 'ImHealthy]))

(reply 'HowAreYou?)
(reply 'HowOldAreYou?)
(reply 'HowDoYouDo?)
(reply 'HowYourHealth?)
```
