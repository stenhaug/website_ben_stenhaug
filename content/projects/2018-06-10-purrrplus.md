purrrplus
================
2018-06-10

[**See the package website.**](http://stenhaug.github.io/purrrplus)

### Background

In my work, I often need to run a function in R many times (for example
in running a simulation). If any of these runs throw an error, all
progress is lost. The tidyverse package purrrr provides functionality
like *safely* which helps but makes subsequent analysis tricky. As a
remedy, I wrote the package purrrplus which allows for running a
function safely with easy analysis of errors and results.

### Example

``` r
library(purrrplus)
library(tidyverse) # most useful with the tidyverse
```

Imagine you have a function (which returns a named list or a named
vector and might throw an error):

``` r
calculate_if_positive <- function(a, b){
  if(a < 0 & b < 0) {stop("Both numbers are negative.")}
  else if(a < 0) {stop("Just the first number is negative")}
  else if(b < 0) {stop("Just the second number is negative")}
  
  list(add = a + b,
       subtract = a - b,
       multiply = a * b,
       divide = a / b)
}
```

And you want to apply this function to each row of a data frame (which
might contain irrelevant variables):

``` r
(numbers <- data_frame(a = c(-1, 0, 1, 2),
                      b = c(2, 1, 0, -1),
                      irrelevant = c("minneapolis", "st_paul", "minneapolis", "st_paul")))
```

    ## # A tibble: 4 x 3
    ##       a     b irrelevant 
    ##   <dbl> <dbl> <chr>      
    ## 1    -1     2 minneapolis
    ## 2     0     1 st_paul    
    ## 3     1     0 minneapolis
    ## 4     2    -1 st_paul

pmap\_safely adds an error and a result column (which come from applying
the function) to the inputted data
    frame.

``` r
(output <- pmap_safely(numbers, calculate_if_positive))
```

    ## Note that the function does not use the following variables: irrelevant

    ## # A tibble: 4 x 5
    ##       a     b irrelevant  error                              result    
    ##   <dbl> <dbl> <chr>       <chr>                              <list>    
    ## 1    -1     2 minneapolis Just the first number is negative  <NULL>    
    ## 2     0     1 st_paul     <NA>                               <list [4]>
    ## 3     1     0 minneapolis <NA>                               <list [4]>
    ## 4     2    -1 st_paul     Just the second number is negative <NULL>

get\_errors allows for quick analysis of errors:

``` r
get_errors(output)
```

    ## # A tibble: 10 x 5
    ##    variable   value       n_errors count error_rate
    ##    <chr>      <chr>          <int> <int>      <dbl>
    ##  1 a          -1                 1     1        1  
    ##  2 a          2                  1     1        1  
    ##  3 a          0                  0     1        0  
    ##  4 a          1                  0     1        0  
    ##  5 b          -1                 1     1        1  
    ##  6 b          2                  1     1        1  
    ##  7 b          0                  0     1        0  
    ##  8 b          1                  0     1        0  
    ##  9 irrelevant minneapolis        1     2        0.5
    ## 10 irrelevant st_paul            1     2        0.5

get\_results filters out rows with errors and unnests results such that
each item in the list that the function returns has its own column:

``` r
get_results(output)
```

    ## Removed 2 errors out of 4 rows.

    ## # A tibble: 2 x 7
    ##       a     b irrelevant  add_result subtract_result multiply_result
    ##   <dbl> <dbl> <chr>            <dbl>           <dbl>           <dbl>
    ## 1     0     1 st_paul              1              -1               0
    ## 2     1     0 minneapolis          1               1               0
    ## # ... with 1 more variable: divide_result <dbl>
