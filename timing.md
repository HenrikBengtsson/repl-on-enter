# REPL timing

Reports on evaluation time of a REPL call.

## Usage

```r
repl_timeit()
```

## Example

```r
> Sys.sleep(2.3)
[repl] Ellapsed time: 2.3 s
>
```


## Implementation

```r
repl_timeit <- local({
  start <<- proc.time()

  addTaskCallback(name = "repl_timeit", function(expr) {
    start <<- proc.time()
  }, before = TRUE)

  addTaskCallback(name = "repl_timeit", function(expr) {
    duration <- proc.time() - start
    message(sprintf("[repl] Ellapsed time: %g s", duration[3]))
  })
})
```
