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

[1]: https://stackoverflow.com/questions/50516915/interlacing-two-vectors/50517503#50517503

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
# Update this to something more informative.
test_object("res")
success_msg("Great! Check solution for more insights!")
print("hello")
```



