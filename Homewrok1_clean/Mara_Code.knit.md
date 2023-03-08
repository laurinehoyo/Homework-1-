---
title: "HW1_Clean"
author: "Mara"
date: "08/03/2023"
output: html_document
---
---
title: "HW"
author: "Mara"
date: "3/1/2023"
output: html_document
---
## HOMEWORK 1 

## R Markdown Syntax

## Picture
![High Kick during a Muay Thai Fight](https://cdn.onefc.com/wp-content/uploads/2020/01/Jamal-Yusupov-defeats-Yodsanklai-at-ONE-AGE-OF-DRAGONS-DA-5280.jpg)

## Quote

> "the realm of birth and death" 

## Emojis

Look at my nice emojis: 
💩
🎈
❤️

## Giphy 
Here is a big Giphy: 

![Is that a jojo reference?](https://media.giphy.com/media/br8dqCCmLppvO/giphy.gif) 

and a smaller one... <img src='https://media.giphy.com/media/VRKheDy4DkBMrQm66p/giphy.gif' width='200' height='200' />

## Tables and Columns
Experiment with the Rmd Code below and test output.

+-------------------------------+---------------+
| Classes                       | Time          |
+===============================+===============+
| International                 | 4 hours       | 
| Macroeconomics                |               | 
+-------------------------------+---------------+
| Microéconomie II              | 2 hours       | 
|                               |               | 
+-------------------------------+---------------+
| Eco contemporaine             | 4 hours       | 
| Dans une perspective          |               |
| Historique                    |               |
+-------------------------------+---------------+
| Création d'entreprise et      | 2 hours       | 
| système d'innovation          |               | 
+-------------------------------+---------------+
| Intro to Data Science         | 4 hours       |
|                               |               |
+-------------------------------+---------------+
| Intro à la fiscalité          | 2 hours       | 
|                               |               |
+-------------------------------+---------------+

## Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/zaTg2s4hOU8" title="YouTube video player" frameborder="0" data-external="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## R Markdown Syntax
Show an example where the chunk option cache = T leads to a misleading answer. This example must be different from the one presented in the textbook.


```r
a = 20
```


```r
(m = a/2)
```

```
## [1] 10
```

here, if we change the value of a, the output remains the cached initial a divided by 2.

```
set.seed(100)
samples <- runif(n=100, min=0, max=1)
x <- samples
print(x)
```

```
theoreticalmean <- ((0+1)/2)
theoreticalvar <- ((1-0)/12)

mean(x)
median(x)
var(x)
````

the observed values are slighty off. 
The mean and median are relatively close to the theoretical ones, which makes sense because we generate a large number of samples between 0 and 1, which correlates with the law of large numbers.
The variance is slightly off, which makes sense because we do not controll where the samples are located between 0 and 1, so we might get a larger variance.

```
hist(x, xlab = "uniformly dist. 100 random samples")
```
## Equations

Here we have centered equations

$$\frac{\partial\ l }{\partial\beta }= \sigma _{}^{-2}
\sum_{}^{} \mathbf{X_{i}^{'}} \mathbf{V_{i}^{-1}}(\mathbf{y_{i}-X_{i}\beta })$$


$$\frac{\partial l}{\partial \sigma ^2}=-\frac{1}{2}N_T\sigma ^{-2}+\frac{1}{2}\sigma^{-4}\mathbf{\sum (y_i-X_i\beta)'V_i^{-1}(y_i-X_i\beta)}$$

$$\frac{\partial l}{\partial \mathbf{D}}=-\frac{1}{2} \mathbf{\sum \mathbf{ [Z_\textit{i}^{'}V_\textit{i}^{-1}Z_\textit{i}-\sigma ^{-2}Z_\textit{i}^{'}V_\textit{i}^{-1}(y_\textit{i}-X_\textit{i}\beta)(y_\textit{i}-X_\textit{i}\beta)^{'}V_\textit{i}^{-1}Z_\textit{i}]}}$$
And a formula that is embedded in the text: 
$\mathbf{A}\equiv [a_{i,j}]_{i,j=1,...,p}$ - what a nice formula!

## Quote in Red
<span style="color: red;">“Mieux que l’amour, l’argent, la gloire, donnez moi la vérité.”, Henri David Thoreau</span>

## A Button and a Box!

<button data-toggle="collapse" data-target="#demo">
Surprise!
</button>
<div id="demo" class="collapse">
<p> 6 is the grade we want ;) </p>

</div>

<div style="background-color: #FFCCCC; padding: 10px;">
**Very Important !** 🎈
</div>


## EXERCISE 2 - FINANCIAL ANALYSIS
__Questions 1 and 2__ 




```r
mydates <- c("01/01/2022","01/01/2023")

mydates2 <- as.Date(mydates, format = "%m/%d/%Y")
mydates2
```

```
## [1] "2022-01-01" "2023-01-01"
```

```r
getSymbols("AAPL", from = min(mydates2), to = max(mydates2))
```

```
## [1] "AAPL"
```

```r
getSymbols("CSCO", from = min(mydates2), to = max(mydates2))
```

```
## [1] "CSCO"
```

```r
getSymbols("INTC", from = min(mydates2), to = max(mydates2))
```

```
## [1] "INTC"
```

```r
getSymbols("HD", from = min(mydates2), to = max(mydates2))
```

```
## [1] "HD"
```

```r
getSymbols("GOOG", from = min(mydates2), to = max(mydates2))
```

```
## [1] "GOOG"
```

```r
getSymbols("JPM", from = min(mydates2), to = max(mydates2))
```

```
## [1] "JPM"
```

__Question3:__

```r
plot(AAPL$AAPL.Close)
```

<img src="Mara_Code_files/figure-html/unnamed-chunk-4-1.png" width="672" />

```r
plot(CSCO$CSCO.Close)
```

<img src="Mara_Code_files/figure-html/unnamed-chunk-4-2.png" width="672" />


__Question 4__

```r
mydatesnew <- c("10/01/2022","01/01/2023")
mydates3 <- as.Date(mydatesnew, format = "%m/%d/%Y")
mydates3
```

```
## [1] "2022-10-01" "2023-01-01"
```

```r
getSymbols("GOOG", from = min(mydates3), to = max(mydates3))
```

```
## [1] "GOOG"
```

```r
getSymbols("JPM", from = min(mydates3), to = max(mydates3))
```

```
## [1] "JPM"
```

```r
candleChart(GOOG, theme = 'white', type = 'candles')
```

<img src="Mara_Code_files/figure-html/unnamed-chunk-5-1.png" width="672" />

```r
candleChart(JPM, theme = 'white', type = 'candles')
```

<img src="Mara_Code_files/figure-html/unnamed-chunk-5-2.png" width="672" />

__Question 5__

```r
mean(AAPL$AAPL.Close)
```

```
## [1] 154.8351
```

```r
mean(GOOG$GOOG.Close)
```

```
## [1] 95.43667
```

```r
mean(JPM$JPM.Close)
```

```
## [1] 126.7063
```

```r
mean(CSCO$CSCO.Close)
```

```
## [1] 48.53781
```

```r
mean(INTC$INTC.Close)
```

```
## [1] 38.5945
```

```r
mean(HD$HD.Close)
```

```
## [1] 310.3346
```

```r
var(AAPL$AAPL.Close)
```

```
##            AAPL.Close
## AAPL.Close   170.4613
```

```r
var(GOOG$GOOG.Close)
```

```
##            GOOG.Close
## GOOG.Close   26.39921
```

```r
var(JPM$JPM.Close)
```

```
##           JPM.Close
## JPM.Close  96.17719
```

```r
var(CSCO$CSCO.Close)
```

```
##            CSCO.Close
## CSCO.Close   31.87959
```

```r
var(INTC$INTC.Close)
```

```
##            INTC.Close
## INTC.Close    80.1732
```

```r
var(HD$HD.Close)
```

```
##          HD.Close
## HD.Close 842.1292
```

__Question 6__

```r
mean(AAPL$AAPL.Close)
```

```
## [1] 154.8351
```

```r
mean(GOOG$GOOG.Close)
```

```
## [1] 95.43667
```

```r
mean(JPM$JPM.Close)
```

```
## [1] 126.7063
```

```r
mean(CSCO$CSCO.Close)
```

```
## [1] 48.53781
```

```r
mean(INTC$INTC.Close)
```

```
## [1] 38.5945
```

```r
mean(HD$HD.Close)
```

```
## [1] 310.3346
```

```r
sd(AAPL$AAPL.Close)
```

```
## [1] 13.05608
```

```r
sd(AAPL$AAPL.Close)
```

```
## [1] 13.05608
```

```r
sd(GOOG$GOOG.Close)
```

```
## [1] 5.138016
```

```r
sd(JPM$JPM.Close)
```

```
## [1] 9.806997
```

```r
sd(CSCO$CSCO.Close)
```

```
## [1] 5.646201
```

```r
sd(INTC$INTC.Close)
```

```
## [1] 8.953949
```

```r
sd(HD$HD.Close)
```

```
## [1] 29.01946
```

__Question 7__





```r
getSymbols("AAPL", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "AAPL"
```

```r
getSymbols("CSCO", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "CSCO"
```

```r
getSymbols("INTC", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "INTC"
```

```r
getSymbols("HD", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "HD"
```

```r
getSymbols("GOOG", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "GOOG"
```

```r
getSymbols("JPM", from = min(mydates2013), to = max(mydates2013))
```

```
## [1] "JPM"
```

```r
AAPL_returns <- na.omit(ClCl(AAPL))
GOOG_returns <- na.omit(ClCl(GOOG))
CSCO_returns <- na.omit(ClCl(CSCO))
INTC_returns <- na.omit(ClCl(INTC))
HD_returns <- na.omit(ClCl(HD))
JPM_returns <- na.omit(ClCl(JPM))
Rf <- 0.03/(252)
```

mean(AAPL_returns) 
mean(GOOG_returns)
mean(CSCO_returns)
mean(INTC_returns)
mean(HD_returns)
mean(JPM_returns)


sd(AAPL_returns) 
sd(GOOG_returns)
sd(CSCO_returns)
sd(INTC_returns)
sd(HD_returns)
sd(JPM_returns)

sharpe_ratioAAPL <- (mean(AAPL_returns) - Rf) / sd(AAPL_returns) * sqrt(252)
sharpe_ratioGOOG <- (mean(GOOG_returns) - Rf) / sd(GOOG_returns) * sqrt(252)
sharpe_ratioCSCO <- (mean(CSCO_returns) - Rf)/sd(CSCO_returns) * sqrt(252)
sharpe_ratioINTC <- (mean(INTC_returns) - Rf )/ sd(INTC_returns) * sqrt(252)
sharpe_ratioHD <- (mean(HD_returns)- Rf) / sd(HD_returns) * sqrt(252)
sharpe_ratioJPM <- (mean(JPM_returns)- Rf) / sd(JPM_returns) * sqrt(252)

cat("Sharpe Ratios for each stock:")
print(sharpe_ratioAAPL)
print(sharpe_ratioGOOG) 
print(sharpe_ratioCSCO) 
print(sharpe_ratioINTC)
print(sharpe_ratioHD)
print(sharpe_ratioJPM)


AAPL_return = quantmod::dailyReturn(AAPL)
CSCO_return = quantmod::dailyReturn(CSCO)
INTC_return = quantmod::dailyReturn(INTC)
HD_return = quantmod::dailyReturn(HD)
GOOG_return = quantmod::dailyReturn(GOOG)
JPM_return = quantmod::dailyReturn(JPM)

#excess return
AAPL_excess = AAPL_return - 0.03/252
CSCO_excess = CSCO_return - 0.03/252
INTC_excess = INTC_return - 0.03/252
GOOG_excess = GOOG_return - 0.03/252
JPM_excess = JPM_return - 0.03/252
HD_excess = HD_return - 0.03/252

#yearly sharpe ratio
AAPL_sharpe_yearly = mean(AAPL_excess) / sd(AAPL_excess) * sqrt(252)
CSCO_sharpe_yearly = mean(CSCO_excess) / sd(CSCO_excess) * sqrt(252)
INTC_sharpe_yearly = mean(INTC_excess) / sd(INTC_excess) * sqrt(252)
HD_sharpe_yearly = mean(HD_excess) / sd(HD_excess) * sqrt(252)
GOOG_sharpe_yearly = mean(GOOG_excess) / sd(GOOG_excess) * sqrt(252)
JPM_sharpe_yearly = mean(JPM_excess) / sd(JPM_excess) * sqrt(252)

yearly_shape = cbind(AAPL_sharpe_yearly, CSCO_sharpe_yearly, INTC_sharpe_yearly, HD_sharpe_yearly, JPM_sharpe_yearly)

colnames(yearly_shape) = c("AAPL", "CSCO", "INTC", "HD", "GOOG", "JPM")
yearly_shape


#estimation of mean (mu) and variance (Sigma)
mat_return = cbind(AAPL_return, CSCO_return, INTC_return, HD_return, GOOG_return, JPM_return)
colnames (mat_return) = c("AAPL", "CSCO", "INTC", "HD", "GOOG", "JPM")

mu = apply(mat_return, 2, mean)
Sigma = var(mat_return)
```


# equally weighted portfolio
equal_return = (AAPL_return + CSCO_return + INTC_return + HD_return + GOOG_return + JPM_return)/6

muequal = mean(equal_return)
varequal = var(equal_return)

#The individual variance of these 6 stocks are:
diag(Sigma)


