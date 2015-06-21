---
title       : Body Mass Index (BMI) Calculator
subtitle    : Developing Data Products Project
author      : Vouris Angelos
job         : Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : standalone # {standalone, draft}
knit        : slidify::knit2slides

--- .class #id 

## What is BMI?

The Body Mass Index (BMI) is a measure of body fat based on height and weight that applies to adult men and women. Regarding the BMI measure, the World Health Organization (WHO) proposes the following classification:
* BMI <18.5 : Underweight
* BMI [18.5-24.9] : Normal weight
* BMI [25-29.9] : Overweight
* BMI >=30 : Obesity

--- .class #id

## How is it calculated?

There is a formula for calculating the BMI measure. The formula is the following:

BMI = weight(kg) / height$^2$ (metres)

Thus for the next example, the BMI will be:

```r
weight = 75
height = 1.8
BMI <- weight/height^2
BMI
```

```r
## [1] 23.15
```

--- .class #id


## Diagnostic

The function use for calculating the diagnostic is the following:

```r
diagnostic_f <- function(weight, height) {
    BMI_value <- weight/(height^2)
    ifelse(BMI_value < 18.5, "underweight", ifelse(BMI_value < 25, "normal weight", 
        ifelse(BMI_value < 30, "overweight", "obesity")))
}
```

For our example (weight=75 kg and height=1.80 m) the diagnostic would be:


```r
diagnostic_f(75, 1.8)
```


```r
## [1] "normal weight"
```

--- .class #id

## Conclusion

The BMI is a relatively easy, cheap and non-invasive method for establishing weight status, and for most people, it correlates reasonably well with their level of body fat.

However, BMI is only a proxy for body fatness. other factors such as fitness, ethnic origin and puberty can alter the relation between BMI and body fatness and must be taken into consideration.
