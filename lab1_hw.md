---
title: "Lab 1 Homework"
author: "What is Your Name?"
date: "Winter 2020"
output:
  html_document:
    keep_md: yes
    theme: spacelab
---

## Instructions
Answer the following questions and complete the exercises in RMarkdown. Please embed all of your code, keep track of your versions using git, and push your final work to our [GitHub repository](https://github.com/FRS417-DataScienceBiologists). I will randomly select a few examples of student work at the start of each session to use as examples so be sure that your code is working to the best of your ability.  

1. Navigate to the R console and calculate the following expressions.  
  + 5 - 3 * 2  
  + 8 / 2 ** 2  
  
2. Did any of the results in #1 surprise you? Write two programs that calculate each expression such that the result for the first example is 4 and the second example is 16.  

The computer's usage of PEMDAS surprised me. 

```r
(5-3)*2
```

```
## [1] 4
```

```r
(8/2)**2
```

```
## [1] 16
```

3. Make a new object `pi` as 3.14159265359.  


```r
pi = 3.14159265359
```

4. Is `pi` an integer or numeric? Why? Show your code.  
numeric

```r
is.numeric(pi)
```

```
## [1] TRUE
```


5. You have decided to use your new analytical powers in R to become a professional gambler. Here are your winnings and losses this week. Note that you don't gamble on the weekends!  

```r
blackjack <- c(140, -20, 70, -120, 240, NA, NA)
roulette <- c(60, 50, 120, -300, 10, NA, NA)
```

a. Build a new vector called `days` for the days of the week. 

```r
days <- c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday")
```

We will use `days` to name the elements in the poker and roulette vectors.

```r
names(blackjack) <- days
names(roulette) <- days
```

b. Calculate how much you won or lost in blackjack over the week.  

```r
blackjacksum <- sum(blackjack[1:7], NA, na.rm = TRUE)
blackjacksum
```

```
## [1] 310
```

c. What is your interpretation of this result? What do you need to do to address the problem? Recalculate how much you won or lost in blackjack over the week.  

I won $310 in blackjack this week in total. The problem I initially encountered was being unable to add the money I made because of the days I did not gain any winnings.

d. Calculate how much you won or lost in roulette over the week.  

```r
roulettesum <- sum(roulette[1:7], NA, na.rm=TRUE)
roulettesum
```

```
## [1] -60
```


e. Build a `total_week` vector to show how much you lost or won on each day over the week. Which days seem lucky or unlucky for you?

```r
total_week <- c(blackjack[1]+roulette[1], blackjack[2]+roulette[2], blackjack[3]+roulette[3], blackjack[4]+roulette[4], blackjack[5]+roulette[5], blackjack[6]+roulette[6], blackjack[7]+roulette[7])

names(total_week) <- days

total_week
```

```
##    Sunday    Monday   Tuesday Wednesday  Thursday    Friday  Saturday 
##       200        30       190      -420       250        NA        NA
```
Wednesday seemed unlucky for me because I lost $420. Thursday and Sunday are lucky for me because I made a profit of $250 and $200. 

f. Should you stick to blackjack or roulette? Write a program that verifies this below. 
I should stick to blackjack because I made a net profit of $310, but lost $60 with roulette. 

```r
if (blackjacksum > roulettesum) {
  print("Stick to blackjack.")
}else {
    print("Stick to roulette.")
}
```

```
## [1] "Stick to blackjack."
```


## Push your final code to [GitHub](https://github.com/FRS417-DataScienceBiologists)
