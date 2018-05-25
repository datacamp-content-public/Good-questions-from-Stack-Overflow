---
title: Template Chapter 1
description: >-
  This is a template chapter.


---
## Interlacing two vectors

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: 04476f35ac
```

[Credit: John, Ryan, Moody_Mudskipper][1]

[1]: https://stackoverflow.com/questions/50516915/interlacing-two-vectors/50517503

`@instructions`
From two vectors such as those:

    a <- c("a1", "a2", "a3")
    b <- c("b1", "b2", "b3")

Build the following one, alternating elements from `a` and `b` :

    c("a1","b1", "a2", "b2", "a3", "b3")

`@hint`
- One way could be to build a matrix then flatten it


`@sample_code`
```{r}
x <- paste0("x",1:20)
y <- paste0("y",1:20)

# assign solution to res
res <- ___
```
`@solution`
```{r}
x <- paste0("x",1:20)
y <- paste0("y",1:20)

# assign solution to res
res <- as.vector(rbind(x,y))

# compare to other possible solutions, sorted by increasing execution time
# note that as.vector is faster than c
# See source for benchmark

# c(rbind(a,b))
# c(rbind(a,b))
# c(matrix(c(a,b),ncol=length(a),,T))
# c(a,b)[rep(1:length(a),each=2)+c(0,length(a))]
# c(mapply(c,a,b))
```
`@sct`
```{r}
test_object("res")
success_msg("Great! Check solution for more insights!")
```





---
## Assign NA to phone numbers of wrong digit length

```yaml
type: NormalExercise

xp: 100

key: e5a4411969
```

[Credit: Krishna, akrun, Roland, Rui Barradas, DJV][1]

[1]: https://stackoverflow.com/questions/50501950/replace-the-phone-numbers-not-having-exactly-10-digits

`@instructions`
How to replace the phone numbers not having exactly 10 digits with NA

    nums <- c(99887766, 998877665521, 9897932453)

Expected output:

    c(NA, NA, 9897932453)

`@hint`
Count characters or compare values, and assign `NA` to subelements or use `is.na<-`


`@sample_code`
```{r}
nums <- c(99887766, 998877665521, 9897932453, 989793453, 9897832453)

# modify nums to replace relevant elements by NA
___
```
`@solution`
```{r}
nums <- c(99887766, 998877665521, 9897932453, 989793453, 9897832453)

# modify nums to replace relevant elements by NA
nums[nchar(nums) != 10] <- NA

# Other possible solutions:
# is.na(nums) <- nchar(nums) !=10
# is.na(nums) <- log10(nums) >= 10 | log10(nums) < 9
# is.na(nums) <- nums >= 1e10 | nums < 1e9
# ifelse(nchar(nums) != 10, NA, nums)
```
`@sct`
```{r}
test_object("nums")
success_msg("Great! Check solution for more insights!")
```





---
## Reformat product lists into a wide table

```yaml
type: NormalExercise

xp: 100

key: bab9ee7da3
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}
library(dplyr)
```

`@solution`
```{r}


```
`@sct`
```{r}
test_object("res")
success_msg("Great! Check source for more insights!")
```





---
## Insert exercise title here

```yaml
type: NormalExercise

xp: 100

key: cb512dd36f
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}
library(ggplot2)
```






