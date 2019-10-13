# Quiz 1 
### Daniel Borders (dborder1)

#### Question 1
a) 15932 w/ sepsis, 3507 w/ septic shock. 

Sensitivity = 88% = 
$\frac{tp}{tp+fn}$

Specificity = 84% = 
$\frac{tn}{tn+fp}$

PPV = 58% = 
$\frac{tp}{tp+fp}$

Simplifying the above equations:

$.88fn -.12tp = 0$

$.84fp - .16tn = 0$

$-.42tp + .58fp = 0$

$tp + fn = 3507$

$tp + tn + fp + fn = 15932$

solving the above system of equations, we get the following:
tp = 3086, fn = 421, tn = 10437, fp = 1988

We can now look at the prevelance of septic shock in adults:

Prev = 
$\frac{tp+fn}{tp+tn+fp+fn}$
=.22

Convert to children:

$tp+fn=(.22/3)(tp+tn+fp+fn)$ 

Note: these variables are for children because we changed the equation.
Assume that the sensitivity and specificity are the same for adults as kids.

$(1-\frac{.22}{3})(tp+fn)=\frac{.22}{3}(tn+fp)$ 

plug in for fn and tn:

$(1-\frac{.22}{3})(tp+\frac{.12}{.88}tp) = \frac{.22}{3}(\frac{.84}{.16}fp + fp)$

$\frac{(1-\frac{.22}{3})(1+\frac{.12}{.88})}{\frac{.22}{3}(\frac{.84}{.16} + 1)}tp=fp$

add tp to each side:

$(1+\frac{(1-\frac{.22}{3})(1+\frac{.12}{.88})}{\frac{.22}{3}(\frac{.84}{.16} + 1)})tp=fp+tp$

$\frac{tp}{tp+fp}=\frac{1}{1+\frac{(1-\frac{.22}{3})(1+\frac{.12}{.88})}{\frac{.22}{3}(\frac{.84}{.16} + 1)}}=.273$

PPV = 27.3%

b) Find NPV:
Use the same method above, except substitute in for fp and tp:

$ NPV = \frac{tn}{tn+fn} = \frac{1}{1+\frac{\frac{.22}{3}(\frac{.16}{.84} + 1)}{(1-\frac{.22}{3})(1+\frac{.88}{.12})}}=.989$

NPV = 98.9%

c) 3 factors diffrent from kids to adults:

    1) Heart rates of kids are higher than that of adults. For ex, adults are usually in the range 60-100 bpm wheras kids are in the range 60-220. The model would need to be retrained with some kid data so it can more accuratly represent this new range. A normalizing method could also be used to put the heart rate into an adult range
    2) Lactate levels are diffrent in kids vs adults. Loking at this paper https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1332314/, we see that puberty effects how lactate is held in the blood, so the model could also need to be adjusted for this. 
    3) generally blood pressure is lower in kids than adults, so the blood pressure should also be adjusted or the model retrained on kids data. 
    
#### Question 2
Take the derivative of the poisson with respect to lambda

$\frac{d}{d\lambda} (\frac{(\lambda \delta t)^n}{n!}e^{-\lambda \delta t})=0$

recall 
$\delta t = 1$ 

so the above simplifes to:

$\frac{1}{n!} \frac{d}{d\lambda}(\lambda^n e^{-\lambda})=0$

$n\lambda^{n-1} e^{-\lambda} - \lambda^n e^{-\lambda} = 0$

we can get rid of the 
$e^{-\lambda}$ bc its greater than zero

$n\lambda^{n-1} - \lambda^n = 0$

$\lambda^{n-1}(n - \lambda) = 0$

$\lambda^\star = n $