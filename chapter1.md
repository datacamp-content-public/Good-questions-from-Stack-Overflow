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

[Credit: Nikita Pronin,  Uwe][1]

[1]: https://stackoverflow.com/questions/50464389/make-a-named-table-from-list-of-dataframes

`@instructions`
We have a one column `data.frame` containing ids of bundles of products:

          bundle
    1  284993459
    2 1048768805
    3  511310430
    4 1034630958
    5 1235581326

And a list of `data.frames` as long as the above `data.frame` has rows, each item contains the ids of the products contained in the corresponding bundle, and it value :

    [[1]]
        id value
    1   35   0.2
    2 1462   0.2
    3 1109   0.2
    4  220   0.2
    5  211   0.1
    
    [[2]]
    list()
    
    [[3]]
        id name value
    1  394        0.5
    2 1462        0.5
    
    [[4]]
        id name value
    1  926        0.3
    2 1462        0.3
    3  381        0.3
    4  930        0.2
    
    [[5]]
        id name value
    1  926        0.5
    2 1462        0.5
    

We want to build a wide format `data.frame` that will describe the content of each bundle so the output will be the following:

        bundle  35 211 220 381 394 926 930 1109 1462
     284993459 0.2 0.1 0.2 0.0 0.0 0.0 0.0  0.2  0.2
     511310430 0.0 0.0 0.0 0.0 0.5 0.0 0.0  0.0  0.5
    1034630958 0.0 0.0 0.0 0.3 0.0 0.3 0.2  0.0  0.3
    1048768805 0.0 0.0 0.0 0.0 0.0 0.0 0.0  0.0  0.0
    1235581326 0.0 0.0 0.0 0.0 0.0 0.5 0.0  0.0  0.5

`@hint`


`@pre_exercise_code`
```{r}
library(dplyr)
```
`@sample_code`
```{r}
bundle_df =  data.frame(bundle =  c(284993459,1048768805,511310430,1034630958,1235581326))
products <- list(data.frame(id = c(35,1462,1109,220,211), value = c(0.2, 0.2, 0.2,0.2,0.1)), 
                 data.frame(id = NULL, value = NULL), 
                 data.frame(id = c(394,1462), value = c(0.5,0.5)),
                 data.frame(id = c(926,1462,381,930), value = c(0.3,0.3,0.3,0.2)),
                 data.frame(id = c(926,1462), value = c(0.5,0.5)))

# assign solution to res
res <- ___
```
`@solution`
```{r}
bundle_df =  data.frame(bundle =  c(284993459,1048768805,511310430,1034630958,1235581326))
products <- list(data.frame(id = c(35,1462,1109,220,211), value = c(0.2, 0.2, 0.2,0.2,0.1)), 
                 data.frame(id = NULL, value = NULL), 
                 data.frame(id = c(394,1462), value = c(0.5,0.5)),
                 data.frame(id = c(926,1462,381,930), value = c(0.3,0.3,0.3,0.2)),
                 data.frame(id = c(926,1462), value = c(0.5,0.5)))

# assign solution to res
res <- NA
# res <- map2_dfr(bundle$bundle,d2,~mutate(.y,bundle=.x)) %>%
#   spread(id,value,)
# res[is.na(res)] <- 0
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





`@pre_exercise_code`
```{r}
library(ggplot2)
```






